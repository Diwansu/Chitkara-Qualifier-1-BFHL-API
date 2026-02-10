# 🚀 Deployment Instructions

## ✅ What's Been Completed

1. ✅ Complete API implementation (server.js)
2. ✅ All configuration files created
3. ✅ Code pushed to GitHub
4. ✅ Ready for deployment

## 🔑 STEP 1: Get Your Google Gemini API Key (5 minutes)

### Follow these exact steps:

1. **Open your browser** and go to: https://aistudio.google.com
2. **Sign in** with your Google account
3. **Click** "Get API Key" (top right corner)
4. **Click** "Create API key in new project"
5. **Copy** the API key (it looks like: `AIzaSy...`)
6. **Keep it safe** - you'll need it in Step 3

---

## 📝 STEP 2: Update Your Email

1. **Open** the `.env` file in this project
2. **Replace** `your_email@chitkara.edu.in` with **your actual Chitkara email**
3. **Save** the file

---

## 🔐 STEP 3: Add API Key to .env File

1. **Open** the `.env` file
2. **Replace** `your_api_key_here` with the API key you got from Step 1
3. **Save** the file

Your `.env` should look like:
```
GEMINI_API_KEY=AIzaSyC9XnzHq...your_actual_key
OFFICIAL_EMAIL=yourname@chitkara.edu.in
PORT=3000
```

---

## 🧪 STEP 4: Test Locally (IMPORTANT!)

### 4.1: Start the Server

Open terminal in this project folder and run:

```bash
npm start
```

You should see: `Server running on port 3000`

### 4.2: Test Health Endpoint

**Open a NEW terminal** and run:

```bash
curl http://localhost:3000/health
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in"
}
```

### 4.3: Test BFHL Endpoint

**Test Fibonacci:**
```bash
curl -X POST http://localhost:3000/bfhl -H "Content-Type: application/json" -d "{\"fibonacci\": 7}"
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in",
  "data": [0, 1, 1, 2, 3, 5, 8]
}
```

**Test Prime:**
```bash
curl -X POST http://localhost:3000/bfhl -H "Content-Type: application/json" -d "{\"prime\": [2,4,7,9,11]}"
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in",
  "data": [2, 7, 11]
}
```

**Test LCM:**
```bash
curl -X POST http://localhost:3000/bfhl -H "Content-Type: application/json" -d "{\"lcm\": [12,18,24]}"
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in",
  "data": 72
}
```

**Test HCF:**
```bash
curl -X POST http://localhost:3000/bfhl -H "Content-Type: application/json" -d "{\"hcf\": [24,36,60]}"
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in",
  "data": 12
}
```

**Test AI:**
```bash
curl -X POST http://localhost:3000/bfhl -H "Content-Type: application/json" -d "{\"AI\": \"What is the capital of India?\"}"
```

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "yourname@chitkara.edu.in",
  "data": "New Delhi"
}
```

---

## 🌐 STEP 5: Deploy to Vercel (10 minutes)

### 5.1: Create Vercel Account

1. Go to: https://vercel.com
2. Click "Sign Up"
3. Choose "Continue with GitHub"
4. Authorize Vercel to access your GitHub

### 5.2: Import Project

1. Click "New Project" (or "Add New" → "Project")
2. Find `bajajfinserv-assignment-` in the list
3. Click "Import"

### 5.3: Configure Project

**Framework Preset:** Other (leave as is)

**Build Settings:** (leave default)

### 5.4: Add Environment Variables

**CRITICAL STEP:**

Click "Environment Variables" and add these **TWO** variables:

1. **Key:** `GEMINI_API_KEY`
   **Value:** [Paste your API key from Step 1]

2. **Key:** `OFFICIAL_EMAIL`
   **Value:** [Your Chitkara email]

### 5.5: Deploy

1. Click "Deploy"
2. Wait 2-3 minutes (Vercel will build and deploy)
3. You'll see "Congratulations!" when done
4. **Copy your deployment URL** (looks like: `https://bajajfinserv-assignment-xyz.vercel.app`)

---

## ✅ STEP 6: Test Deployed API

Replace `YOUR_VERCEL_URL` with your actual Vercel URL:

### Test Health:
```bash
curl https://YOUR_VERCEL_URL/health
```

### Test BFHL (Fibonacci):
```bash
curl -X POST https://YOUR_VERCEL_URL/bfhl -H "Content-Type: application/json" -d "{\"fibonacci\": 7}"
```

### Test BFHL (AI):
```bash
curl -X POST https://YOUR_VERCEL_URL/bfhl -H "Content-Type: application/json" -d "{\"AI\": \"What is 2+2?\"}"
```

**All tests should return `is_success: true`**

---

## 📤 STEP 7: Submit Your Assignment

### What to Submit:

1. **GitHub Repository URL:**
   ```
   https://github.com/ManmeetSingh777/bajajfinserv-assignment-
   ```

2. **Vercel Deployment URL:**
   ```
   https://YOUR_PROJECT_NAME.vercel.app
   ```

3. **Your Email:**
   ```
   your_email@chitkara.edu.in
   ```

### Submission Format:

```
Name: [Your Name]
Roll Number: [Your Roll Number]
Official Email: your_email@chitkara.edu.in

GitHub Repository: https://github.com/ManmeetSingh777/bajajfinserv-assignment-
Deployed API URL: https://your-project.vercel.app

Test Endpoints:
- Health Check: https://your-project.vercel.app/health
- BFHL Endpoint: https://your-project.vercel.app/bfhl

All endpoints tested and working successfully.
```

---

## 🔍 Verification Checklist

Before submitting, verify:

- [ ] Health endpoint returns 200 status with your email
- [ ] BFHL endpoint handles Fibonacci correctly
- [ ] BFHL endpoint handles Prime numbers correctly
- [ ] BFHL endpoint handles LCM correctly
- [ ] BFHL endpoint handles HCF correctly
- [ ] BFHL endpoint handles AI questions correctly
- [ ] All responses have correct structure (`is_success`, `official_email`, `data`)
- [ ] GitHub repository is PUBLIC
- [ ] README.md updated with Vercel URL
- [ ] No errors in Vercel deployment logs

---

## 🚨 Troubleshooting

### Issue: "AI service unavailable"
**Solution:** Check that your GEMINI_API_KEY is correct in Vercel environment variables

### Issue: "Cannot find module"
**Solution:** Make sure all dependencies are in package.json (they should be)

### Issue: "404 Not Found on Vercel"
**Solution:** Check that vercel.json exists and is correct (it should be)

### Issue: "Email showing as undefined"
**Solution:** Make sure OFFICIAL_EMAIL is set in Vercel environment variables

### Issue: "Build failed on Vercel"
**Solution:** 
1. Check Vercel build logs for specific error
2. Make sure package.json has all dependencies
3. Verify vercel.json configuration

---

## 📞 Need Help?

1. Check Vercel deployment logs (click on your deployment → "Logs")
2. Test locally first before deploying
3. Verify all environment variables are set correctly
4. Make sure your API key is valid at https://aistudio.google.com

---

## 🎉 Success Criteria

Your assignment is complete when:

✅ GET /health returns correct response  
✅ POST /bfhl handles all 5 operations (fibonacci, prime, lcm, hcf, AI)  
✅ Proper error handling for invalid inputs  
✅ Correct HTTP status codes (200, 400, 500)  
✅ GitHub repo is public with complete code  
✅ Vercel deployment is live and accessible  
✅ All test cases pass  

---

**Good luck! You got this! 🚀**
