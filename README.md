# Stock-Dashboard

A polished stock trend analyzer and currency converter built with Next.js 16, React 19, TypeScript, and Tailwind CSS.

Stock-Dashboard provides a unified experience for tracking stock quotes, viewing market sentiment, converting USD to THB, and obtaining AI-powered investment insights.

## Features

- Stock quote search for individual tickers
- Real-time summary of market status and macro trend indicators
- Interactive candlestick charts for price history
- Stock news retrieval for company-specific events
- USD to THB currency conversion
- Local watchlist persistence
- Search history persistence
- AI analysis with OpenRouter for structured stock insights
- Built-in API routes for data aggregation and caching

## Tech Stack

- Next.js 16 (App Router)
- React 19
- TypeScript
- Tailwind CSS v4
- Framer Motion
- Radix UI
- OpenRouter API
- Yahoo Finance, Alpha Vantage, Finnhub, ExchangeRate API

## Repository Structure

- `src/app/`
  - `page.tsx` - Main application page
  - `layout.tsx` - Root layout and metadata
  - `api/` - Server-side endpoints used by the app
    - `stock/[symbol]/route.ts` - Stock quote data
    - `stock/[symbol]/news/route.ts` - News data
    - `stock/[symbol]/indicators/route.ts` - Technical indicators
    - `exchange/route.ts` - USD/THB exchange rate
    - `market/route.ts` - Market overview data
    - `ai/route.ts` - AI analysis endpoint
- `src/components/`
  - `features/` - Domain features like stock analyzer, charts, converter
  - `ui/` - Reusable UI components like buttons, cards, inputs
- `src/hooks/` - Custom hooks for persistence and local state
- `src/lib/` - Shared types, utilities, validation logic
- `public/` - Static assets

## Environment Variables

Create a `.env.local` file from `.env.example` and provide the required keys:

- `OPENROUTER_API_KEY` - OpenRouter API key for AI analysis
- `ALPHA_VANTAGE_API_KEY` - Alpha Vantage API key for technical indicators and fundamentals
- `FINNHUB_API_KEY` - Finnhub API key for news data
- `NEXT_PUBLIC_APP_URL` - Optional public app URL for API referer headers

## Setup

1. Install dependencies

```bash
npm install
```

2. Run the development server

```bash
npm run dev
```

3. Open the app

```text
http://localhost:3000
```

## Scripts

- `npm run dev` - Start the Next.js development server
- `npm run build` - Create a production build
- `npm run lint` - Run ESLint checks
- `npm start` - Start the production server after build

## API Routes

### `GET /api/stock/[symbol]`
Fetches stock quote data from Yahoo Finance with input validation and response caching.

### `GET /api/exchange`
Returns USD/THB exchange rate data.

### `GET /api/market`
Provides market overview and global sentiment information.

### `POST /api/ai`
Sends stock data to OpenRouter and returns structured AI analysis.

## Notes

- The app uses local storage for search history and watchlist persistence.
- API routes centralize third-party calls and help avoid exposing API keys in the browser.
- The project is designed for extension: add new indicators, new news sources, or new currency pairs.

## Contribution

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a pull request

## License

This project is provided under the MIT License.
