IMAGE LINK BOT - UPDATED BUILD

Required Render environment variables:
- TOKEN: Telegram token for the primary bot
- MAIN_ADMIN_ID: numeric Telegram ID of the Main Admin (do not use a username)
- DATA_DIR: /var/data only when a Render Persistent Disk is mounted at /var/data

The existing admin panel functions (statistics, broadcast, user list, ban/unban,
and bot on/off) are retained. Main Admin can configure links from Admin Panel >
Bot Links / Owner Setup by sending:
  owner https://your-owner-link
  createbot https://t.me/your_creation_bot

Important implementation status:
- The requested persistent main-menu keyboard, profile details/photo, menu routes,
  configurable Owner/creation links, fixed Main Admin ID, and 2.5-second upload
  completion delay are included.
- Telegram does not support arbitrary custom background colors for ordinary
  keyboard buttons; clients choose their own button styling.
- Full multi-tenant bot provisioning (BotFather token intake, approval queue,
  separate running bot instances, per-customer bot databases/admin panels, and
  per-customer bot ON/OFF/DELETE) is not implemented in this build. Do not treat
  the Image2 URL Bot button as a working bot-provisioning system yet.
- Language currently has a saved EN/BN selector notice; complete translation of
  every existing screen is not yet implemented.

Deploy with Node.js 22-25 and keep a persistent disk mounted for SQLite data.
