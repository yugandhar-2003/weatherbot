!pip install gradio requests

import requests
import gradio as gr

# ✅ WeatherAPI + UltraMsg Setup
WEATHER_API_KEY = ""
INSTANCE_ID = ""
TOKEN = ""
TO_PHONE = "918309359937"  # Replace with your WhatsApp number

# 🌤️ Get weather using WeatherAPI
def get_weather(city):
    url = f"https://api.weatherapi.com/v1/current.json?key={WEATHER_API_KEY}&q={city}"
    try:
        response = requests.get(url)
        data = response.json()

        # ❌ Error from WeatherAPI
        if "error" in data:
            return None, f"⚠️ API Error: {data['error']['message']}"

        return data, None
    except Exception as e:
        return None, f"❌ Exception: {str(e)}"

# 📝 Format the weather message
def generate_message(data):
    name = data['location']['name']
    country = data['location']['country']
    temp = data['current']['temp_c']
    condition = data['current']['condition']['text']
    humidity = data['current']['humidity']
    suggestion = "☀️ Stay hydrated!" if temp > 30 else "🌤️ Nice weather today!"

    return (
        f"🌦️ *Weather Update*\n"
        f"📍 *{name}, {country}*\n"
        f"🌡️ Temperature: {temp}°C\n"
        f"💧 Humidity: {humidity}%\n"
        f"🌈 Condition: {condition}\n"
        f"{suggestion}"
    )

# 📲 Send to WhatsApp via UltraMsg
def send_whatsapp_message(message):
    url = f"https://api.ultramsg.com/{INSTANCE_ID}/messages/chat"
    payload = {
        "token": TOKEN,
        "to": TO_PHONE,
        "body": message
    }
    try:
        response = requests.post(url, data=payload)
        return response.status_code == 200
    except Exception as e:
        print("❌ WhatsApp error:", e)
        return False

# 🎛️ Gradio function
def weather_to_whatsapp(city):
    data, error = get_weather(city)
    if error:
        return error, "❌ API Error"

    message = generate_message(data)
    success = send_whatsapp_message(message)
    status = "✅ Message sent to WhatsApp!" if success else "⚠️ Failed to send message."
    return message, status

# 🎨 Gradio Interface
gr.Interface(
    fn=weather_to_whatsapp,
    inputs=gr.Textbox(label="Enter City Name (e.g., Hyderabad)"),
    outputs=[
        gr.Textbox(label="Weather Info"),
        gr.Textbox(label="WhatsApp Send Status")
    ],
    title="🌦️ Weather WhatsApp Bot",
    description="Type a city to get live weather info sent to WhatsApp using WeatherAPI + UltraMsg."
).launch(share=True)
