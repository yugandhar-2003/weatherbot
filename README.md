
# 🌦️ Weather WhatsApp Bot with Gradio
real-time weather updates sent directly to your WhatsApp by typing any city name in a simple Gradio interface.

## 📌 Features

* ✅ Real-time weather using **[WeatherAPI.com](https://www.weatherapi.com/)**
* 💬 Sends a WhatsApp message using **UltraMsg API**
* 🎛️ Beautiful web UI built with **Gradio**
* 🌡️ Includes temperature, humidity, weather condition, and a smart suggestion

---

## 🚀 Demo

**Input:**
`Hyderabad`

**WhatsApp Output:**

```
🌦️ Weather Update  
📍 Hyderabad, India  
🌡️ Temperature: 31°C  
💧 Humidity: 52%  
🌈 Condition: Sunny  
☀️ Stay hydrated!
```

---

## 🔧 Technologies Used

| Tech              | Purpose                    |
| ----------------- | -------------------------- |
| WeatherAPI        | Fetch current weather data |
| UltraMsg          | Send WhatsApp messages     |
| Gradio            | Web UI in Google Colab     |
| Python (requests) | API calls and logic        |

---

## 📁 How to Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/)
2. Copy-paste the full code from your `main.py` or the notebook
3. Replace the following placeholders:

```python
WEATHER_API_KEY = "your_weatherapi_key"
INSTANCE_ID = "your_ultramsg_instance_id"
TOKEN = "your_ultramsg_token"
TO_PHONE = "whatsapp_number_with_country_code"
```

4. Run all cells.
5. Click the `Gradio` link to open the interface.
6. Type any city name and submit.

---

## 🔐 API Setup

### 📍 Get WeatherAPI Key

* Sign up at [https://weatherapi.com](https://www.weatherapi.com/)
* Go to Dashboard → Create Key → Copy and paste in code

### 💬 Get UltraMsg API Details

* Sign up at [https://ultramsg.com](https://ultramsg.com/)
* Create an instance
* Get:

  * Instance ID
  * Token
  * Connect your WhatsApp (scan QR code)
  * Add your `TO_PHONE` number (with country code, e.g., 91 for India)

---

## 📦 Future Ideas

* ⏰ Schedule daily weather alerts at 8AM
* 🌐 Add multi-language support (e.g., Telugu, Hindi)
* 📍 Support weather by GPS location
* ⚠️ Add rain or UV alerts

---

## 🙌 Author

Built with ❤️ by **Yugandhar**
Feel free to fork or contribute!

---
