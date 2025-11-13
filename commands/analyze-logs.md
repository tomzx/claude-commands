Analyze application logs to identify issues and patterns.

## Instructions

1. **Locate Log Files**
   - Application logs
   - Error logs
   - Access logs (web server, API)
   - System logs
   - Database query logs

2. **Identify Log Format**
   - Plain text logs
   - JSON structured logs
   - Common log formats (Apache, nginx)
   - Application-specific formats

3. **Define Analysis Goal**
   - Find errors and exceptions
   - Identify performance issues
   - Detect unusual patterns
   - Track specific user actions
   - Monitor API usage
   - Investigate specific incident

4. **Analyze Logs**

   **Find Errors:**
   ```bash
   # Recent errors
   grep -i "error\|exception\|fatal" app.log | tail -50

   # Error frequency by type
   grep -i "error" app.log | awk '{print $NF}' | sort | uniq -c | sort -rn

   # Errors in last hour
   grep -i "error" app.log | grep "$(date -u +%Y-%m-%d\ %H)" | wc -l
   ```

   **Performance Analysis:**
   ```bash
   # Slow requests (>1000ms)
   grep "duration" app.log | awk '$NF > 1000' | tail -20

   # Average response time
   grep "duration" app.log | awk '{sum+=$NF; count++} END {print sum/count}'

   # Top slowest endpoints
   grep "path=" app.log | awk '{print $(NF-1), $NF}' | sort -k2 -rn | head -10
   ```

   **Traffic Patterns:**
   ```bash
   # Requests per hour
   awk '{print $4}' access.log | cut -c 14-15 | sort | uniq -c

   # Top IP addresses
   awk '{print $1}' access.log | sort | uniq -c | sort -rn | head -20

   # Most accessed endpoints
   awk '{print $7}' access.log | sort | uniq -c | sort -rn | head -20
   ```

5. **Use Log Analysis Tools**

   **Command-line tools:**
   - `grep`, `awk`, `sed`: Pattern matching and text processing
   - `jq`: JSON log parsing
   - `goaccess`: Real-time web log analyzer
   - `lnav`: Advanced log viewer

   **Application-specific:**
   - Python: `structlog`, `loguru` with parsing scripts
   - Node.js: `winston`, `bunyan` with analysis tools
   - For structured logs: Query with `jq` or `python -m json.tool`

   **Example with structured JSON logs:**
   ```bash
   # Errors by severity
   cat app.log | jq -r 'select(.level=="error") | .message' | sort | uniq -c

   # Average response time by endpoint
   cat app.log | jq -r 'select(.endpoint) | "\(.endpoint) \(.duration)"' | \
     awk '{sum[$1]+=$2; count[$1]++} END {for(e in sum) print e, sum[e]/count[e]}'

   # Errors timeline
   cat app.log | jq -r 'select(.level=="error") | .timestamp' | cut -c 1-13 | \
     uniq -c
   ```

6. **Identify Patterns**
   - Recurring errors
   - Error spikes at specific times
   - Correlated errors
   - User-specific issues
   - Geographic patterns
   - Performance degradation over time

7. **Create Summary**
   - Error rate (total, by type)
   - Most common errors
   - Performance metrics (avg, p95, p99)
   - Traffic patterns
   - Anomalies detected
   - Recommendations for fixes

## Common Log Analysis Tasks

**Find stack traces:**
```bash
grep -A 20 "Traceback\|Exception" app.log
```

**Extract specific user's actions:**
```bash
grep "user_id=123" app.log
```

**Count log levels:**
```bash
grep -oE "(DEBUG|INFO|WARNING|ERROR|CRITICAL)" app.log | sort | uniq -c
```

**Find memory-related issues:**
```bash
grep -i "memory\|oom\|out of memory" app.log
```

**Analyze database queries:**
```bash
# Slow queries
grep "duration" db.log | awk '$NF > 1000' | sort -k NF -rn | head -20
```

## Best Practices

- Use structured logging (JSON) for easier analysis
- Include request IDs to trace requests across services
- Log at appropriate levels (DEBUG, INFO, WARNING, ERROR)
- Include context (user ID, request ID, timestamp, etc.)
- Don't log sensitive data (passwords, tokens, PII)
- Rotate logs to prevent disk space issues
- Use centralized logging for distributed systems
- Set up alerts for critical errors

## Output

Provide a log analysis report:
- **Time Range**: Logs analyzed (from/to timestamps)
- **Log Volume**: Total log entries analyzed
- **Error Summary**:
  - Total errors
  - Error rate
  - Top errors by frequency
  - Recent errors
- **Performance Metrics**:
  - Average response time
  - Slow requests
  - Performance trends
- **Traffic Analysis**:
  - Request volume
  - Top endpoints
  - Traffic patterns
- **Anomalies**: Unusual patterns or spikes
- **Recommendations**: Issues to investigate or fix
- **Action Items**: Specific problems requiring attention
