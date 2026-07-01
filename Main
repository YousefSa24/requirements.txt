from flask import Flask, request, jsonify
import os

app = Flask(__name__)

@app.route("/webhook", methods=["POST"])
def webhook():
    data = request.json
    user_msg = data['messages'][0]['text']['body']
    reply = f"وصلتني: {user_msg}. @AI.ps شغال 🔥"
    return jsonify({"messages": [{"text": reply}]})

@app.route("/", methods=["GET"])
def home():
    return "AI-PS Bot is running"

if __name__ == "__main__":
    port = int(os.environ.get("PORT", 3000))
    app.run(host="0.0.0.0", port=port)
