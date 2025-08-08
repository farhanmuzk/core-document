## 🎯 Project Overview

**Syntax Playground** adalah platform interaktif yang memungkinkan developer mengekspresikan emosi dan pemikiran mereka melalui format kode yang familiar. Target: membuat tools yang viral, shareable, dan memiliki identitas kuat tanpa bergantung pada personal branding.

### Core Value Proposition

- Format ekspresi kreatif berbasis metafora teknologi
- Pengalaman interaktif yang mindblowing
- Output yang instantly shareable dan relatable
- Modular dan scalable architecture

## 🏗️ Technical Architecture

### Stack Decision

```
Frontend: Next.js 14 (App Router)
Styling: Tailwind CSS + shadcn/ui
Database: Supabase (PostgreSQL)
Auth: Supabase Auth
Storage: Supabase Storage (untuk image exports)
Deployment: Vercel
Analytics: Vercel Analytics
```

### Project Structure

```
syntax-playground/
├── app/                          # Next.js App Router
│   ├── (auth)/                  # Route groups
│   ├── formats/[slug]/          # Dynamic format pages
│   ├── inject/                  # Random format generator
│   ├── gallery/                 # Public showcase
│   └── api/                     # API routes
├── components/
│   ├── ui/                      # shadcn/ui components
│   ├── formats/                 # Format renderers
│   ├── generators/              # Content generators
│   └── exports/                 # Export utilities
├── lib/
│   ├── formats/                 # Format definitions
│   ├── prompts/                 # Prompt systems
│   ├── generators/              # Content generation logic
│   ├── exports/                 # Export handlers
│   └── utils/                   # Utilities
├── types/                       # TypeScript definitions
├── public/                      # Static assets
└── supabase/                    # Database schemas & migrations
```

## 🧩 Core Features - MVP v0.1

### 1. Format Generator System

#### Format Definition Structure

```typescript
// lib/formats/types.ts
interface FormatDefinition {
  id: string
  name: string
  description: string
  category: 'reflective' | 'absurd' | 'technical-poetic' | 'experimental'
  icon: string
  prompts: PromptField[]
  renderer: string // Component name
  previewImage: string
  metadata: {
    difficulty: 1 | 2 | 3
    estimatedTime: string
    tags: string[]
  }
}

interface PromptField {
  id: string
  label: string
  type: 'text' | 'textarea' | 'select' | 'slider' | 'checkbox'
  placeholder?: string
  options?: string[] // for select type
  validation?: {
    required?: boolean
    minLength?: number
    maxLength?: number
  }
}
```

#### Built-in Formats (MVP)

```typescript
// lib/formats/definitions/
├── cli-kehidupan.ts
├── refactor-diri.ts
├── error-eksistensial.ts
├── unit-test-emosi.ts
└── env-kehidupan.ts
```

### 2. Interactive Builder Component

```typescript
// components/generators/FormatBuilder.tsx
interface FormatBuilderProps {
  format: FormatDefinition
  onPreview: (data: FormData) => void
  onExport: (data: FormData, exportType: ExportType) => void
}

// Features:
// - Real-time preview
// - Form validation
// - Auto-save drafts
// - Export options (PNG, IG Story, Text)
```

### 3. Visual Renderer System

```typescript
// components/formats/renderers/
├── CliRenderer.tsx        # Terminal-style output
├── ErrorRenderer.tsx      # Error box styling
├── CodeRenderer.tsx       # Code block formatting
└── EnvRenderer.tsx        # .env file styling

// Each renderer:
// - Accepts structured data
// - Returns styled JSX
// - Supports theme switching
// - Exportable to image
```

### 4. Export Engine

```typescript
// lib/exports/types.ts
interface ExportOptions {
  format: 'png' | 'jpg' | 'svg'
  size: 'square' | 'story' | 'post' | 'custom'
  theme: 'light' | 'dark'
  quality: number
}

// lib/exports/image-generator.ts
// - Uses html-to-image or similar
// - Handles different aspect ratios
// - Optimized for social media
```

## 🎲 Inject Me Feature

### Random Content Generator

```typescript
// lib/generators/inject-engine.ts
interface InjectResult {
  format: FormatDefinition
  prompt: string
  prefill?: Partial<FormData>
}

// Algorithm:
// 1. Pick random format based on weights
// 2. Generate contextual prompt
// 3. Optional: prefill some fields
// 4. Return complete setup for immediate use
```

## 🗄️ Database Schema

```sql
-- supabase/migrations/001_initial_schema.sql

-- User content storage
CREATE TABLE user_contents (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  user_id UUID REFERENCES auth.users(id) ON DELETE CASCADE,
  format_id VARCHAR(50) NOT NULL,
  title VARCHAR(200),
  content_data JSONB NOT NULL,
  rendered_output TEXT,
  is_public BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Analytics tracking
CREATE TABLE content_interactions (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  content_id UUID REFERENCES user_contents(id) ON DELETE CASCADE,
  interaction_type VARCHAR(50) NOT NULL, -- 'view', 'share', 'remix'
  user_id UUID REFERENCES auth.users(id) ON DELETE SET NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Format usage statistics
CREATE TABLE format_stats (
  format_id VARCHAR(50) PRIMARY KEY,
  usage_count INTEGER DEFAULT 0,
  last_used TIMESTAMP WITH TIME ZONE,
  avg_completion_time INTERVAL
);
```

