# Stork Verify Bot

An automation to validate transactions based on the Stork Verify extension efficiently.

## Features

- Automated price data validation from Stork Oracle API
- Secure authentication with credentials stored in `config.json`
- Periodic validation and submission of results
- Token refresh for continuous operation
- Real-time validation statistics and status updates
- Proxy support for distributed request handling
- **Multi-Accounts** support for managing multiple account

## Prerequisites

Before running the bot, make sure you have:

- Node.js (v14 or higher)
- A valid Stork Oracle account (register [here](https://chromewebstore.google.com/detail/stork-verify/knnliglhgkmlblppdejchidfihjnockl) and input referral code `XTY6GVCFLT`)
- Properly configured `config.json` file

## Installation

1. Clone the repository:

```bash
git clone https://github.com/itsnodrops/krots-ver-bot.git
```

2.  Navigate to the project directory:

```bash
cd krots-ver-bot
```

3. Install dependencies:

```bash
npm install
```

4. Edit `config.json` with your Stork Oracle account credentials:

```json
{
  "accounts": [
    {
      "username": "your-email-1@example.com",
      "password": "your-password-1"
    },
    {
      "username": "your-email-2@example.com",
      "password": "your-password-2"
    }
  ],
  "stork": {
    "intervalSeconds": 60
  },
  "concurrency": {
    "maxTasks": 1
  },
  "proxy": {
    "enable": false
  }
}
```

> - Replace `username` and `password` value with your actual credentials
> - stork.intervalSeconds → Validation interval in seconds (default: 60)
> - concurrency.maxTasks → Number of concurrent validation workers (default: 1)
> - proxy.enable → Set to true to enable proxies

### Optional: Proxy Configuration

To use proxy servers for distribution of requests:

1. Edit `proxies.txt` file in the project root

```bash
nano proxies.txt
```

2. Add one proxy per line in any of these formats:

   - HTTP proxies: `http://user:pass@host:port`
   - SOCKS proxies: `socks5://user:pass@host:port`

3. Enable proxy usage in `config.json`:

```json
"proxy": {
  "enable": true
}
```

## Usage

Start the bot:

```bash
npm start
```

## Project Structure

```
krots-ver-bot/
├── index.js         # Main bot script
├── config.json      # Bot configuration file
├── package.json     # Project dependencies
├── tokens.json      # Token storage for authentication
├── proxies.txt      # Proxy list (optional)
└── src
    ├── banner.js    # Dashboard banner configuration
    ├── colors.js    # Color scheme configuration
    └── ..
```

## Features Explained

- Authenticate using account(s) credentials in `config.json`
- Process accounts with proxy from `proxy.txt` file(if available)
- Fetch signed price data from Stork Oracle API
- Validate and submit results at regular intervals
- Display real-time validation statistics

## Troubleshooting

- Authentication Error: Ensure your username and password are correct in config.json
- Bot Fails to Start: Check if config.json is properly formatted
- Token Expired Issues: Delete tokens.json and restart the bot
- Connection Issues: Verify your internet connection and Stork Oracle API availability
- Proxy Errors: Ensure proxies.txt is correctly formatted

## Support & Links

- Reference: [https://github.com/airdropinsiders](https://github.com/airdropinsiders/Stork-Auto-Bot)
- GitHub: https://github.com/itsnodrops
- Telegram: https://t.me/NoDrops

## Security Notice

Important: Your credentials are sensitive information. Never share them with anyone and ensure `config.json` is properly secured.

## Contributing

Need source code? Feel free to DM me.

## Disclaimer

This bot is provided as-is, without any warranties. Users are responsible for their own actions. Ensure you understand the risks before using this tool.

## License

This project is licensed under the [MIT License](https://github.com/itsnodrops/poolnepo-bot/blob/main/LICENSE).

## Donation

If you want to support the development of this project, you can use this referral code:
```
XTY6GVCFLT
```

## Community

Join our community:

- [![Telegram](https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Telegram_logo.svg/12px-Telegram_logo.svg.png)](https://t.me/NoDrops) [NoDrops Telegram Channel](https://t.me/NoDrops)
- [![Telegram](https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Telegram_logo.svg/12px-Telegram_logo.svg.png)](https://t.me/NoDropsChat) [NoDrops Telegram Group](https://t.me/NoDropsChat)
