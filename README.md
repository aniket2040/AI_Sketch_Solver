# AI Sketch Solver

A powerful web application that uses AI to solve mathematical expressions, equations, and graphical problems drawn on a canvas. Built with a FastAPI backend and React TypeScript frontend.

## 🚀 Features

### Core Functionality
- **Canvas Drawing**: Draw mathematical expressions, equations, and graphical problems with multiple color options
- **AI-Powered Analysis**: Uses Google's Gemini AI to analyze and solve drawn mathematical content
- **Multiple Problem Types**:
  - Simple mathematical expressions (2 + 2, 3 * 4, etc.)
  - Equations with variables (x^2 + 2x + 1 = 0)
  - Variable assignments (x = 4, y = 5)
  - Graphical math problems (trigonometry, Pythagorean theorem, etc.)
  - Abstract concept detection from drawings
- **Variable Management**: Store and reuse variables across multiple calculations
- **LaTeX Rendering**: Beautiful mathematical notation display using MathJax
- **Draggable Results**: Move solution displays anywhere on the canvas

### Technical Features
- **Real-time Processing**: Instant analysis of drawn content
- **Color-coded Drawing**: 11 different colors for complex diagrams
- **Responsive Design**: Works on desktop and mobile devices
- **CORS Enabled**: Cross-origin requests supported for API integration

## 🛠️ Tech Stack

### Backend (calc-be)
- **FastAPI**: Modern, fast web framework for building APIs
- **Google Gemini AI**: Advanced AI model for mathematical analysis
- **Pydantic**: Data validation using Python type hints
- **Uvicorn**: ASGI server for FastAPI
- **PIL (Pillow)**: Image processing library
- **Python-dotenv**: Environment variable management

### Frontend (calc-fron)
- **React 18**: Modern React with hooks
- **TypeScript**: Type-safe JavaScript
- **Vite**: Fast build tool and dev server
- **Tailwind CSS**: Utility-first CSS framework
- **Mantine UI**: React component library
- **Axios**: HTTP client for API calls
- **React Draggable**: Drag and drop functionality
- **MathJax**: LaTeX mathematical rendering

## 📦 Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- Python 3.8+
- Google Gemini API key

### Backend Setup

1. Navigate to the backend directory:
```bash
cd calc-be
```

2. Create a virtual environment:
```bash
python -m venv venv
```

3. Activate the virtual environment:
- Windows:
```bash
venv\Scripts\activate
```
- macOS/Linux:
```bash
source venv/bin/activate
```

4. Install dependencies:
```bash
pip install -r requirements.txt
```

5. Create environment file:
```bash
cp .envExample .env
```

6. Add your Google Gemini API key to `.env`:
```
GEMINI_API_KEY=your_gemini_api_key_here
```

7. Run the backend server:
```bash
python main.py
```

The backend will run on `http://localhost:8900`

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd calc-fron
```

2. Install dependencies:
```bash
npm install
```

3. Create environment file:
```bash
cp .env.example .env
```

4. Add API URL to `.env`:
```
VITE_API_URL=http://localhost:8900
```

5. Start the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173`

## 🎯 Usage

1. **Open the application** in your web browser
2. **Choose a color** from the color palette
3. **Draw your mathematical expression** or problem on the canvas
4. **Click "Run"** to analyze your drawing
5. **View the solution** displayed in beautiful LaTeX notation
6. **Drag the solution** to any position on the canvas
7. **Use "Reset"** to clear the canvas and start over

### Supported Problem Types

1. **Simple Expressions**: `2 + 3 * 4` → `14`
2. **Equations**: `x^2 + 2x + 1 = 0` → `x = -1`
3. **Variable Assignment**: `x = 5` → Stores value for future use
4. **Graphical Problems**: Draw triangles, graphs, or diagrams
5. **Abstract Concepts**: Detect concepts from drawings

## 🔧 API Endpoints

### POST `/calculate`
Analyzes an image and returns mathematical solutions.

**Request Body:**
```json
{
  "image": "base64_encoded_image_data",
  "dict_of_vars": {
    "x": "5",
    "y": "10"
  }
}
```

**Response:**
```json
{
  "message": "Image processed",
  "data": [
    {
      "expr": "2 + 3 * 4",
      "result": "14",
      "assign": false
    }
  ],
  "status": "success"
}
```

## 🎨 Color Palette

The application provides 11 colors for drawing:
- White (#ffffff)
- Red (#ee3333)
- Pink (#e64980)
- Purple (#be4bdb)
- Olive (#839200)
- Blue (#228be6)
- Dark Blue (#3333ee)
- Green (#40c057)
- Yellow (#fab005)
- Dark Green (#00aa00)
- Orange (#fd7e14)

## 📁 Project Structure

```
├── calc-be/                 # Backend (FastAPI)
│   ├── apps/
│   │   └── calculator/
│   │       ├── route.py     # API routes
│   │       └── utils.py     # AI processing logic
│   ├── constants.py         # Configuration constants
│   ├── schema.py           # Pydantic models
│   ├── main.py             # FastAPI application
│   └── .envExample         # Environment template
│
├── calc-fron/              # Frontend (React + TypeScript)
│   ├── src/
│   │   ├── components/     # Reusable components
│   │   ├── screens/        # Page components
│   │   ├── constants.ts    # Application constants
│   │   └── lib/           # Utility functions
│   ├── public/            # Static assets
│   └── package.json       # Dependencies
│
└── README.md              # This file
```

## 🔒 Environment Variables

### Backend (.env)
- `GEMINI_API_KEY`: Your Google Gemini API key
- `SERVER_URL`: Server host (default: localhost)
- `PORT`: Server port (default: 8900)
- `ENV`: Environment (dev/prod)

### Frontend (.env)
- `VITE_API_URL`: Backend API URL (default: http://localhost:8900)

## 🚀 Deployment

### Backend Deployment
The backend can be deployed to any platform supporting Python/ASGI:
- Railway
- Heroku
- DigitalOcean App Platform
- AWS Elastic Beanstalk

### Frontend Deployment
The frontend can be deployed to:
- Vercel
- Netlify
- GitHub Pages
- Any static hosting service

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Google Gemini AI for mathematical analysis capabilities
- FastAPI team for the excellent web framework
- React and Vite teams for the modern frontend tooling
- MathJax for beautiful mathematical notation rendering

## 📞 Support

For support or questions, please open an issue in the GitHub repository.

---

**Note**: This application requires a valid Google Gemini API key to function. You can obtain one from the [Google AI Studio](https://makersuite.google.com/app/apikey).
