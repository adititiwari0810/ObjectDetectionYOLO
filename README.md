# 🎯 YOLO Object Detection System

Advanced object detection system with YOLOv3, ROI monitoring, email alerts, and web dashboard.

## 🚀 Features

- ✅ Real-time object detection using YOLOv3
- 🎯 Region of Interest (ROI) monitoring
- 📧 Email alerts with video clips
- 🌐 Web dashboard for viewing logs and clips
- 📊 Analytics and reporting
- 💾 CSV logging and clip management

## 📋 Requirements

- Python 3.7+
- Webcam or video file
- Gmail account (for email alerts)

## 🔧 Installation

1. **Clone the repository:**
```bash
git clone https://github.com/YOUR_USERNAME/ObjectDetectionYOLO.git
cd ObjectDetectionYOLO
```

2. **Install dependencies:**
```bash
pip install -r requirements.txt
```

3. **Run setup script:**
```bash
python setup.py
```

4. **Download YOLOv3 weights:**
- Download from: [https://pjreddie.com/media/files/yolov3.weights](https://pjreddie.com/media/files/yolov3.weights)
- Place in `weights/` folder

## 📖 Usage

### Basic Detection
```bash
python main.py
```

### With ROI Monitoring
```bash
python main.py --roi
```

### With Email Alerts
```bash
python main.py --roi --email --alert-objects person,car
```

### View Analytics
```bash
python analytics_viewer.py
```

### Manage Video Clips
```bash
python compile_alerts.py
```

### Web Dashboard
```bash
python web_dashboard.py
# Open http://localhost:5000
```

## ⚙️ Configuration

Edit `main.py` to configure:
- Email credentials (lines 40-46)
- ROI zones (lines 49-53)
- Alert objects
- Confidence threshold
- Recording duration

## 📁 Project Structure

```
ObjectDetectionYOLO/
├── main.py                 # Main detection system
├── web_dashboard.py        # Web interface
├── analytics_viewer.py     # Analytics dashboard
├── compile_alerts.py       # Video management
├── setup.py               # Setup script
├── requirements.txt       # Python dependencies
├── config.json           # Configuration file
├── coco.names            # YOLO class names
├── weights/              # Model weights (add yolov3.weights)
├── cfg/                  # Model config files
└── outputs/              # Auto-created for logs/clips
```

## 🎮 Keyboard Controls

- **Q** - Quit application
- **S** - Take screenshot

## 📧 Email Setup (Gmail)

1. Enable 2FA on your Gmail account
2. Create an [App Password](https://myaccount.google.com/apppasswords)
3. Update `EMAIL_CONFIG` in `main.py`

## 📊 Output Files

- `outputs/logs/` - CSV detection logs
- `outputs/clips/` - Alert video clips
- `outputs/screenshots/` - Captured screenshots
- `outputs/` - Analytics reports

## 🔍 Features Details

### ROI Monitoring
Define multiple zones to monitor specific areas:
```python
ROI_ZONES = [
    {"name": "Zone 1", "coords": (x, y, width, height), "color": (B, G, R)},
]
```

### Alert System
- Triggers when alert objects detected in ROI
- Records video clip (default 10 seconds)
- Sends email with video attachment
- Cooldown period between alerts

### Web Dashboard
- View recent alerts
- Download video clips
- Check detection statistics
- Real-time monitoring

## 📈 Analytics

Generate detailed reports:
- Detection over time
- Top detected objects
- ROI vs Non-ROI distribution
- Hourly activity heatmap
- Confidence distribution

## 🛠️ Troubleshooting

**Webcam not detected:**
```bash
python setup.py
```

**Out of memory with large videos:**
- Reduce frame buffer size in `main.py` line 65
- Use smaller resolution input

**Email not sending:**
- Verify App Password
- Check Gmail SMTP settings
- Disable firewall temporarily

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests.

## 📧 Contact

For questions or issues, please create an issue in the repository.

---

**Happy detecting! 🎯**