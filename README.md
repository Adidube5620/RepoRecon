# CodeRecon - AI-Powered Code Analysis Platform

> Transform your code review process with AI-powered insights, security audits, and comprehensive analytics.

## 🚀 Features

### Core Analysis Tools
- **📊 System Blueprint** - Automatic architecture mapping and visualization
- **🤖 AI Insights** - Intelligent code analysis and recommendations
- **🔒 Security Audit** - Vulnerability detection and security best practices
- **📈 Code Quality** - Quality metrics and improvement suggestions
- **📚 Documentation Generator** - Auto-generate comprehensive documentation
- **🏗️ Architecture Diagrams** - Visual system architecture with Mermaid

### User Management & Authentication
- **🔐 Secure Authentication** - Email/password login with JWT tokens
- **👤 User Profiles** - Personal dashboards for each user
- **🔑 Protected Routes** - Secure access to analysis features
- **🚪 Session Management** - Persistent login across sessions

### Project Management
- **📁 Multiple Projects** - Manage unlimited code repositories
- **🔍 Search & Filter** - Quickly find your projects
- **📝 Project Metadata** - Track repository URLs and descriptions
- **🗑️ Project Management** - Create, update, and delete projects

### Analysis History & Tracking
- **💾 Persistent Storage** - All analyses saved to database
- **📜 Complete History** - Access all past analyses anytime
- **🔎 Advanced Filtering** - Filter by analysis type
- **📊 Metrics Tracking** - Track API usage and token counts

### Analytics & Trends
- **📈 Progress Tracking** - See code quality improvements over time
- **📉 Trend Analysis** - Visualize security and quality trends
- **⚖️ Comparison Views** - Compare current vs previous analyses
- **🎯 Performance Metrics** - Track issues fixed and improvements made
- **📅 Timeline View** - Complete analysis history timeline

## 🛠️ Tech Stack

### Backend
- **FastAPI** - Modern Python web framework
- **Supabase** - PostgreSQL database with real-time capabilities
- **Google Gemini AI** - Advanced AI for code analysis
- **PyGithub** - GitHub integration
- **ReportLab & python-docx** - Document generation

### Frontend
- **React 18** - Modern UI library
- **Vite** - Lightning-fast build tool
- **Tailwind CSS** - Utility-first CSS framework
- **Framer Motion** - Smooth animations
- **React Router** - Client-side routing
- **Supabase JS** - Database client
- **Lucide React** - Beautiful icons

## 📦 Installation

### Prerequisites
- Python 3.8+
- Node.js 16+
- Supabase account (free tier works great!)
- Git (optional - only needed for GitHub URL analysis, see [GIT_INSTALLATION.md](./GIT_INSTALLATION.md))

### Backend Setup

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd Codereviewer/backend
```

2. **Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure environment variables**
Create `.env` file in `backend/` directory:
```env
GOOGLE_API_KEY=your_google_api_key
GITHUB_TOKEN=your_github_token
PORT=8000

# Supabase Configuration
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_anon_key
JWT_SECRET=your_jwt_secret_32_chars_min
```

5. **Start the backend server**
```bash
python main.py
```

Backend will run on `http://localhost:8000`

### Frontend Setup

1. **Navigate to frontend directory**
```bash
cd ../frontend
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment variables**
Create `.env` file in `frontend/` directory:
```env
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

4. **Start the development server**
```bash
npm run dev
```

Frontend will run on `http://localhost:5173`

### Supabase Setup

