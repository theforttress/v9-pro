# Production Deployment Checklist

1. Set strong secrets:
   JWT_SECRET=$(openssl rand -hex 32)
   DB_PASSWORD=$(openssl rand -base64 32)

2. Enable 2FA for admin:
   POST /api/v1/auth/2fa/setup

3. Run tests:
   pytest -v

4. Deploy with:
   docker-compose -f docker-compose.prod.yml up -d

5. Monitor:
   docker logs -f api
