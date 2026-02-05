# 🤖 Form Bot - Advanced Google Form Automation

An intelligent automation tool for Google Forms with a modern cyberpunk-themed web interface. Built for testing, development, and research purposes.

## ✨ Features

- 🎯 **Smart Field Detection** - Automatically identifies and interacts with all form field types
- 🔄 **Random Response Generation** - Creates varied, realistic test data
- ⚡ **High Performance** - Fast execution with configurable timing controls
- 🎨 **Modern UI** - Cyberpunk-inspired interface with smooth animations
- 📊 **Analytics Dashboard** - Track success rates and performance metrics
- 🔒 **Secure** - Built with security best practices
- 🌙 **Headless Mode** - Run automations in background without visible browser

## 🛠 Technology Stack

- **Backend:** Python 3.8+, Flask
- **Automation:** Selenium WebDriver
- **Frontend:** HTML5, CSS3 (Custom Design)
- **Fonts:** Orbitron, Rajdhani, Space Mono
- **Browser:** Chrome/Chromium via WebDriver Manager

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.8 or higher
- Chrome browser
- pip (Python package manager)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/RabinGoswami/Google_Form_Bot.git
cd form-bot
```

### 2. Create Virtual Environment (Recommended)

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
flask==2.3.2
selenium==4.11.2
webdriver-manager==3.8.6
```

### 4. Project Structure

Organize your files as follows:

```
GOOGLE_FORM_BOT/
│
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
│
├── static/
│   └── style.css         # Cyberpunk-themed styles
│
└── templates/
    ├── base.html         # Base template
    ├── index.html        # Main dashboard
    ├── dashboard.html    # Analytics dashboard
    ├── history.html      # Execution history
    ├── settings.html     # Configuration
    ├── about.html        # About page
    ├── login.html        # Login page
    └── register.html     # Registration page
```

## 🎮 Usage

### Starting the Application

1. **Activate your virtual environment** (if not already active)
2. **Run the Flask application:**

```bash
python app.py
```

3. **Open your browser and navigate to:**
```
http://127.0.0.1:8000
```

### Using the Bot

1. **Navigate to the main dashboard** (automatically loads at `/`)
2. **Enter the number of responses** you want to generate (1-200)
3. **Click "Generate Responses"**
4. **Monitor progress** - The bot will:
   - Open the Google Form
   - Detect all field types
   - Fill in random data
   - Submit the form
   - Repeat for the specified count

### Configuration

Visit the **Settings** page to customize:

- **Submit Delay:** Time between each submission (2-10 seconds)
- **Page Load Timeout:** Maximum wait time for pages to load
- **Browser Mode:** Visible or headless operation
- **Text Randomization:** Simple, realistic, or custom responses
- **Retry Logic:** Enable/disable automatic retries
- **Logging Level:** Normal, verbose, or minimal

## 🎯 Supported Field Types

Form Bot intelligently handles:

- ✅ Text inputs (`<input type="text">`)
- ✅ Textareas (`<textarea>`)
- ✅ Radio buttons (`role="radio"`)
- ✅ Checkboxes (`role="checkbox"`)
- ✅ Dropdowns (coming soon)
- ✅ File uploads (coming soon)

## 📊 Analytics

Track your automation performance:

- **Total Runs:** Number of completed executions
- **Success Rate:** Percentage of successful submissions
- **Average Time:** Mean time per response
- **Total Responses:** Cumulative form submissions
- **Execution History:** Detailed logs with timestamps

## ⚙️ Advanced Configuration

### Customizing Response Data

Edit `app.py` to customize the data generation:

```python
# Example: Custom text responses
text_responses = [
    "This is a test response",
    "Automated data entry",
    "Sample form submission"
]

for text in driver.find_elements(By.XPATH, '//input[@type="text"]'):
    text.send_keys(random.choice(text_responses))
```

### Adjusting Timing

Modify timing parameters in your code:

```python
time.sleep(3)  # Wait 3 seconds after page load
time.sleep(random.randint(4, 6))  # Random delay between 4-6 seconds
```

### Headless Mode

Enable headless mode for server deployment:

```python
chrome_options.add_argument("--headless")
chrome_options.add_argument("--no-sandbox")
chrome_options.add_argument("--disable-dev-shm-usage")
```

## 🔒 Security Considerations

- ⚠️ **Authorization:** Only automate forms you have permission to test
- ⚠️ **Rate Limiting:** Respect form submission limits
- ⚠️ **Data Privacy:** Don't submit sensitive personal information
- ⚠️ **Terms of Service:** Comply with Google Forms ToS

## 🐛 Troubleshooting

### Common Issues

**ChromeDriver not found:**
```bash
pip install --upgrade webdriver-manager
```

**Element not clickable:**
- Increase page load timeout
- Add more explicit waits
- Check for overlapping elements

**Form not submitting:**
- Verify the submit button XPath
- Check if CAPTCHA is present
- Ensure all required fields are filled

**Port already in use:**
```bash
# Change port in app.py
app.run(host="127.0.0.1", port=8001, debug=True)
```

## 📝 Best Practices

1. **Test Responsibly:** Only use on your own forms or with explicit permission
2. **Start Small:** Begin with a low response count to verify functionality
3. **Monitor Performance:** Check the dashboard regularly for error rates
4. **Use Realistic Delays:** Mimic human behavior with appropriate timing
5. **Review Logs:** Check execution history for any anomalies

## 🎨 Customizing the UI

The interface uses a cyberpunk aesthetic with:

- **Color Scheme:** Neon cyan (#00fff2), magenta (#ff006e), yellow (#ffbe0b)
- **Fonts:** Orbitron (headers), Rajdhani (body), Space Mono (code)
- **Animations:** Smooth transitions and micro-interactions
- **Theme:** Dark mode with glowing accents

To customize, edit `/static/style.css` and modify CSS variables:

```css
:root {
    --neon-cyan: #00fff2;
    --neon-magenta: #ff006e;
    --neon-yellow: #ffbe0b;
    /* ... more variables */
}
```

## 🔮 Future Enhancements

- [ ] Multi-form support
- [ ] Scheduled automation
- [ ] Export analytics to CSV/PDF
- [ ] User authentication system
- [ ] API endpoints
- [ ] Docker containerization
- [ ] Cloud deployment guides

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

This tool is designed for **legitimate testing, development, and educational purposes only**. Users are responsible for ensuring they have proper authorization before automating any form submissions. The developers assume no liability for misuse of this software.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Contact: your.email@example.com

## 🌟 Acknowledgments

- Flask framework for the web backend
- Selenium for browser automation
- Google Fonts for typography
- The open-source community

---

**Built with ❤️ for automation enthusiasts**

*Version 2.0.0 - Cyberpunk Edition*
