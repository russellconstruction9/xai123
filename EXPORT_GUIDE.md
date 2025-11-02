# 📦 Export Guide for Bolt.new

## ✅ Project Status: READY TO EXPORT

Your CustodyX.AI project is fully configured and ready for Bolt.new deployment.

---

## 📁 Correct Folder Structure

**Use this structure (files in `src/` and `public/`):**

```
custodyx-ai/
├── public/
│   ├── icon.svg
│   ├── manifest.json
│   └── service-worker.js
│
├── src/
│   ├── components/      (23 component files)
│   ├── constants/       (3 constant files)
│   ├── services/        (1 service file)
│   ├── App.tsx
│   ├── main.tsx
│   ├── types.ts
│   └── constants.ts
│
├── .env.example          (CREATE THIS - see below)
├── .gitignore
├── index.html
├── package.json
├── README.md
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

**Note:** Old files at root (`App.tsx`, `components/`, etc.) can be ignored - use `src/` structure only.

---

## 🔧 Create `.env.example` File

**Manually create this file** (if it doesn't exist):

```bash
# Google Gemini API Key
# Get your API key from: https://makersuite.google.com/app/apikey
GEMINI_API_KEY=your_gemini_api_key_here
```

---

## 📤 Export Steps

### Step 1: Prepare ZIP File

**On Windows (PowerShell):**
```powershell
Compress-Archive -Path . -DestinationPath custodyx-ai-export.zip -Exclude @('node_modules','dist','build','.git','components','constants','services','App.tsx','constants.ts','types.ts','index.tsx','mockData.ts','metadata.json','xai123.code-workspace','.env.local')
```

**On Mac/Linux:**
```bash
zip -r custodyx-ai-export.zip . \
  -x "node_modules/*" \
  -x "dist/*" \
  -x "build/*" \
  -x ".git/*" \
  -x "components/*" \
  -x "constants/*" \
  -x "services/*" \
  -x "App.tsx" \
  -x "constants.ts" \
  -x "types.ts" \
  -x "index.tsx" \
  -x "mockData.ts" \
  -x "metadata.json" \
  -x ".env.local" \
  -x ".env"
```

### Step 2: Upload to Bolt.new

1. Go to **[bolt.new](https://bolt.new)**
2. Click **"Import"**
3. Select **"Upload ZIP"**
4. Choose `custodyx-ai-export.zip`
5. Wait for upload

### Step 3: Configure Environment

In Bolt.new settings → Environment Variables:

**Add:**
```
Key: GEMINI_API_KEY
Value: your_actual_api_key_here
```

**Get API key from:** https://makersuite.google.com/app/apikey

### Step 4: Build & Deploy

Bolt.new will automatically:
1. Run `npm install`
2. Run `npm run build`
3. Start with `npm start`

**Port:** 3000 (default)

---

## ✅ Verification Checklist

### Before Export:
- [x] All files in `src/` directory
- [x] `src/main.tsx` exists (entry point)
- [x] `src/App.tsx` exists (main app)
- [x] `public/` directory with assets
- [x] `package.json` has correct scripts
- [x] `vite.config.ts` configured
- [x] `index.html` points to `/src/main.tsx`
- [x] `.env.example` exists (create if needed)
- [x] No API keys hardcoded

### After Import to Bolt:
- [ ] Environment variable `GEMINI_API_KEY` is set
- [ ] `npm install` runs successfully
- [ ] `npm run build` completes without errors
- [ ] App starts on port 3000
- [ ] App loads in browser
- [ ] AI features work (test chat interface)

---

## 🔑 Key Configuration Files

### `package.json` Scripts:
```json
{
  "dev": "vite",
  "build": "tsc && vite build",
  "preview": "vite preview",
  "start": "vite preview --port 3000 --host"
}
```

### `vite.config.ts` - CORS Configuration:
✅ Already configured:
- CORS enabled
- Port 3000
- Host 0.0.0.0
- Environment variable loading

### `index.html` Entry Point:
```html
<script type="module" src="/src/main.tsx"></script>
```

---

## 📋 File Summary

### Essential Files (Must be in ZIP):
1. ✅ `src/main.tsx` - Entry point
2. ✅ `src/App.tsx` - Main app
3. ✅ `src/types.ts` - Type definitions
4. ✅ `src/constants.ts` - Main constants
5. ✅ `src/components/*` - All 23 components
6. ✅ `src/constants/*` - All 3 constant files
7. ✅ `src/services/geminiService.ts` - API service
8. ✅ `public/*` - All public assets
9. ✅ `package.json` - Dependencies
10. ✅ `vite.config.ts` - Build config
11. ✅ `tsconfig.json` - TypeScript config
12. ✅ `index.html` - HTML template
13. ✅ `.gitignore` - Git ignore rules
14. ✅ `README.md` - Documentation

### Optional Files:
- `BOLT_SETUP.md` - Setup guide
- `PROJECT_SUMMARY.md` - Project summary
- `EXPORT_GUIDE.md` - This guide

---

## 🚨 Troubleshooting

### If build fails:
1. Check `package.json` has all dependencies
2. Verify TypeScript configs are correct
3. Check for syntax errors in `src/` files

### If app doesn't start:
1. Verify `GEMINI_API_KEY` is set in Bolt
2. Check port 3000 is available
3. Review Bolt.new build logs

### If imports fail:
1. Verify all files are in `src/` directory
2. Check relative imports (use `./` or `../`)
3. Ensure `tsconfig.json` paths are correct

---

## 🎯 Quick Start Commands

**After importing to Bolt.new:**

1. **Set environment variable:**
   ```
   GEMINI_API_KEY=your_key_here
   ```

2. **Build should run automatically**

3. **Start should run automatically**

4. **Access app at:** Bolt.new provided URL

---

## 📝 Notes

- **Data Storage:** localStorage (no backend needed)
- **CORS:** Fully configured
- **HTTPS:** Automatic via Bolt.new
- **Port:** 3000 (configurable in Bolt)
- **Dependencies:** All in `package.json`

---

**🚀 Your project is ready! Create the ZIP and upload to Bolt.new!**

