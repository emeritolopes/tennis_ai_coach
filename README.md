# Tennis AI Coach

**AI-Powered Tennis Technique Analysis & Personalized Coaching**

Transform your tennis game with cutting-edge computer vision and AI coaching. Upload a video of your practice session and get instant, personalized feedback on your technique.

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-app-url.streamlit.app)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Features

### Current (MVP)

- **Video Upload & Analysis** - Upload tennis practice videos directly in the browser
- **AI Pose Detection** - Advanced body tracking using MediaPipe
- **Technique Metrics** - Measure swing speed, contact point height, elbow angle, and more
- **AI Coaching Feedback** - Get personalized coaching advice powered by GPT-4
- **Annotated Video Export** - Download your video with skeleton overlay and metrics
- **Progress Tracking** - See your improvement over time

### Coming Soon

- **Wearable Integration** - Connect WHOOP, Apple Watch, or Garmin for recovery-aware coaching
- **User Accounts** - Save your sessions and track long-term progress
- **Advanced Analytics** - Shot type classification, ball tracking, placement analysis
- **Comparison Mode** - Compare your technique to professional players
- **Mobile App** - Native iOS and Android applications

---

## Quick Start

### Prerequisites

- Python 3.10 or higher
- pip (Python package manager)
- A tennis video (recorded from side angle)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/emeritolopes/tennis_ai_coach.git
   cd tennis-ai-coach
   ```

2. **Create virtual environment**

   ```bash
   python -m venv venv

   # On Windows:
   venv\Scripts\activate

   # On Mac/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up OpenAI API key (optional, for AI coaching)**

   Create a file `.streamlit/secrets.toml`:

   ```toml
   OPENAI_API_KEY = "your-api-key-here"
   ```

   Get your API key at [platform.openai.com](https://platform.openai.com/)

5. **Run the app**

   ```bash
   streamlit run app.py
   ```

6. **Open your browser**

   Navigate to `http://localhost:8501`

---

## 📖 How to Use

### Recording Your Video

For best results, follow these guidelines:

**DO:**

- Record from the **side angle** (perpendicular to the net)
- Capture **full body** (head to feet in frame)
- Use **good lighting** (outdoor or well-lit indoor courts)
- Keep camera **steady** (use a tripod or prop phone against something)
- Record **5-10 strokes** minimum for accurate analysis
- Film at **30fps or higher**

**AVOID:**

- Recording from behind the player
- Cutting off head or feet
- Shaky handheld video
- Poor lighting or shadows
- Camera too far away (player should fill ~60% of frame)

### Analyzing Your Video

1. **Upload Video** - Click "Browse files" and select your tennis video
2. **Review Upload** - The video will play in the browser for verification
3. **Analyze** - Click "Analyze My Technique" button
4. **Wait** - Processing takes 1-2 minutes depending on video length
5. **Review Results** - See your metrics, coaching feedback, and annotated video
6. **Download** - Save the annotated video for your records

---

## Technical Details

### Architecture

```
tennis-ai-coach/
├── app.py                    # Main Streamlit application
├── video_analysis.py         # Computer vision & pose analysis
├── coaching.py               # AI coaching generation
├── requirements.txt          # Python dependencies
├── .streamlit/
│   └── secrets.toml         # API keys (not committed)
└── README.md                # This file
```

### Technologies Used (initially)

- **[Streamlit](https://streamlit.io/)** - Web application framework
- **[MediaPipe](https://google.github.io/mediapipe/)** - Pose estimation and body tracking
- **[OpenCV](https://opencv.org/)** - Video processing and computer vision
- **[OpenAI GPT-4](https://openai.com/)** - AI coaching feedback generation
- **[NumPy](https://numpy.org/)** - Numerical computations
- **[Pandas](https://pandas.pydata.org/)** - Data analysis and tracking

### Key Metrics Analyzed

| Metric                   | Description                                 | Optimal Range   |
| ------------------------ | ------------------------------------------- | --------------- |
| **Elbow Angle**          | Angle at elbow joint during contact         | 150-170°        |
| **Contact Point Height** | Where ball is struck relative to body       | Shoulder height |
| **Swing Speed**          | Estimated racket speed through contact zone | Varies by level |
| **Shot Count**           | Number of forehands/backhands/serves        | -               |
| **Contact Consistency**  | % of shots with good contact point          | >70%            |

---

## Roadmap

### Phase 1: MVP (Current)

- [x] Basic video upload and playback
- [x] Pose detection with MediaPipe
- [x] Calculate key tennis metrics
- [x] Generate AI coaching feedback
- [x] Export annotated videos

### Phase 2: User System (In Progress)

- [ ] User authentication (login/signup)
- [ ] Session history and storage
- [ ] Progress tracking over time
- [ ] Comparison charts (week-over-week)

### Phase 3: Advanced Analysis

- [ ] Shot type classification (forehand/backhand/serve)
- [ ] Ball tracking and trajectory analysis
- [ ] Court positioning and movement analysis
- [ ] Spin estimation
- [ ] Match strategy recommendations

### Phase 4: Integrations

- [ ] WHOOP API integration
- [ ] Apple HealthKit integration
- [ ] Garmin Connect integration
- [ ] Recovery-aware training recommendations

### Phase 5: Mobile & Scale

- [ ] React Native mobile app
- [ ] Real-time analysis mode
- [ ] Social features (share progress)
- [ ] Coach/academy accounts

---

## Contributing

Contributions are welcome!

## Example Results

### Before and After

**Input:** Raw tennis practice video

```
[Side-angle video of player hitting forehands]
```

**Output:** Comprehensive analysis

- Analyzed 45 forehands in 2 minutes
- Average elbow angle: 162° (optimal range)
- Contact point: 68% good, 32% low
- Recommended drill: Wall rally at shoulder height
- Annotated video with skeleton overlay

### Sample Coaching Feedback

> **What You Did Well:**
> Your elbow angle is consistently in the optimal range (160-165°), showing good arm extension at contact. Your swing path is smooth and controlled.
>
> **Primary Area to Improve:**
> Your contact point is too low on 32% of shots, which limits power and makes it harder to generate topspin.
>
> **Recommended Drill:**
> Practice the "Wall Rally Drill" - Stand 2 meters from a wall and hit 20 forehands, focusing exclusively on contacting the ball at shoulder height. Don't worry about power; just focus on high contact point. Do this for 5 minutes before each practice session.
>
> **Expected Timeline:**
> With consistent practice, you should see 10-15% improvement in contact point height within 2-3 weeks.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Happy Practicing!

Built with love for tennis players by a tennis player.

_"The best time to plant a tree was 20 years ago. The second best time is now."_ - Also applies to improving your forehand.

---

**[⬆ back to top](#-tennis-ai-coach)**
cd