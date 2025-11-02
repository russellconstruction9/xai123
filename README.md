# CustodyX.AI

A neutral co-parenting incident tracker powered by AI to help divorced or separated parents log and analyze incidents for legal documentation.

## Features

- **AI-Powered Incident Logging**: Conversational interface to document co-parenting incidents with structured output
- **Incident Timeline**: Chronological view of all logged incidents
- **Pattern Analysis**: Identify recurring themes and behaviors across incidents
- **Deep Analysis**: Forensic analysis of individual incidents (Pro tier)
- **Legal Assistant**: AI-powered assistant for legal questions and document drafting
- **Document Library**: Store and manage legal documents
- **Evidence Package Builder**: Build comprehensive evidence packages from selected incidents
- **Voice Agent**: AI voice assistant for hands-free navigation (Pro tier)
- **Calendar View**: Visual calendar of incidents
- **PWA Support**: Progressive Web App with offline capabilities

## Prerequisites

- Node.js 18+ and npm
- Google Gemini API key ([Get one here](https://makersuite.google.com/app/apikey))

## Setup

### 1. Install Dependencies

```bash
npm install
```

### 2. Configure Environment Variables

Copy `.env.example` to `.env`:

```bash
cp .env.example .env
```

Edit `.env` and add your Google Gemini API key:

```
GEMINI_API_KEY=your_actual_api_key_here
```

### 3. Run Development Server

```bash
npm run dev
```

The app will be available at `http://localhost:3000`

### 4. Build for Production

```bash
npm run build
```

The production build will be in the `dist/` directory.

### 5. Preview Production Build

```bash
npm run preview
```

## External Services

### Google Gemini AI

This application uses Google's Gemini AI for:
- Incident report generation
- Legal document drafting
- Pattern analysis
- Deep behavioral analysis
- Voice agent functionality

**Setup:**
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Add the key to your `.env` file as `GEMINI_API_KEY`

**Usage Limits:**
- Free tier: 50,000 tokens/month
- Plus tier: 500,000 tokens/month  
- Pro tier: 5,000,000 tokens/month

The app tracks token usage and enforces limits based on subscription tier.

## Project Structure

```
custodyx-ai/
├── public/
│   ├── icon.svg
│   ├── manifest.json
│   └── service-worker.js
├── src/
│   ├── components/       # React components
│   ├── constants/        # Constants and prompts
│   ├── services/         # API services
│   ├── types.ts          # TypeScript type definitions
│   ├── App.tsx           # Main app component
│   └── main.tsx          # Entry point
├── .env.example          # Environment variables template
├── index.html            # HTML template
├── package.json
├── tsconfig.json
└── vite.config.ts        # Vite configuration
```

## Data Storage

The application uses **localStorage** for data persistence. All data is stored locally in the browser:
- Incident reports
- User profile
- Documents
- Incident templates
- Messages
- Subscription settings
- Token usage

**Note:** Data is not synced across devices or backed up automatically.

## Deployment on Bolt.new

### Method 1: Direct ZIP Upload

1. Create a ZIP file of the entire project folder
2. Go to [Bolt.new](https://bolt.new)
3. Click "Import" and select your ZIP file
4. Add your `GEMINI_API_KEY` to the environment variables in Bolt's settings

### Method 2: GitHub Integration

1. Push your code to a GitHub repository
2. In Bolt.new, connect your GitHub account
3. Select the repository
4. Configure environment variables in Bolt's settings

### Bolt Configuration

In Bolt.new, you may need to configure:

1. **Environment Variables:**
   - `GEMINI_API_KEY`: Your Google Gemini API key

2. **Build Command:**
   ```
   npm install && npm run build
   ```

3. **Start Command:**
   ```
   npm start
   ```

4. **Port:** 3000 (or configure as needed)

5. **CORS Settings:**
   - The Vite config already includes CORS headers
   - Bolt should handle HTTPS automatically

## Browser Support

- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

**Note:** Voice Agent feature requires microphone permissions and may have limited support in some browsers.

## Security Notes

- API keys are stored in environment variables, never in code
- All data is stored locally in the browser (localStorage)
- No data is transmitted to third parties except Google Gemini API
- HTTPS is recommended for production deployments

## License

Private - All rights reserved

## Support

For issues or questions:
- Check the documentation
- Review environment variable configuration
- Ensure API key is valid and has sufficient quota

---

**Important:** This application does not provide legal advice. All generated documents and analyses should be reviewed by a qualified attorney before use in legal proceedings.
