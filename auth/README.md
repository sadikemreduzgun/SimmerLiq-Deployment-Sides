1. Go to AWS Cognito
2. Create user pool
3. Select traditional web app
4. Email and username sign in identifier
5. Return url
6. Buy a domain cheap
7. Get the domain to AWS Route53 hosted zones by changing NS records
8. Configure custom domain in Cognito
9. Create auth.domain.com certificate in ACM for custom domain configuration
10. Get Alias target from Cognito>User Pools>Branding>Domain
11. Go to Route53 again and add an A record selecting alias option and in the services menu, select alias to CloudFront distribution and paste Alias target copied.
