# 🎓 AI Masterclass Analytics Dashboard

## 📊 Overview

Professional analytics dashboard for AI/ML masterclasses with advanced NLP analysis, real content extraction, and GPT-4 powered summaries. This application provides comprehensive insights from video transcripts, generating detailed professional reports and interactive visualizations.

## ✨ Features

### 🧠 Advanced NLP Analysis
- **Real Content Extraction**: Direct analysis from video transcripts
- **Technical Term Detection**: AI-powered identification of methodologies and technologies
- **Content Complexity Assessment**: Automatic classification of difficulty levels
- **Q&A Analysis**: Interactive question-answer pair extraction

### 📊 Professional Reporting
- **GPT-4 Powered Summaries**: 1000+ word professional analysis
- **Multiple Export Formats**: HTML, PDF, Markdown, and Text
- **Cached Analysis**: Efficient processing with intelligent caching
- **Real Video Duration**: Accurate timing from transcript metadata

### 🎯 Interactive Visualizations
- **Content Volume Analysis**: Word count vs duration charts
- **Technical Complexity Distribution**: Visual complexity breakdown
- **Technical Domain Mapping**: Frequency analysis of technical terms
- **Methodology Extraction**: Smart identification of frameworks and approaches

### 📈 Intelligence Metrics
- Total content analysis across all masterclasses
- Real video duration calculations
- Technical entity extraction and categorization
- Professional learning library with enhanced search

## 🚀 Quick Start

### For Streamlit Cloud Deployment

1. **Fork this repository** to your GitHub account

2. **Add your OpenAI API key** in Streamlit Cloud:
   - Go to your Streamlit Cloud dashboard
   - Navigate to your app settings
   - Add secrets in the following format:
   ```toml
   OPENAI_API_KEY = "your-openai-api-key-here"
   ```

3. **Deploy** your app through Streamlit Cloud interface

### For Local Development

1. **Clone the repository**:
   ```bash
   git clone <your-repo-url>
   cd ai-masterclass-analytics
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up your OpenAI API key**:
   ```bash
   export OPENAI_API_KEY="your-openai-api-key-here"
   ```
   
   Or create `.streamlit/secrets.toml`:
   ```toml
   OPENAI_API_KEY = "your-openai-api-key-here"
   ```

4. **Prepare your data**:
   - Create a `data/` directory
   - Add your `masterclass.db` SQLite database with the following schema:
   ```sql
   CREATE TABLE masterclasses (
       id INTEGER PRIMARY KEY,
       title TEXT NOT NULL,
       content TEXT NOT NULL,
       analysis_data TEXT
   );
   ```

5. **Run the application**:
   ```bash
   streamlit run hybrid_app.py
   ```

## 📁 Project Structure

```
ai-masterclass-analytics/
├── hybrid_app.py              # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                 # This file
├── .streamlit/
│   └── secrets.toml          # API keys (local only)
└── data/
    └── masterclass.db        # SQLite database with transcripts
```

## 🔧 Configuration

### Database Schema

The application expects a SQLite database with the following structure:

```sql
CREATE TABLE masterclasses (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content TEXT NOT NULL,
    analysis_data TEXT
);

CREATE TABLE professional_summaries (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content_hash TEXT NOT NULL,
    summary TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    UNIQUE(title, content_hash)
);
```

### Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key for GPT-4 analysis

## 🎨 Key Components

### 📊 Dashboard Overview
- **Intelligence Metrics**: Real-time analytics across all content
- **Content Volume vs Duration**: Interactive dual-axis charts
- **NLP Complexity Distribution**: Visual complexity analysis
- **Technical Domain Analysis**: Frequency-based term extraction

### 🧠 Individual Masterclass Analysis
- **Content Overview**: Comprehensive metrics and statistics
- **Real Analysis**: GPT-4 powered professional summaries
- **NLP Intelligence**: Advanced linguistic analysis

### 📈 Advanced Features
- **Smart Caching**: Efficient re-processing with hash-based caching
- **Real Video Duration**: Extraction from transcript metadata
- **Spanish Encoding Fix**: Robust handling of international characters
- **Methodology Detection**: Advanced pattern recognition for technical approaches

## 🔒 Security & Privacy

- API keys are securely managed through Streamlit secrets
- Content analysis is performed locally with OpenAI API calls
- No data is stored externally beyond OpenAI's standard processing
- All generated reports can be downloaded for offline use

## 📊 Data Flow

1. **Input**: Video transcripts stored in SQLite database
2. **Processing**: NLP analysis extracts technical terms, methodologies, and insights
3. **AI Analysis**: GPT-4 generates comprehensive professional summaries
4. **Caching**: Results are cached for efficient subsequent access
5. **Output**: Interactive dashboards, downloadable reports, and visualizations

## 🛠️ Technical Stack

- **Frontend**: Streamlit with custom CSS styling
- **Data Processing**: Pandas, NumPy for data manipulation
- **Visualizations**: Plotly for interactive charts
- **AI Integration**: OpenAI GPT-4 for content analysis
- **Database**: SQLite for local data storage
- **Export**: ReportLab for PDF generation, custom HTML templates

## 📧 Support & Contributing

For questions, issues, or contributions:

1. **Issues**: Open an issue on GitHub with detailed description
2. **Feature Requests**: Submit enhancement proposals through GitHub issues
3. **Contributions**: Fork the repository and submit pull requests

## 📄 License

This project is intended for educational use. Please ensure compliance with OpenAI's usage policies when deploying.

## 🎯 Use Cases

- **Educational Institutions**: Analyze course content and complexity
- **Corporate Training**: Evaluate training material effectiveness
- **Content Creators**: Optimize educational content for target audiences
- **Research**: Study patterns in educational content and delivery methods

---

**Built with ❤️ for advancing AI education analytics**

*Last updated: July 2025*
