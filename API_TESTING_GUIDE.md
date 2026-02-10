# 🧪 API Testing Guide - Bajaj Finserv Assignment

## 📋 Project Information

- **Project Name:** Bajaj Finserv Health API
- **GitHub Repository:** https://github.com/Diwansu/Chitkara-Qualifier-1-BFHL-API.git
- **Live API Base URL:** https://bajajfinserv-assignment-nu.vercel.app
- **Email:** diwanshu1618.be23@chitkarauniversity.edu.in
- **Date:** February 10, 2026

---

## 🌐 Base URL

```
https://bajajfinserv-assignment-nu.vercel.app
```

---

## 📡 API Endpoints

### 1. Root Endpoint - API Documentation

**Description:** Returns API information and usage guide

**Method:** `GET`

**Endpoint:** `/`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/

**Parameters:** None

**Request Body:** None

**Expected Response:**
```json
{
  "message": "Bajaj Finserv Health API",
  "status": "Running",
  "endpoints": {
    "health": "GET /health",
    "bfhl": "POST /bfhl"
  },
  "usage": {
    "fibonacci": "POST /bfhl with body: {\"fibonacci\": 7}",
    "prime": "POST /bfhl with body: {\"prime\": [2,4,7,9,11]}",
    "lcm": "POST /bfhl with body: {\"lcm\": [12,18,24]}",
    "hcf": "POST /bfhl with body: {\"hcf\": [24,36,60]}",
    "ai": "POST /bfhl with body: {\"AI\": \"Your question here\"}"
  }
}
```

**Status Code:** `200 OK`

**Test in Browser:** Simply open https://bajajfinserv-assignment-nu.vercel.app/

---

### 2. Health Check Endpoint

**Description:** Verifies API is running and returns official email

**Method:** `GET`

**Endpoint:** `/health`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/health

**Parameters:** None

**Request Body:** None

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in"
}
```

**Status Code:** `200 OK`

**Test in Browser:** Simply open https://bajajfinserv-assignment-nu.vercel.app/health

**cURL Command:**
```bash
curl https://bajajfinserv-assignment-nu.vercel.app/health
```

---

### 3. Fibonacci Sequence Generator

**Description:** Generates Fibonacci sequence up to nth term

**Method:** `POST`

**Endpoint:** `/bfhl`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/bfhl

**Content-Type:** `application/json`

**Request Body:**
```json
{
  "fibonacci": 7
}
```

**Parameters:**
- `fibonacci` (Integer): Number of terms in Fibonacci sequence (must be non-negative)

**Example Input Values:**
- `5` → Returns first 5 Fibonacci numbers
- `7` → Returns first 7 Fibonacci numbers
- `10` → Returns first 10 Fibonacci numbers

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": [0, 1, 1, 2, 3, 5, 8]
}
```

**Status Code:** `200 OK`

**cURL Command:**
```bash
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d "{\"fibonacci\": 7}"
```

---

### 4. Prime Number Filter

**Description:** Filters and returns only prime numbers from given array

**Method:** `POST`

**Endpoint:** `/bfhl`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/bfhl

**Content-Type:** `application/json`

**Request Body:**
```json
{
  "prime": [2, 4, 7, 9, 11]
}
```

**Parameters:**
- `prime` (Array of Integers): Array of numbers to filter for primes

**Example Input Values:**
- `[2, 4, 7, 9, 11]` → Returns `[2, 7, 11]`
- `[1, 2, 3, 4, 5]` → Returns `[2, 3, 5]`
- `[10, 13, 15, 17, 20]` → Returns `[13, 17]`

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": [2, 7, 11]
}
```

**Status Code:** `200 OK`

**cURL Command:**
```bash
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d "{\"prime\": [2,4,7,9,11]}"
```

---

### 5. LCM Calculator

**Description:** Calculates Lowest Common Multiple (LCM) of given numbers

**Method:** `POST`

**Endpoint:** `/bfhl`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/bfhl

**Content-Type:** `application/json`

**Request Body:**
```json
{
  "lcm": [12, 18, 24]
}
```

**Parameters:**
- `lcm` (Array of Integers): Array of numbers to calculate LCM (must be non-empty)

**Example Input Values:**
- `[12, 18, 24]` → Returns `72`
- `[4, 6]` → Returns `12`
- `[15, 20, 25]` → Returns `300`

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": 72
}
```

**Status Code:** `200 OK`

**cURL Command:**
```bash
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d "{\"lcm\": [12,18,24]}"
```

---

### 6. HCF/GCD Calculator

**Description:** Calculates Highest Common Factor (HCF/GCD) of given numbers

**Method:** `POST`

**Endpoint:** `/bfhl`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/bfhl

**Content-Type:** `application/json`

**Request Body:**
```json
{
  "hcf": [24, 36, 60]
}
```

**Parameters:**
- `hcf` (Array of Integers): Array of numbers to calculate HCF (must be non-empty)

