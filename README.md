# English Booster

An AI-powered vocabulary learning platform built with Next.js, Firebase, and Gemini API. The application helps learners manage vocabulary, practice pronunciation, review words using spaced repetition, and generate learning content with AI assistance.

## Features

### Authentication

- Email & Password authentication using Firebase Auth
- User-specific vocabulary collections
- Personal learning progress tracking

### Vocabulary Management

- Create, edit, and delete vocabulary
- Organize words into custom decks
- Bulk import vocabulary via CSV upload
- Search and filter vocabulary

### AI Learning Assistant

- Generate word explanations
- Create example sentences
- Rewrite sentences with different difficulty levels
- Generate quizzes and practice exercises

### Pronunciation Support

- Free pronunciation audio from Dictionary API
- Audio URL caching to reduce repeated API requests
- AI-powered text-to-speech for sentences and paragraphs
- User-provided Gemini API key

### Spaced Repetition System

- Inspired by the Anki SM-2 algorithm
- Track review intervals
- Schedule future reviews automatically
- Learning progress dashboard

## Tech Stack

### Frontend

- Next.js 15
- React
- TypeScript
- Tailwind CSS

### Backend Services

- Firebase Authentication
- Cloud Firestore

### AI & External APIs

- Gemini API
- Dictionary API

### Deployment

- Vercel

## Architecture

```text
Next.js
│
├── Firebase Auth
├── Firestore
├── Dictionary API
└── Gemini API (User Key)
```

## Audio Strategy

### Single Word Pronunciation

```text
Word
 ↓
Firestore Cache
 ↓
Dictionary API
 ↓
Play Audio
```

The application stores audio URLs instead of audio files to minimize storage costs.

### Sentence Pronunciation

```text
Sentence
 ↓
Gemini TTS
 ↓
Play Audio
```

Gemini is only used for sentence-level pronunciation and AI-assisted learning features.

## CSV Import Format

Required columns:

```csv
word,meaning
```

Optional columns:

```csv
word,meaning,ipa,example,deck,pos
```

Example:

```csv
word,meaning,ipa,example,deck
implement,thực hiện,/ˈɪmplɪment/,"We implement new policies.",TOEIC
postpone,hoãn lại,/poʊstˈpoʊn/,"The meeting was postponed.",Business
```

## Environment Variables

```env
NEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=
NEXT_PUBLIC_FIREBASE_APP_ID=
```

Gemini API keys are managed by individual users through the application settings.

## Installation

Clone repository:

```bash
git clone <repository-url>
cd english-booster
```

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

## Future Improvements

- Speaking assessment
- TOEIC practice generator
- IELTS vocabulary packs
- Pronunciation scoring
- Learning streak tracking
- Dark mode
- Mobile responsive optimization

## Author

Ngoc Diep Au

Aspiring Software Developer transitioning from an education background to software engineering, with a focus on Java, Spring Boot, React, and AI-powered applications.
