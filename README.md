# MediNotes Pro 📋

An AI-powered healthcare consultation assistant that transforms doctor's notes into professional medical summaries, actionable next steps, and patient-friendly email communications.

## 🌟 Features

- **Professional Summaries**: Generate comprehensive medical record summaries from consultation notes
- **Action Items**: Clear next steps and follow-up actions for every consultation
- **Patient Communications**: Draft patient-friendly email communications automatically
- **Real-time Streaming**: Live AI-generated responses using OpenAI's GPT-5
- **Secure Authentication**: User authentication with Clerk
- **Modern UI**: Beautiful, responsive interface built with Next.js and Tailwind CSS

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 15.5.6 with React 19
- **Authentication**: Clerk (@clerk/nextjs)
- **Styling**: Tailwind CSS 4
- **UI Components**: 
  - React DatePicker for date selection
  - React Markdown for formatted output
  - Real-time streaming with @microsoft/fetch-event-source
- **Language**: TypeScript 5

### Backend
- **Framework**: FastAPI (Python)
- **AI**: OpenAI GPT-5 Nano
- **Authentication**: fastapi-clerk-auth
- **Data Validation**: Pydantic

## 📋 Prerequisites

- Node.js 20+ and npm/yarn
- Python 3.8+
- OpenAI API key
- Clerk account for authentication

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd healthcare-app
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

### 4. Environment Variables

Create a `.env.local` file in the root directory with the following variables:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
CLERK_JWKS_URL=your_clerk_jwks_url

# OpenAI
OPENAI_API_KEY=your_openai_api_key
```

### 5. Run the Development Server

```bash
vercel dev
```

This will start both the Next.js frontend and the Python API backend locally. The application will be available at [http://localhost:3000](http://localhost:3000)

## 📁 Project Structure

```
healthcare-app/
├── api/
│   └── index.py           # FastAPI backend with OpenAI integration
├── pages/
│   ├── _app.tsx          # Next.js app configuration
│   ├── _document.tsx     # Custom document structure
│   ├── index.tsx         # Landing page with features
│   └── product.tsx       # Main consultation form interface
├── public/               # Static assets
├── styles/
│   └── globals.css       # Global styles and Tailwind imports
├── eslint.config.mjs     # ESLint configuration
├── next.config.ts        # Next.js configuration
├── package.json          # Node dependencies
├── requirements.txt      # Python dependencies
├── tsconfig.json         # TypeScript configuration
└── README.md            # This file
```

## 🎯 Usage

1. **Sign In**: Use the Clerk authentication to sign in or create an account
2. **Access Consultation Form**: Click "Go to App" or "Open Consultation Assistant"
3. **Fill in Details**:
   - Enter patient's name
   - Select visit date
   - Add consultation notes
4. **Submit**: Click "Generate Summary" to get AI-powered output
5. **Review**: The system will generate:
   - Summary of visit for the doctor's records
   - Next steps for the doctor
   - Draft email to patient in patient-friendly language

## 🔒 Security & Privacy

- **Secure Authentication**: Clerk-based authentication with JWT tokens
- **Protected API Routes**: All endpoints require authentication
- **HTTPS Encryption**: Secure data transmission via Vercel

**Note**: This application is a demonstration project. For production use with actual patient data, additional security measures and compliance requirements (such as HIPAA) would need to be implemented, including Business Associate Agreements with third-party services, encrypted data storage, comprehensive audit logging, and proper data retention policies.

## 🚢 Deployment

The application is configured for deployment on Vercel:

```bash
vercel --prod
```

Make sure to set up environment variables in your Vercel project settings.

## 🧪 Development Scripts

```bash
vercel dev       # Start development server with both frontend and API
vercel --prod    # Deploy to production
npm run build    # Build for production (local)
npm run lint     # Run ESLint
```

## ⚠️ Disclaimer

This application is an AI-assisted tool designed to help healthcare professionals. All AI-generated content should be reviewed by qualified medical professionals before use. This tool does not replace professional medical judgment.

**Privacy Notice**: This is a demonstration project. It is not currently HIPAA compliant and should not be used with real patient data without implementing proper security controls, obtaining necessary Business Associate Agreements, and ensuring full compliance with healthcare data privacy regulations.
