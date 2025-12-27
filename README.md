# AI News Sentinel & Analytics Engine 🤖📰

A robust, automated data processing (ETL) pipeline designed to monitor real-time news feeds, generate intelligent summaries using Large Language Models (LLMs), and distribute insights across multiple platforms.

## 🚀 Key Features
- **Real-time Monitoring:** Continuously polls RSS feeds (e.g., TechCrunch, Reuters) for new articles.
- **AI-Powered Analysis:** Leverages the `gpt-4o-mini` model to synthesize complex articles into 3-point concise summaries.
- **Smart Filtering:** Integrated logic layer to filter news by specific keywords (e.g., Tech, Economy, AI), significantly reducing API token consumption.
- **Multi-channel Distribution:** - **Data Archiving:** Structured logging in **Google Sheets** for long-term storage.
  - **Instant Alerts:** Real-time push notifications via a custom **Telegram Bot**.

## 🛠️ Tech Stack
- **Orchestration:** [Make.com](https://make.com)
- **AI/LLM:** OpenAI API (GPT-4o)
- **Data Protocols:** RSS (XML) / HTTP
- **Database:** Google Sheets API
- **Communication:** Telegram Bot API

## 📐 System Architecture
1. **Trigger:** RSS Watcher (configured for 60-minute polling intervals).
2. **Filter:** Boolean logic layer for keyword matching (case-insensitive).
3. **AI Layer:** Prompt engineering focused on structured, bulleted summaries.
4. **Storage Layer:** Dynamic data mapping into Google Sheets relational structure.
5. **Notification Layer:** Telegram Bot API execution for mobile alerts.

## 📦 How to Use
1. Import the `blueprint.json` file into your Make.com dashboard.
2. Configure API connections for:
   - OpenAI (API Key)
   - Google Sheets (OAuth2)
   - Telegram Bot (Bot Token)
3. Ensure your Google Sheet has the following headers: `Title`, `Link`, `AI Summary`, `Date`.
4. Set the Scheduling to **ON**.

## 📝 Developer Insights & Optimization
* **Cost Efficiency:** Optimized the workflow by placing filter modules before AI modules, ensuring OpenAI tokens are only spent on relevant data.
* **Data Normalization:** Implemented `formatDate` functions to standardize various ISO timestamps into a human-readable `DD.MM.YYYY HH:mm` format.
* **Protocol Handling:** Successfully managed XML-to-JSON parsing challenges common in legacy RSS feed structures.
