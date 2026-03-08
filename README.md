# Autiste Vêtements - Backend API

Backend Node.js/Express pour gérer les paiements Stripe.

## Installation locale

```bash
cd backend
npm install
cp .env.example .env
# Édite .env avec tes clés
npm run dev
```

## Déploiement sur Vercel

1. Crée un nouveau repo GitHub pour le backend
2. Push le code:
```bash
git init
git add .
git commit -m "Initial backend"
git remote add origin https://github.com/ton-username/autiste-vetements-backend.git
git push -u origin main
```

3. Va sur Vercel → New Project → Import ton repo backend
4. Configure les variables d'environnement:
   - `STRIPE_SECRET_KEY`: Ta secret key Stripe (sk_live_...)
   - `FRONTEND_URL`: https://ton-site.vercel.app
5. Deploy!

## Endpoints

- `GET /` - Health check
- `POST /api/create-checkout-session` - Créer une session Stripe
- `POST /api/webhook` - Webhook Stripe

## Utilisation

Une fois déployé, update `config.js` dans le frontend avec l'URL du backend:
```javascript
const BACKEND_URL = 'https://ton-backend.vercel.app';
```