**Example Input Values:**
- `[24, 36, 60]` → Returns `12`
- `[8, 12]` → Returns `4`
- `[15, 25, 35]` → Returns `5`

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": 12
}
```

**Status Code:** `200 OK`

**cURL Command:**
```bash
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d "{\"hcf\": [24,36,60]}"
```

---

### 7. AI Question Answering (Google Gemini Integration)

**Description:** Uses Google Gemini AI to answer questions

**Method:** `POST`

**Endpoint:** `/bfhl`

**Full URL:** https://bajajfinserv-assignment-nu.vercel.app/bfhl

**Content-Type:** `application/json`

**Request Body:**
```json
{
  "AI": "What is the capital of India?"
}
```

**Parameters:**
- `AI` (String): Question to ask the AI (must be non-empty string)

**Example Input Values:**
- `"What is the capital of India?"` → Returns AI-generated answer
- `"What is 2+2?"` → Returns `"2 + 2 = 4"`
- `"Explain quantum computing"` → Returns AI explanation

**Expected Response:**
```json
{
  "is_success": true,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": "The capital of India is **New Delhi**."
}
```

**Status Code:** `200 OK`

**Note:** Response may take 2-5 seconds as it queries Google Gemini AI

**cURL Command:**
```bash
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d "{\"AI\": \"What is the capital of India?\"}"
```

---

## ❌ Error Handling

### Error Response Format

All errors return this structure:
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "Error message description"
}
```

### Common Error Cases

#### 1. Empty Request Body
**Request:**
```json
{}
```

**Response:**
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "At least one input is required"
}
```
**Status Code:** `400 Bad Request`

---

#### 2. Invalid Fibonacci Input
**Request:**
```json
{
  "fibonacci": -5
}
```

**Response:**
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "Fibonacci input must be a non-negative integer"
}
```
**Status Code:** `400 Bad Request`

---

#### 3. Invalid Prime Input
**Request:**
```json
{
  "prime": "not an array"
}
```

**Response:**
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "Prime input must be an array"
}
```
**Status Code:** `400 Bad Request`

---

#### 4. Empty Array for LCM/HCF
**Request:**
```json
{
  "lcm": []
}
```

**Response:**
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "LCM input must be a non-empty array"
}
```
**Status Code:** `400 Bad Request`

---

#### 5. Invalid AI Input
**Request:**
```json
{
  "AI": ""
}
```

**Response:**
```json
{
  "is_success": false,
  "official_email": "diwanshu1618.be23@chitkarauniversity.edu.in",
  "data": null,
  "error": "AI input must be a non-empty string"
}
```
**Status Code:** `400 Bad Request`

---

## 🧪 Testing Tools

### Option 1: Bruno (Recommended)
1. Open Bruno
2. Create new collection
3. Add requests with URLs and bodies from this guide
4. Click "Send Request"

### Option 2: Postman
1. Open Postman
2. Create new request
3. Set method (GET/POST)
4. Enter URL
5. For POST: Go to Body → raw → JSON and paste request body
6. Click Send

### Option 3: cURL (Terminal)
Use the cURL commands provided for each endpoint above

### Option 4: Browser
For GET requests (Root and Health), simply open the URL in your browser

---

## ✅ Complete Test Checklist

Use this checklist to verify all endpoints:

- [ ] **Root Endpoint** - GET `/` - Shows API documentation
- [ ] **Health Check** - GET `/health` - Returns email and success
- [ ] **Fibonacci** - POST `/bfhl` with `{"fibonacci": 7}` - Returns sequence
- [ ] **Prime** - POST `/bfhl` with `{"prime": [2,4,7,9,11]}` - Returns `[2,7,11]`
- [ ] **LCM** - POST `/bfhl` with `{"lcm": [12,18,24]}` - Returns `72`
- [ ] **HCF** - POST `/bfhl` with `{"hcf": [24,36,60]}` - Returns `12`
- [ ] **AI** - POST `/bfhl` with `{"AI": "What is the capital of India?"}` - Returns answer
- [ ] **Error Handling** - POST `/bfhl` with `{}` - Returns 400 error

---

## 📊 Expected Success Rate

✅ **All 8 tests should pass with `"is_success": true"`**

✅ **Status codes:** 200 for success, 400 for validation errors, 500 for server errors

✅ **Response structure:** All successful responses contain `is_success`, `official_email`, and `data`

---

## 🚀 Quick Test Commands

Run these commands in your terminal to test all endpoints quickly:

```bash
# 1. Health Check
curl https://bajajfinserv-assignment-nu.vercel.app/health

# 2. Fibonacci
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl -H "Content-Type: application/json" -d "{\"fibonacci\": 7}"

# 3. Prime
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl -H "Content-Type: application/json" -d "{\"prime\": [2,4,7,9,11]}"

# 4. LCM
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl -H "Content-Type: application/json" -d "{\"lcm\": [12,18,24]}"

# 5. HCF
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl -H "Content-Type: application/json" -d "{\"hcf\": [24,36,60]}"

# 6. AI
curl -X POST https://bajajfinserv-assignment-nu.vercel.app/bfhl -H "Content-Type: application/json" -d "{\"AI\": \"What is the capital of India?\"}"
```

---

## 📝 Notes

- All POST requests must include `Content-Type: application/json` header
- AI endpoint may take 2-5 seconds to respond
- Empty request bodies will return 400 error (this is correct behavior)
- All responses are in JSON format
- API is deployed on Vercel with automatic CI/CD from GitHub

---

## 🎯 Assignment Requirements Met

✅ Strict API response structure  
✅ Correct HTTP status codes (200, 400, 500)  
✅ Robust input validation  
✅ Graceful error handling (no crashes)  
✅ Security best practices (environment variables)  
✅ Public accessibility  
✅ Complete source code on GitHub  
✅ Google Gemini AI integration  
✅ All 5 operations working (Fibonacci, Prime, LCM, HCF, AI)  

---

**API Status:** ✅ **FULLY OPERATIONAL**

**Last Updated:** February 10, 2026
