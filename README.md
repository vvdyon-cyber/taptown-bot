# 🤖 tap_town Discord Bot

Welkom + Ticket bot voor de TapTown Discord server.

---

## 📦 Installatie

### 1. Vereisten
- [Node.js](https://nodejs.org) v18 of nieuwer
- VS Code (aanbevolen)

### 2. Dependencies installeren
Open de map in VS Code, open de terminal (`Ctrl + ~`) en run:
```bash
npm install
```

### 3. Bot aanmaken op Discord
1. Ga naar https://discord.com/developers/applications
2. Klik **New Application** → naam: `tap_town`
3. Ga naar **Bot** → klik **Add Bot**
4. Kopieer het **Token** → plak in `config.json`
5. Zet aan onder **Privileged Gateway Intents**:
   - ✅ Server Members Intent
   - ✅ Message Content Intent

### 4. Bot uitnodigen op je server
Ga naar **OAuth2 → URL Generator**:
- Scopes: `bot`, `applications.commands`
- Permissions: `Manage Channels`, `Send Messages`, `Read Message History`, `Manage Roles`

Kopieer de link en nodig de bot uit.

---

## ⚙️ Config instellen (`config.json`)

| Veld | Wat invullen |
|------|-------------|
| `token` | Bot token van Discord Developer Portal |
| `guildId` | Rechtermuisklik op je server → Kopieer Server ID |
| `welcomeChannelId` | ID van je #welkom kanaal |
| `welcomeMessage` | Welkomsttekst (`{user}` = mention) |
| `ticketCategoryId` | ID van de categorie waar tickets komen |
| `staffRoleId` | ID van je Staff rol |
| `ticketLogChannelId` | ID van je log kanaal |

> **IDs kopiëren?** Zet Discord in Developer Mode: Instellingen → Geavanceerd → Ontwikkelaarsmodus. Dan rechtermuisklik op kanaal/rol/server → Kopieer ID.

---

## 🚀 Starten

```bash
npm start
```

Of met auto-restart bij wijzigingen (handig tijdens ontwikkeling):
```bash
npm run dev
```

---

## 🗂️ Bestandsstructuur

```
taptown-bot/
├── index.js          ← Hoofdbestand
├── config.json       ← Instellingen (niet uploaden naar GitHub!)
├── package.json
└── events/
    ├── welcome.js    ← Welkom embed bij nieuwe leden
    └── ticket.js     ← /ticket slash command + buttons
```

---

## ✨ Features

### 👋 Welkomstbot
- Stuurt een gouden embed naar het welkomstkanaal
- Vermeldt de gebruiker, avatar, link naar de shop en info over tickets

### 🎫 Ticketbot
- `/ticket` → maakt een privé kanaal aan
- Staff en gebruiker kunnen het kanaal zien
- **Claimen** knop voor staffleden
- **Sluiten** knop → logt het ticket en verwijdert het kanaal na 5 seconden
# taptown-bot
# taptown-bot
