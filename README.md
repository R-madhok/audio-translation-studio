# SLAM Labs HTML Translator — Setup

Converts an English HTML learning module into a trilingual (English / हिंदी / ਪੰਜਾਬੀ) version with audio narration buttons.

## Setup (one time, ~2 minutes)

1. Save `translator.html` anywhere on your computer (Desktop is fine). Don't run it from a web preview (Google Drive / OneDrive viewer) — download it first.
2. Open it by double-clicking, or right-click → Open with → Chrome or Edge.
3. Click **⚙ Settings** (top of the page) and paste:
   - OpenAI API key (for translation)
   - ElevenLabs API key (for audio)
   Keys are saved in your browser — you only do this once per machine.
4. Click **Test connections**. Both should show ✓.

## Using it

1. Drop the English module (.html) into the input box.
2. Click **Convert**. Translation takes a minute or two; audio generation takes longer and shows a cost estimate first (you can untick "Generate ElevenLabs audio" for a quick text-only run).
3. Download the result — filename includes date and time. The output file is fully self-contained: it needs no API keys and works offline.

**Fixing repeated translation mistakes:** if the model keeps getting a term wrong, open ⚙ Settings → Glossary and add a line like `integer = पूर्णांक = ਸੰਪੂਰਨ ਸੰਖਿਆ`. The model is forced to use your translation everywhere that term appears. The glossary is saved in your browser and applies to every future conversion — build it up as you review outputs.

## How to get an OpenAI API key

1. Create an account at `https://platform.openai.com` (this is separate from ChatGPT — a ChatGPT subscription does not include API access).
2. Add billing: Settings → Billing → Add payment method, then buy prepaid credits (minimum $5, billed in USD). $5–10 is plenty for many module translations.
3. Create the key: Settings → API keys → "Create new secret key". It starts with `sk-`. Copy it immediately — it is shown only once.
4. Recommended: set a monthly spending limit under Billing → Limits.

**Notes for India:**
- UPI works for ChatGPT subscriptions but NOT for API credits — API billing is card-only (Visa/Mastercard/Amex, charged in USD).
- Indian RuPay and many debit cards are rejected. Use a credit card with international transactions enabled (switch this on in your bank's app first). Expect a 3–5% foreign transaction fee.
- If no card works, virtual international cards (e.g. Wise, Payoneer) are a common workaround.
- Simplest for a team: one person creates the account, buys credits, and shares one key with the team — then only one person needs to deal with payment.

## How to get an ElevenLabs API key

1. Sign up at `https://elevenlabs.io`.
2. The free tier gives ~10,000 credits/month ≈ 10 minutes of audio with the multilingual model — fine for testing, but a full module with audio in 3 languages will need a paid plan (Starter is ~$5/month; Creator ~$22/month). Card payment in USD, same India notes as above.
3. Create the key: click your profile (bottom-left) → API Keys → "Create API Key". It starts with `sk_`.
4. If asked about key permissions, enable at least "Text to Speech". ("Voices: Read" is optional — it only powers the voice-browser button in Settings.)
5. The app shows a character-cost estimate before generating audio, so you can see usage before committing credits.

## If you see "Failed to fetch"

Something on your machine is blocking the API. In order of likelihood:
- Ad-blocker or browser tracking prevention → try an InPrivate/Incognito window
- Antivirus "web protection" or office firewall/VPN → try another network
- Check `https://api.openai.com/v1/models` opens in a browser tab (any JSON response = network is fine)
