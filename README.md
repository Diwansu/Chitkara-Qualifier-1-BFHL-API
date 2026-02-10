# Bajaj Finserv Backend Assignment

## 📋 Description

This project implements two REST API endpoints as part of the Bajaj Finserv Backend Qualifier Assignment:

- **POST /bfhl** - Handles Fibonacci series, Prime number filtering, LCM, HCF calculations, and AI-powered question answering
- **GET /health** - Health check endpoint

 Deployed URL

**Live API:** (https://chitkara-qualifier-1-bfhl-api.vercel.app/)

## 🛠️ Tech Stack

- **Runtime:** Node.js
- **AI Integration:** Google Gemini AI
- **Deployment:** Vercel
- **Environment:** dotenv

## 📡 API Endpoints

### 1. POST /bfhl

**Functionality:**
- Calculate Fibonacci series
- Filter prime numbers
- Calculate LCM (Lowest Common Multiple)
- Calculate HCF (Highest Common Factor)
- AI-powered question answering

**Request Examples:**

```json
// Fibonacci
{
  "fibonacci": 7
}

// Prime Numbers
{
  "prime": [2, 4, 7, 9, 11]
}

// LCM
{
  "lcm": [12, 18, 24]
}

// HCF
{
  "hcf": [24, 36, 60]
}

// AI Question
{
  "AI": "What is the capital of India?"
}
```

**Response Format:**

```json
{
  "is_success": true,
  "official_email": "your_email@chitkara.edu.in",
  "data": <result>
}
```

### 2. GET /health

**Response:**

```json
{
  "is_success": true,
  "official_email": "your_email@chitkara.edu.in"
}
```

## 🔧 Local Setup

1. **Clone the repository:**

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   Create a `.env` file:
   ```
   GEMINI_API_KEY=your_gemini_api_key
   OFFICIAL_EMAIL=your_email@chitkara.edu.in
   PORT=3000
   ```

4. **Run the server:**
   ```bash
   npm start
   # or for development
   npm run dev
   ```

5. **Test locally:**
   ```bash
   curl http://localhost:3000/health
   ```

## 🧪 Testing

### Test Health Endpoint:
```bash
curl http://localhost:3000/health
```

### Test BFHL Endpoint:

**Fibonacci:**
```bash
curl -X POST http://localhost:3000/bfhl \
  -H "Content-Type: application/json" \
  -d '{"fibonacci": 7}'
```

**Prime:**
```bash
curl -X POST http://localhost:3000/bfhl \
  -H "Content-Type: application/json" \
  -d '{"prime": [2,4,7,9,11]}'
```

**AI:**
```bash
curl -X POST http://localhost:3000/bfhl \
  -H "Content-Type: application/json" \
  -d '{"AI": "What is 2+2?"}'
```



## 🌐 Deployment

Deployed on Vercel with automatic CI/CD from GitHub.

### Environment Variables on Vercel:
- `GEMINI_API_KEY`
- `OFFICIAL_EMAIL`

## 📝 Assignment Requirements

✅ Strict API response structure  
✅ Correct HTTP status codes  
✅ Robust input validation  
✅ Graceful error handling  
✅ Security best practices  
✅ Public accessibility  
✅ Complete source code  

## 👨‍💻 Author

**Name:** [Diwanshu Baskota]  
**Email:** [diwanshu1618.be23@chitkarauniversity.edu.in]  
**University:** Chitkara University  
**Class:** 2027  

## 📄 License

This project is created for educational purposes as part of the Bajaj Finserv Backend Qualifier Assignment.

