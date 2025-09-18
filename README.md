# iLovePasswords - Secure Password Generator & Vault

A modern, secure password generator and vault application built with React, Vite, TypeScript, and Supabase. Generate strong passwords and store them securely with client-side encryption.

## 🚀 Features

### Password Generator

-  **Extended Length Range**: Generate passwords from 8 to 128 characters
-  **Character Type Options**: Toggle uppercase, lowercase, numbers, and special characters
-  **Ensure Each Type**: Guarantee at least one character from each selected type
-  **Real-time Strength Analysis**: Live password strength meter with animated visual feedback
-  **Copy to Clipboard**: One-click password copying with animated confirmation
-  **Show/Hide Toggle**: Secure password visibility controls
-  **Modern UI**: Gradient backgrounds, smooth animations, and dark mode support

### Secure Vault

-  **Client-Side Encryption**: Passwords encrypted locally using Web Crypto API (AES-GCM)
-  **Zero-Knowledge Architecture**: Only encrypted data stored on servers
-  **Master Password Protection**: Your master password never leaves your device
-  **Password Categories**: Organize passwords by Social Media, Email, Work, Banking, Shopping, Entertainment, Utilities, and Other
-  **Advanced Search & Filter**: Search by title, username, URL, and filter by category
-  **Grid/List View Toggle**: Switch between card grid and list views
-  **CRUD Operations**: Add, edit, delete, and organize your passwords with smooth animations
-  **Metadata Storage**: Store titles, usernames, URLs, and categories with each password

### Authentication

-  **Supabase Auth**: Secure email/password authentication
-  **Google OAuth**: Sign in with Google for quick access
-  **Protected Routes**: Vault access requires authentication
-  **Session Management**: Automatic session handling and refresh
-  **Modern Auth UI**: Beautiful authentication forms with animations

### Security Features

-  **AES-GCM Encryption**: Industry-standard authenticated encryption
-  **PBKDF2 Key Derivation**: 100,000 iterations for key strengthening
-  **Random Salt & IV**: Unique encryption parameters for each password
-  **No Plaintext Storage**: Passwords never stored in readable format
-  **Row Level Security**: Database-level access control

### Design & UX

-  **Dark/Light Mode**: Toggle between themes with smooth transitions
-  **Framer Motion Animations**: Smooth, performant animations throughout
-  **Responsive Design**: Mobile-first approach with perfect desktop experience
-  **Modern Gradients**: Beautiful gradient backgrounds and UI elements
-  **Glassmorphism**: Backdrop blur effects for modern aesthetic
-  **Micro-interactions**: Hover effects, button animations, and feedback

## 🛠️ Tech Stack

-  **Framework**: React 18 with Vite
-  **Language**: TypeScript
-  **Styling**: TailwindCSS
-  **Animations**: Framer Motion
-  **Database**: Supabase (PostgreSQL)
-  **Authentication**: Supabase Auth
-  **Encryption**: Web Crypto API
-  **UI Components**: Custom components with Radix-inspired design
-  **Routing**: React Router v6
-  **Icons**: Lucide React

## 📦 Installation

### Prerequisites

-  Node.js 18+ (recommended: 20+)
-  npm or yarn
-  Supabase account

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd iLovePasswords
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Setup

Copy the example environment file and configure your variables:

```bash
cp env.example .env.local
```

Update `.env.local` with your Supabase credentials:

```env
VITE_SUPABASE_URL=your-supabase-project-url
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
```

### 4. Supabase Setup

1. **Create a new Supabase project** at [supabase.com](https://supabase.com)

2. **Run the database schema**:

   -  Go to the SQL Editor in your Supabase dashboard
   -  Copy and execute the contents of `supabase-schema.sql`

3. **Configure Authentication**:

   -  Go to Authentication > Settings
   -  Enable email authentication
   -  Configure email templates if needed

4. **Get your credentials**:
   -  Go to Settings > API
   -  Copy your project URL and anon key to `.env.local`

### 5. Run Development Server

```bash
npm run dev
```

Visit [http://localhost:5173](http://localhost:5173) to see the application.

## 🔧 Development

### Available Scripts

-  `npm run dev` - Start development server
-  `npm run build` - Build for production
-  `npm run preview` - Preview production build
-  `npm run lint` - Run ESLint

### Project Structure

```
src/
├── components/           # React components
│   ├── ui/              # Reusable UI components
│   ├── AuthForm.tsx     # Authentication form
│   ├── PasswordGenerator.tsx
│   ├── Vault.tsx        # Main vault component
│   ├── VaultEntry.tsx   # Individual vault entry
│   └── VaultForm.tsx    # Add/edit entry form
├── contexts/            # React contexts
│   └── AuthContext.tsx  # Authentication context
├── lib/                 # Utility libraries
│   ├── crypto.ts        # Encryption/decryption functions
│   ├── supabase.ts      # Supabase client configuration
│   └── utils.ts         # General utilities
├── pages/               # Page components
│   ├── Home.tsx         # Landing page
│   ├── Auth.tsx         # Authentication page
│   └── VaultPage.tsx    # Vault page
├── types/               # TypeScript type definitions
│   └── index.ts
└── main.tsx             # Application entry point
```

## 🚀 Deployment

### Vercel Deployment (Recommended)

1. **Connect to Vercel**:

   -  Import your GitHub repository to Vercel
   -  Vercel will automatically detect it as a Vite project

2. **Environment Variables**:
   Set the following in Vercel dashboard:

   ```
   VITE_SUPABASE_URL=your-supabase-url
   VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
   ```

3. **Deploy**:
   -  Vercel will automatically deploy on push to main branch
   -  Or manually deploy from Vercel dashboard

### Other Platforms

The app can be deployed to any static hosting service:

-  Netlify
-  GitHub Pages
-  AWS S3 + CloudFront
-  Firebase Hosting

## 🔐 Security Considerations

### Client-Side Encryption

-  All passwords are encrypted locally before being sent to the server
-  Uses AES-GCM with 256-bit keys for authenticated encryption
-  PBKDF2 with 100,000 iterations for key derivation
-  Unique salt and IV for each password entry

### Master Password

-  Never transmitted to or stored on servers
-  Used only for local encryption/decryption
-  Required each time you unlock your vault

### Best Practices

-  Use a strong, unique master password
-  Enable 2FA on your Supabase account
-  Regularly backup your encrypted vault data
-  Keep your master password secure and memorable

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

-  [React](https://react.dev/) for the amazing UI library
-  [Vite](https://vitejs.dev/) for the fast build tool
-  [Supabase](https://supabase.com/) for backend services
-  [TailwindCSS](https://tailwindcss.com/) for styling
-  [Framer Motion](https://www.framer.com/motion/) for animations
-  [Lucide](https://lucide.dev/) for beautiful icons

## 📞 Support

If you have any questions or need help:

-  Open an issue on GitHub
-  Check the documentation
-  Review the code comments

---

**⚠️ Security Notice**: This application uses client-side encryption to protect your passwords. However, you should always use a strong master password and keep it secure. The developers are not responsible for any data loss or security breaches.
