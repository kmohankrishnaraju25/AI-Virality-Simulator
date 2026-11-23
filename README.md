::: {align="center"}
# 🚀 AI Virality Simulator

### Understand your video. Discover your audience. Predict engagement. Optimize for reach.

An AI-powered, multi-agent video intelligence platform that analyzes
video content, discovers audience segments, simulates engagement across
virtual personas, estimates virality, and generates actionable
content-optimization recommendations.

[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![AI](https://img.shields.io/badge/AI-Multi--Agent-8A2BE2)](#how-it-works)
[![Status](https://img.shields.io/badge/Status-Development-orange)](https://github.com/kmohankrishnaraju25/AI-Virality-Simulator)
[![License](https://img.shields.io/badge/License-Not%20Specified-lightgrey)](#license)
:::📌 Overview
AI Virality Simulator helps creators and content teams evaluate a
video's potential before publishing it. Instead of looking at a video
only as a file, the system processes its visual, audio, and textual
signals, identifies likely audience groups, and models how a virtual
population may respond.

The project uses a six-agent pipeline. Each agent handles a focused
stage, and the combined outputs are used to produce a virality report
and a practical optimization plan.
Note: Virality and engagement outputs are AI-generated estimates
for analysis and experimentation. They are not guarantees of actual
platform performance.

✨ Key Features
- Video analysis -- extracts video information and analyzes
  frames, on-screen text, and audio.
- Audience discovery -- identifies potential audience segments
  from the content profile.
- Virtual audience simulation -- generates a population of 1,000
  synthetic users for modeled audience analysis.
- Engagement prediction -- estimates engagement and virality
  signals using the generated profiles.
- Automated reporting -- produces a structured virality report in
  JSON and human-readable formats.
- Content optimization -- generates recommendations intended to
  improve the video's appeal and engagement potential.
- Interactive dashboard -- provides an overview, pipeline view,
  retention analytics, optimizer, and audience-persona sections.
- Video upload and simulation -- supports selecting or uploading a
  video and starting the pipeline through the local interface.
🧠 How It Works
The application runs the following six stages in sequence:
  Agent                   Responsibility          Main output
  Agent 1 -- Video      Examines video          Content profile
Analyzer              metadata, frames, OCR
text, audio, and visual
content.                

  Agent 2 -- Audience   Finds audience segments Audience profile
Discovery             that may relate to the
video.                  

  Agent 3 -- Population Creates a synthetic     Virtual population
Generator             audience based on the
discovered segments.    

  Agent 4 -- Engagement Estimates engagement    Engagement prediction
Predictor             and virality using the
content, audience, and
population profiles.    

  Agent 5 -- Report     Combines the analysis   Virality report
Generator             into a structured
report.                 
Agent 6 -- Content    Uses the analysis and   Optimization plan
Optimizer             report to propose
content improvements.
Pipeline
                Video input
                    │
                    ▼
          Agent 1: Video Analyzer
                    │
                    ▼
         Agent 2: Audience Discovery
                    │
                    ▼
       Agent 3: Virtual Population
                    │
                    ▼
       Agent 4: Engagement Predictor
                    │
                    ▼
          Agent 5: Report Generator
                    │
                    ▼
         Agent 6: Content Optimizer
                    │
                    ▼
       Reports + Interactive Dashboard
🛠️ Technology
The repository is primarily implemented in Python, with HTML, CSS,
and JavaScript for the browser-based interface.

  Area               Technologies / components
  Core application   Python
User interface     HTML, CSS, JavaScript
AI providers       Groq API or Google Gemini API
Video processing   Project video/frame service modules
Text extraction    Project OCR service module
Audio analysis     Project audio service module
Visualization      HTML dashboard
Local server       Python HTTP server

The exact Python package versions and dependencies are maintained in
[`requirements.txt`](requirements.txt).
📂 Project Structure
AI-Virality-Simulator/
│
├── agents/
│   ├── agent1_video_analyzer.py
│   ├── agent2_audience_discovery.py
│   ├── agent3_population_generator.py
│   ├── agent4_engagement_predictor.py
│   ├── agent5_report_generator.py
│   └── agent6_content_optimizer.py
│
├── services/
│   ├── frame_service.py
│   ├── ocr_service.py
│   ├── audio_service.py
│   └── vision_service.py
│
├── videos/                  # Add input videos here
├── outputs/                 # Generated analysis and reports
│
├── main.py                  # Runs the six-agent pipeline
├── serve.py                 # Starts the local dashboard server
├── index.html               # Main browser interface
├── dashboard.html           # Interactive analysis dashboard
├── generate_dashboard.py    # Dashboard data synchronization
├── requirements.txt         # Python dependencies
├── .env.example             # Example API configuration
└── README.md
The folders shown for generated files (such as videos/ and
outputs/) are used by the application; they may be created locally
when you run it.
⚙️ Getting Started
1. Prerequisites
- Python installed and available from your terminal.
- Git.
- An API key for one of the supported AI providers (Groq or Google
  Gemini), depending on the configured services.
- A supported video file such as .mp4, .mov, .avi, .mkv, or
  .webm.
2. Clone the repository
git clone https://github.com/kmohankrishnaraju25/AI-Virality-Simulator.git
cd AI-Virality-Simulator
3. Create and activate a virtual environment
Windows (PowerShell):
python -m venv venv
.\venv\Scripts\Activate.ps1
Windows (Command Prompt):
python -m venv venv
venv\Scripts\activate
macOS / Linux:
python3 -m venv venv
source venv/bin/activate
4. Install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
5. Configure your API key
Copy .env.example to a new file named .env:

Windows (PowerShell):
Copy-Item .env.example .env
Windows (Command Prompt):
copy .env.example .env
macOS / Linux:
cp .env.example .env
Open .env and add the API key for the provider you intend to use:
GROQ_API_KEY=your_groq_api_key
GEMINI_API_KEY=your_gemini_api_key
Use the provider configured by the project. You generally do not need to
fill in both keys if you are using only one provider.
- Groq API keys: https://console.groq.com/keys
- Google AI Studio: https://aistudio.google.com/
Security: Never commit your .env file or publish API keys. Keep
.env.example as a template with placeholder values.
6. Add a video
Create a videos folder in the project root if it does not already
exist, then place your input video inside it.
AI-Virality-Simulator/
└── videos/
    └── my_video.mp4
The pipeline can use a video path passed as a command-line argument. If
no path is supplied, it looks for a video in the videos/ directory.
▶️ Run the Application
Option A: Run the AI pipeline
python main.py
To analyze a particular video:
python main.py videos/my_video.mp4
The pipeline executes Agents 1--6 and writes analysis results and
reports into the outputs/ directory.
Option B: Launch the dashboard server
python serve.py
Then open the dashboard in your browser:

http://localhost:8000/dashboard.html

The local server provides the browser interface and endpoints used by
the dashboard to upload videos and trigger simulations.
📊 Generated Outputs
The pipeline creates an outputs/ directory and writes intermediate and
final artifacts. Depending on the stage, these include:
  Output                              Description
  active_video.json                 Information about the selected
video

  content_profile.json              Video content analysis

  audience_profile.json             Discovered audience segments

  virtual_population.json           Synthetic audience population data

  engagement_prediction.json        Engagement and virality estimates

  virality_report.json              Structured final report

  VIRALITY_REPORT.md                Readable virality report

  report.html                       HTML report

  viral_optimization_plan.json      Structured optimization
recommendations

  VIRAL_OPTIMIZATION_PLAN.md        Readable optimization plan
optimization_dashboard.html       Optimization dashboard artifact
The interactive dashboard also synchronizes its view with generated
analysis data.
🖥️ Dashboard Sections
The browser interface includes:
- Executive Overview -- a high-level view of the virality analysis
  and key indicators.
- 6-Agent Pipeline -- an overview of the multi-agent workflow.
- Retention Analytics -- video retention and engagement-related
  analytics.
- Viral Optimizer -- recommendations generated by Agent 6.
- Personas -- audience persona information.
🔐 Environment & Security
- Store API credentials in .env.
- Do not hard-code API keys in Python or frontend files.
- Do not commit secrets, private videos, or sensitive generated data.
- Use .env.example only to document the required variable names.
- Review API-provider usage limits and terms before running large
  workloads.
🧪 Troubleshooting
  Issue                               What to check
  ModuleNotFoundError               Activate the virtual environment and
run
pip install -r requirements.txt.

  API authentication error            Verify the relevant key in .env,
its validity, and provider access.

  No video found                      Add a supported video file to
videos/ or pass its path to
main.py.

  Dashboard does not show updated     Run the pipeline first, then refresh
results                             the dashboard.
Port 8000 is already in use         Close the process using the port or
update the port configuration in
serve.py.
🔮 Future Improvements
Potential directions for further development include:
- Support for more video and social-media formats.
- Platform-specific prediction configurations.
- More detailed audience-persona customization.
- Comparison of multiple video versions.
- Exportable visual reports and analytics.
- Model evaluation against real-world performance data.
🤝 Contributing
Contributions, suggestions, and bug reports are welcome.
1. Fork the repository.
2. Create a feature branch: git checkout -b feature/your-feature.
3. Commit your changes: git commit -m "Add your feature".
4. Push the branch: git push origin feature/your-feature.
5. Open a Pull Request.
📄 License
No license is currently specified in the repository. Unless a license is
added, reuse and redistribution are not automatically granted. Add a
LICENSE file if you intend to publish the project under an open-source
license.
👨‍💻 Author
Mohan Krishnaraju
- GitHub:
  @kmohankrishnaraju25
- Project:
  AI-Virality-Simulator
::: {align="center"}
**If you find this project useful, consider giving the repository a ⭐**

Made with Python and AI.
:::
