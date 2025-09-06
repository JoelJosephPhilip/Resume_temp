# CareerForge AI

An AI-powered career development platform that helps users create professional resumes, cover letters, and prepare for job applications using Google's Gemini AI.

## Features

- 🤖 **AI Resume Builder** - Create professional resumes with AI assistance
- 📝 **Cover Letter Generator** - Generate tailored cover letters for specific jobs
- 📊 **ATS Resume Analyzer** - Analyze resume for ATS compliance with scoring
- 🔧 **Fix My Resume** - Improve existing resumes with AI suggestions
- 🎯 **JD-Resume Matcher** - Compare resumes to job descriptions
- 💬 **AI Interview Coach** - Practice with personalized interview questions
- 🛤️ **Career Path Recommendations** - Get skill gap analysis and career advice
- 🌍 **Multilingual Support** - Generate resumes in different languages
- ☁️ **Google Drive Integration** - Save documents directly to Google Drive

## Tech Stack

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS
- **AI**: Google Genkit, Gemini 2.0 Flash
- **Authentication**: NextAuth.js with Google OAuth
- **Database**: Firebase Firestore
- **UI Components**: Radix UI, shadcn/ui
- **Styling**: Tailwind CSS with custom theme

## Prerequisites

Before running this project, you'll need:

1. **Node.js** (version 18 or higher)
2. **Google Cloud Project** with the following APIs enabled:
   - Google AI API (for Gemini)
   - Google Drive API
3. **Firebase Project** for authentication and database
4. **Google OAuth Credentials**

## Setup Instructions

### 1. Clone and Install Dependencies

```bash
# Navigate to the project directory
cd careerforge-ai

# Install dependencies
npm install
```

### 2. Environment Variables

Copy the example environment file and fill in your credentials:

```bash
cp env.example .env.local
```

Fill in the following environment variables in `.env.local`:

#### Google AI API Key
1. Go to [Google AI Studio](https://aistudio.google.com/)
2. Create a new API key
3. Add it to `GOOGLE_AI_API_KEY`

#### Google OAuth Credentials
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable Google+ API and Google Drive API
4. Go to "Credentials" → "Create Credentials" → "OAuth 2.0 Client IDs"
5. Add authorized redirect URIs:
   - `http://localhost:3000/api/auth/callback/google`
   - `https://yourdomain.com/api/auth/callback/google` (for production)
6. Add the Client ID and Secret to your `.env.local`

#### Firebase Configuration
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or select existing one
3. Enable Authentication (Google provider)
4. Enable Firestore Database
5. Go to Project Settings → General → Your apps
6. Add a web app and copy the config values to your `.env.local`

#### NextAuth Secret
Generate a random secret:
```bash
openssl rand -base64 32
```

### 3. Run the Development Server

```bash
npm run dev
```

The application will be available at `http://localhost:3000`

### 4. Run Genkit (Optional)

To run the Genkit development server for AI flow testing:

```bash
npm run genkit
```

## Project Structure

```
src/
├── ai/                    # AI flows and Genkit configuration
│   ├── flows/            # Individual AI feature implementations
│   ├── genkit.ts         # Genkit configuration
│   └── schemas/          # Zod schemas for validation
├── app/                  # Next.js app router pages
│   ├── (auth)/          # Authentication pages
│   ├── dashboard/       # Main application dashboard
│   ├── api/             # API routes
│   └── actions/         # Server actions
├── components/          # Reusable UI components
│   └── ui/             # shadcn/ui components
├── hooks/              # Custom React hooks
└── lib/                # Utility functions and configurations
```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint
- `npm run genkit` - Start Genkit development server

## API Keys Setup Guide

### Google AI API Key
1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Sign in with your Google account
3. Click "Get API Key" → "Create API Key"
4. Copy the generated key to your `.env.local`

### Firebase Setup
1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Authentication → Sign-in method → Google
3. Enable Firestore Database
4. Go to Project Settings → General → Add app → Web
5. Copy the config object values to your environment variables

### Google OAuth Setup
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create/select a project
3. Enable APIs: Google+ API, Google Drive API
4. Go to Credentials → Create Credentials → OAuth 2.0 Client ID
5. Set application type to "Web application"
6. Add authorized redirect URIs for your domain
7. Copy Client ID and Secret to your `.env.local`

## Troubleshooting

### Common Issues

1. **"Module not found" errors**: Run `npm install` to ensure all dependencies are installed
2. **Authentication errors**: Verify your Google OAuth credentials and redirect URIs
3. **AI API errors**: Check your Google AI API key and ensure the API is enabled
4. **Firebase errors**: Verify your Firebase configuration and ensure Firestore is enabled

### Getting Help

If you encounter issues:
1. Check the browser console for error messages
2. Verify all environment variables are set correctly
3. Ensure all required APIs are enabled in Google Cloud Console
4. Check that Firebase Authentication and Firestore are properly configured

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.
