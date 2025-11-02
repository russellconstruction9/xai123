# Bolt.new Setup Instructions

## Quick Start

1. **ZIP the entire project folder** (excluding `node_modules`, `.git`, and other ignored files)
2. **Upload to Bolt.new**:
   - Go to [Bolt.new](https://bolt.new)
   - Click "Import" → "Upload ZIP"
   - Select your project ZIP file

3. **Configure Environment Variables**:
   - In Bolt.new settings, add:
     - `GEMINI_API_KEY`: Your Google Gemini API key

4. **Build & Deploy**:
   - Bolt will automatically run `npm install` and `npm run build`
   - The app will be available at the provided Bolt.new URL

## Project Structure

```
custodyx-ai/
├── public/
│   ├── icon.svg
│   ├── manifest.json
│   └── service-worker.js
├── src/
│   ├── components/        # All React components (23 files)
│   ├── constants/         # Constants and AI prompts
│   ├── services/          # Gemini API service
│   ├── App.tsx            # Main app component
│   ├── main.tsx           # Entry point
│   ├── types.ts           # TypeScript definitions
│   └── constants.ts       # Main constants
├── .env.example           # Environment template
├── .gitignore
├── index.html
├── package.json
├── README.md
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

## Environment Variables Required

```
GEMINI_API_KEY=your_google_gemini_api_key_here
```

Get your API key from: https://makersuite.google.com/app/apikey

## Build Commands (Bolt Configuration)

**Install Command:**
```bash
npm install
```

**Build Command:**
```bash
npm run build
```

**Start Command:**
```bash
npm start
```

**Port:** 3000

## CORS Configuration

The project is already configured for CORS:
- `vite.config.ts` includes CORS headers
- Server configured to accept requests from any origin
- HTTPS is handled by Bolt.new automatically

## Key Files

### Entry Point
- `src/main.tsx` - React app entry point

### Main Application
- `src/App.tsx` - Main app component with state management

### Components (in `src/components/`)
- `AgentChat.tsx` - Voice agent interface
- `BehavioralInsights.tsx` - Deep analysis component
- `Calendar.tsx` & `CalendarView.tsx` - Calendar components
- `ChatInterface.tsx` - Incident logging chat
- `Dashboard.tsx` - Main dashboard
- `DocumentLibrary.tsx` - Document management
- `EvidencePackageBuilder.tsx` - Evidence package builder
- `Header.tsx` & `Sidebar.tsx` - Navigation
- `IncidentCard.tsx` & `IncidentTimeline.tsx` - Incident display
- `LandingPage.tsx` - Landing page
- `LegalAssistant.tsx` - Legal AI assistant
- `PatternAnalysis.tsx` - Pattern analysis
- `UserProfile.tsx` - User profile
- `icons.tsx` - Icon components
- Plus modals and other components

### Services
- `src/services/geminiService.ts` - Google Gemini API integration

### Constants
- `src/constants.ts` - Main constants and prompts
- `src/constants/legalPrompts.ts` - Legal assistant prompts
- `src/constants/behavioralPrompts.ts` - Behavioral analysis prompts
- `src/constants/legalContext.ts` - Indiana legal context

## Data Storage

- Uses **localStorage** for all data persistence
- No backend database required
- Data stored locally in browser

## Features

✅ AI-Powered Incident Logging
✅ Pattern Analysis
✅ Deep Behavioral Analysis (Pro tier)
✅ Legal Document Drafting
✅ Evidence Package Builder
✅ Voice Agent (Pro tier)
✅ Calendar & Timeline Views
✅ Document Library
✅ PWA Support

## Subscription Tiers

- **Free:** 50,000 tokens/month
- **Plus:** 500,000 tokens/month
- **Pro:** 5,000,000 tokens/month

## Troubleshooting

### If app doesn't start:
1. Check environment variables are set in Bolt.new
2. Verify `GEMINI_API_KEY` is valid
3. Check build logs in Bolt.new console

### If API calls fail:
1. Verify API key has sufficient quota
2. Check CORS headers in network tab
3. Ensure API key is correctly set in environment

### If imports fail:
- All imports use relative paths (`./` or `../`)
- TypeScript path aliases configured for `@/*` → `./src/*`

## Next Steps After Deployment

1. Test the app functionality
2. Configure custom domain (if needed)
3. Set up monitoring/analytics (optional)
4. Review API usage in Google Cloud Console

