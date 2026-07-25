# Codes - BallsDex Extension

A redeemable promo codes system for BallsDex Discord bot (v3).

## Features

- `/redeem` slash command for code redemption
- Reward types: Countryball, Countryball + Special, Money
- Configurable max uses, per-user limits, and expiration dates
- Admin integration via Django

## Installation

Add to your BallsDex `extra.toml`:

```toml
[[ballsdex.packages]]
location = "git+https://github.com/haithanh456/Codes.git@main"
path = "codes_app"
enabled = true
```

Then build & restart your instance by running `docker compose up -d --build`.

## Configuration

Create promo codes through the Django admin panel with the following fields:

| Field | Description |
| ----- | ----------- |
| `code` | Case-insensitive promo string |
| `reward_type` | `ball`, `ball_special`, or `money` |
| `amount` | Money amount (for money reward) |
| `ball` | Specific ball (blank = random) |
| `special` | Special event (for ball + special) |
| `max_uses` | Max redemptions (blank = unlimited) |
| `single_use_per_user` | One redemption per player |
| `expires_at` | Expiration datetime |

## License

MIT