## 🎨 UI/UX Components

### Key Components List

```typescript
// components/ui/ (shadcn/ui based)
├── FormatCard.tsx           # Format selection cards
├── PromptForm.tsx           # Dynamic form generator
├── PreviewPanel.tsx         # Live preview container
├── ExportDialog.tsx         # Export options modal
├── GalleryGrid.tsx          # Public content grid
└── InjectButton.tsx         # Random generator trigger

// Design tokens:
// - Monospace fonts: JetBrains Mono, Fira Code
// - Dark/light theme support
// - Terminal-inspired color palette
// - Glassmorphism elements for modernity
```

## 🔄 User Flow Implementation

### Core User Journeys

#### 1. Quick Creation Flow

```
Landing → Pick Format → Fill Prompts → Preview → Export → Share
```

#### 2. Inject Me Flow

```
Landing → Inject Me → Random Setup → Tweak → Export → Share
```

#### 3. Gallery Exploration

```
Landing → Gallery → View Content → Remix → Create Own → Export
```

## 🚀 Implementation Phases

### Phase 1 (Week 1-2): Core MVP

- [ ] Project setup with Next.js 14
- [ ] Basic format system (3 formats: CLI, Error, .env)
- [ ] Prompt form generator
- [ ] Simple renderer components
- [ ] PNG export functionality

### Phase 2 (Week 3-4): Enhanced UX

- [ ] Inject Me random generator
- [ ] Gallery system (public showcase)
- [ ] User authentication (Supabase)
- [ ] Content saving/loading
- [ ] Multiple export formats

### Phase 3 (Week 5-6): Polish & Distribution

- [ ] Advanced renderers with animations
- [ ] SEO optimization
- [ ] Analytics integration
- [ ] Social media optimization
- [ ] Performance optimization

## 📊 Success Metrics & Tracking

### Key Performance Indicators

```typescript
// Analytics events to track:
interface AnalyticsEvent {
  'format_selected': { formatId: string }
  'content_generated': { formatId: string, completionTime: number }
  'content_exported': { formatId: string, exportType: string }
  'inject_me_used': { formatId: string }
  'gallery_content_viewed': { contentId: string }
  'content_remixed': { originalId: string, formatId: string }
}

// Success metrics:
// - Content creation completion rate (>60%)
// - Export rate (>40% of completed content)
// - Return user rate (>30% in 7 days)
// - Social media shares (trackable via UTM)
```

## 🔧 Development Setup

### Environment Configuration

```env
# .env.local
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Quick Start Commands

```bash
# Setup
npx create-next-app@latest syntax-playground --typescript --tailwind --app
cd syntax-playground
npm install @supabase/supabase-js @supabase/auth-helpers-nextjs
npm install @radix-ui/react-* class-variance-authority clsx tailwind-merge
npm install html-to-image lucide-react

# Development
npm run dev

# Database
npx supabase init
npx supabase start
npx supabase db reset
```

## 📦 Third-party Integrations

### Image Export

- **html-to-image**: Convert React components to images
- **canvas-confetti**: Celebration effects on export

### Analytics

- **Vercel Analytics**: Basic usage tracking
- **PostHog** (future): Advanced user behavior analysis

### Social Features

- **Open Graph**: Rich social media previews
- **Twitter Cards**: Enhanced Twitter sharing

## 🔄 Content Distribution Strategy

### Built-in Sharing Features

```typescript
// lib/sharing/social-export.ts
interface SocialExport {
  platform: 'instagram' | 'twitter' | 'linkedin' | 'facebook'
  format: 'post' | 'story'
  optimizedSize: { width: number, height: number }
  hashtags: string[]
  suggestedCaption: string
}
```

### Viral Mechanics

- **Watermark system**: Subtle branding on exports
- **UTM tracking**: Monitor shared content performance
- **Referral system**: Track user acquisition from shares

## 🛡️ Security & Privacy

### Data Protection

- **Anonymous mode**: Create without account
- **GDPR compliance**: Easy data export/deletion
- **Content moderation**: Flag system for inappropriate content
- **Rate limiting**: Prevent abuse

### Performance

- **Image optimization**: Next.js Image component
- **Lazy loading**: Gallery and preview components
- **CDN**: Supabase storage for static assets
- **Caching**: API route caching for public content

---

## 🎬 Launch Checklist

### Pre-Launch (Technical)

- [ ] All MVP features working
- [ ] Responsive design tested
- [ ] Export functionality optimized
- [ ] Database indexes created
- [ ] Error monitoring setup (Sentry)
- [ ] Performance benchmarked (Lighthouse)

### Launch (Marketing)

- [ ] Landing page copy optimized
- [ ] Sample content created (10+ examples)
- [ ] Social media assets prepared
- [ ] Community outreach planned
- [ ] Analytics goals defined

### Post-Launch (Iteration)

- [ ] User feedback collection system
- [ ] A/B testing framework
- [ ] Feature usage analytics
- [ ] Performance monitoring
- [ ] Community building strategy

---

_This MVP focuses on delivering a unique, technically sound, and immediately usable product that can grow organically through its inherent shareability and creative value proposition._