1. **Create Supabase Project**
   - Go to [supabase.com](https://supabase.com)
   - Create a new project
   - Note your Project URL and anon key

2. **Run Database Schema**
   - Open Supabase SQL Editor
   - Copy contents of `backend/database_schema.sql`
   - Run the SQL to create tables and policies

3. **Enable Authentication**
   - In Supabase dashboard, go to Authentication
   - Email auth is enabled by default
   - Configure email templates if desired

For detailed setup instructions, see [SUPABASE_SETUP.md](./SUPABASE_SETUP.md)

## 🎯 Usage

### First Time Setup

1. **Create Account**
   - Visit `http://localhost:5173`
   - Click "Sign up"
   - Enter email and password
   - Verify email (if configured)

2. **Create Your First Project**
   - Click "New Project"
   - Enter project name and repository URL
   - Add optional description

3. **Run Analysis**
   - Upload your code (ZIP file or GitHub URL)
   - Select analysis type
   - View results instantly
   - Results are automatically saved!

### Running Analyses

**Upload Methods:**
- **ZIP File**: Upload compressed repository
- **GitHub URL**: Analyze public repositories
- **GitHub Integration**: Connect your GitHub account

**Analysis Types:**
- **Blueprint**: System architecture and component mapping
- **AI Insights**: Code quality and best practices
- **Security Audit**: Vulnerability scanning
- **Quality Metrics**: Code quality scores
- **Documentation**: Auto-generated docs
- **Architecture**: Visual diagrams

### Viewing Analytics

1. **Project Dashboard**
   - See all your projects
   - View last analyzed dates
   - Quick access to analyses

2. **Analysis History**
   - View all past analyses
   - Filter by type
   - Compare results over time

3. **Trend Analytics**
   - Track code quality improvements
   - Monitor security trends
   - See issues fixed over time
   - Compare first vs latest analysis

## 📊 Database Schema

### Tables

**projects**
- Stores user projects
- Links to repository URLs
- Tracks creation and last analysis dates

**analyses**
- Stores all analysis results
- JSONB format for flexibility
- Tracks token usage
- Links to projects and users

**Row Level Security (RLS)**
- Users can only access their own data
- Automatic data isolation
- Secure by default

## 🔒 Security Features

- **JWT Authentication** - Secure token-based auth
- **Row Level Security** - Database-level access control
- **Password Hashing** - Bcrypt encryption
- **Protected Routes** - Frontend route protection
- **CORS Configuration** - Controlled API access
- **Environment Variables** - Sensitive data protection

## 🎨 UI/UX Features

- **Dark Mode** - Toggle between light and dark themes
- **Responsive Design** - Works on all screen sizes
- **Smooth Animations** - Framer Motion animations
- **Loading States** - Clear feedback during operations
- **Error Handling** - User-friendly error messages
- **Empty States** - Helpful guidance when no data

## 📈 Analytics Features

### Trend Tracking
- **Issues Trend**: Track bug fixes over time
- **Security Trend**: Monitor vulnerability improvements
- **Quality Trend**: See code quality changes

### Comparison Views
- **First vs Latest**: Compare initial and current state
- **Time-based**: See improvements over days/weeks
- **Metric-specific**: Focus on specific improvements

### Visualizations
- **Trend Cards**: Color-coded improvement indicators
- **Progress Stats**: Numerical improvement metrics
- **Timeline View**: Chronological analysis history

## 🚀 Deployment

### Backend Deployment
- Deploy to Heroku, Railway, or any Python hosting
- Set environment variables
- Ensure Supabase connection

### Frontend Deployment
- Build: `npm run build`
- Deploy to Vercel, Netlify, or Cloudflare Pages
- Set environment variables
- Update CORS settings in backend

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📝 License

This project is licensed under the MIT License.

## 🆘 Support

For issues and questions:
- Check [SUPABASE_SETUP.md](./SUPABASE_SETUP.md) for setup help
- Review error messages in browser console
- Check backend logs for API errors

## 🎯 Roadmap

- [ ] Team collaboration features
- [ ] Real-time collaboration
- [ ] Advanced charting with Chart.js
- [ ] Export analytics to PDF
- [ ] Scheduled analysis runs
- [ ] Webhook integrations
- [ ] CI/CD integration
- [ ] Custom analysis rules

## ⭐ Features Highlight

### What Makes CodeRecon Special?

1. **AI-Powered Analysis** - Leverages Google Gemini for intelligent insights
2. **Complete History** - Never lose an analysis again
3. **Trend Tracking** - See your code improve over time
4. **Multi-Project** - Manage all your repositories in one place
5. **Beautiful UI** - Modern, responsive design with smooth animations
6. **Secure** - Enterprise-grade security with RLS
7. **Fast** - Optimized for performance
8. **Free** - Use Supabase free tier for unlimited analyses

---

**Built with ❤️ using React, FastAPI, and Supabase by Aditya Dubey**
