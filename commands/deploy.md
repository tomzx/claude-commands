Deploy the application to a target environment.

## Instructions

1. **Pre-Deployment Checklist**
   - Verify all tests pass in CI/CD
   - Confirm code review and approval
   - Check deployment branch (main/master/release)
   - Review deployment plan
   - Ensure rollback plan is ready
   - Verify configuration for target environment
   - Check dependency compatibility

2. **Identify Deployment Type**
   - **Cloud Platforms**: AWS, GCP, Azure, Heroku
   - **Container**: Docker, Kubernetes
   - **Serverless**: AWS Lambda, Cloud Functions
   - **Traditional**: VPS, bare metal
   - **Static**: Vercel, Netlify, GitHub Pages

3. **Prepare Deployment**
   - Build production artifacts:
     - JavaScript: `npm run build`
     - Python: Build wheels/packages
     - Go: Build binary with `go build`
     - Rust: `cargo build --release`
   - Run production checks:
     - Minification and optimization
     - Remove debug code
     - Security audit
     - Check environment variables

4. **Database Migrations**
   - Review pending migrations
   - Test migrations in staging first
   - Run migrations with backup ready:
     - Django: `python manage.py migrate`
     - Rails: `rake db:migrate`
     - Node: Run migration scripts
   - Verify migrations completed successfully

5. **Deploy Application**

   **Container Deployment:**
   ```bash
   docker build -t app:version .
   docker push registry/app:version
   kubectl set image deployment/app app=registry/app:version
   kubectl rollout status deployment/app
   ```

   **Serverless:**
   ```bash
   # AWS Lambda
   aws lambda update-function-code --function-name myapp

   # Vercel
   vercel --prod
   ```

   **Traditional:**
   ```bash
   git pull origin main
   # Install dependencies
   # Restart services
   sudo systemctl restart myapp
   ```

6. **Post-Deployment Verification**
   - Check application health endpoints
   - Verify critical functionality works
   - Monitor error rates and logs
   - Check performance metrics
   - Run smoke tests
   - Verify database migrations applied
   - Test user-facing features

7. **Monitor Deployment**
   - Watch application logs for errors
   - Monitor metrics (CPU, memory, requests)
   - Check error tracking (Sentry, Rollbar)
   - Verify no increase in error rates
   - Monitor for 15-30 minutes after deployment

8. **Rollback Plan**
   - If issues detected:
     - Assess severity (critical vs minor)
     - Execute rollback if critical:
       ```bash
       # Kubernetes
       kubectl rollout undo deployment/app

       # Revert to previous version
       git revert <commit>
       # Re-deploy previous version
       ```
   - Document issues for post-mortem

## Deployment Best Practices

- Deploy during low-traffic periods
- Use blue-green or canary deployments for zero downtime
- Always test in staging before production
- Keep deployment process automated
- Monitor closely after deployment
- Have rollback plan ready
- Document deployment steps
- Use feature flags for risky features

## Output

Provide a deployment report:
- **Environment**: Target deployment environment
- **Version**: Version being deployed
- **Pre-Deployment Checks**: Checklist completion status
- **Deployment Method**: How application was deployed
- **Migrations**: Database migration status
- **Verification Results**: Post-deployment checks
- **Monitoring**: Initial metrics and logs
- **Issues**: Any problems encountered
- **Status**: Deployment success/failure/rolled back
- **Next Steps**: Any follow-up actions needed
