git clone https://github.com/angkerith1/rithtopup-site.git
cd rithtopup-site
npm install
cp .env.example .env
DATABASE_URL="postgresql://user:pass@host/db?sslmode=require"
JWT_SECRET="$(openssl rand -base64 32)"
ADMIN_EMAIL="you@example.com"
ADMIN_PASSWORD="YourStrongPassword!"
PAYMENT_SIMULATION_MODE="true"
-join ((1..48) | ForEach-Object { [char[]](48..57+65..90+97..122) | Get-Random })
npx prisma generate
npx prisma db push
npm run db:seed
