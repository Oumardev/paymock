# 🧪 paymock

> Simulateur de paiements pour projets en développement (CinetPay, Stripe, PayDunya, TouchPay)

**paymock** est un outil de simulation de paiements qui permet aux développeurs de tester facilement leurs intégrations sans se connecter aux vraies API des services de paiement.  
Il simule la création de transaction, les redirections et les webhooks (IPN) pour un environnement de développement fluide et sans stress.

---

## 🚀 Installation

```bash
npx paymock init --provider=cinetpay
Vous pouvez remplacer cinetpay par stripe, paydunya, touchpay, etc.

⚙️ Utilisation
Une fois lancé, paymock démarre un serveur Express local avec les endpoints suivants :

/init-payment
Initie une transaction de paiement simulée.

Exemple de requête :

```bash
curl -X POST http://localhost:3000/init-payment \
     -H "Content-Type: application/json" \
     -d '{"amount": 5000, "currency": "XOF"}'
```
Réponse simulée :

```json
{
  "status": "WAITING",
  "transaction_id": "TX-CINET-123456",
  "redirect_url": "http://localhost:3000/fake-payment-page"
}
/simulate-callback
Simule un envoi de webhook vers votre backend.

Vous pouvez configurer la cible du callback via un fichier .env ou un paramètre d'initialisation (à venir).

📦 Fournisseurs supportés
✅ CinetPay

🔜 PayDunya

🔜 Stripe

🔜 TouchPay

Vous pouvez facilement en ajouter d'autres via le dossier src/providers.

🛠️ Personnalisation
Prochainement configurable :

Le comportement (succès, échec, timeout)

La devise, les montants

Les délais de réponse

Le corps du webhook

Les logs des paiements simulés

📄 Licence
Ce projet est sous licence ISC — voir le fichier LICENSE pour plus d’informations.

👨‍💻 Auteur
Développé avec ❤️ par Oumar Cissé

---