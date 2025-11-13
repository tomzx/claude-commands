Conduct performance testing and identify bottlenecks.

## Instructions

1. **Define Performance Goals**
   - Response time targets (e.g., API < 200ms)
   - Throughput requirements (requests/second)
   - Resource usage limits (CPU, memory)
   - Concurrent user capacity
   - Database query performance

2. **Identify Performance Test Scenarios**
   - Critical user journeys
   - High-traffic endpoints
   - Resource-intensive operations
   - Database-heavy workflows
   - Peak load situations

3. **Set Up Performance Testing**
   - Choose performance testing tools:
     - Load testing: `locust`, `k6`, `artillery`, `jmeter`
     - Profiling: `py-spy`, `cProfile`, Chrome DevTools, `perf`
     - Database: `pg_stat_statements`, slow query logs
     - APM: `newrelic`, `datadog`, `elastic APM`

4. **Run Performance Tests**

   **Load Testing:**
   - Start with baseline load (single user)
   - Gradually increase concurrent users
   - Identify breaking point
   - Measure response times at different loads
   - Check for memory leaks over time

   **Profiling:**
   - Profile critical code paths
   - Identify slow functions
   - Analyze CPU usage
   - Check memory allocation patterns
   - Review database query performance

5. **Analyze Results**
   - Response time distribution (p50, p95, p99)
   - Throughput at different load levels
   - Error rate under load
   - Resource utilization (CPU, memory, disk I/O)
   - Database query times
   - Identify bottlenecks:
     - Slow queries (N+1, missing indexes)
     - CPU-bound operations
     - Memory leaks
     - Blocking I/O
     - Inefficient algorithms

6. **Optimize Performance**
   - Add database indexes
   - Implement caching
   - Optimize queries (reduce N+1)
   - Use async/await for I/O operations
   - Implement pagination
   - Add connection pooling
   - Optimize algorithms
   - Consider caching strategies

7. **Verify Improvements**
   - Re-run performance tests
   - Compare before/after metrics
   - Ensure optimizations didn't break functionality
   - Check that issues are resolved

## Common Performance Issues

- **Database**: N+1 queries, missing indexes, large result sets
- **API**: Synchronous external calls, no caching, large payloads
- **Memory**: Leaks, unbounded collections, unnecessary copying
- **CPU**: Inefficient algorithms, unnecessary computation
- **Network**: Too many requests, large responses, no compression

## Output

Provide a performance test report:
- **Test Scenarios**: What was tested
- **Performance Goals**: Target metrics
- **Test Results**:
  - Response time statistics (min, max, mean, p95, p99)
  - Throughput (requests/second)
  - Error rates
  - Resource usage
- **Bottlenecks Identified**: Specific performance issues found
- **Optimizations Applied**: Changes made to improve performance
- **Before/After Comparison**: Performance improvements achieved
- **Recommendations**: Further optimization opportunities
