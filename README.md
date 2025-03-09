- 👋 Hi, I’m @Gensimmy
- 👀 I’m interested in ...
from flask import Flask, request
from twilio.twiml.messaging_response import MessagingResponse

app = Flask(__name__)

@app.route("/whatsapp", methods=['POST'])
def whatsapp_reply():
    incoming_msg = request.values.get('Body', '').lower()
    resp = MessagingResponse()
    msg = resp.message()

    if 'hello' in incoming_msg:
        msg.body("Hi! How can I help you?")
    else:
        msg.body("I'm a bot, reply with 'hello' to start!")

    return str(resp)

if __name__ == "__main__":
    app.run(debug=True)

<!---
Gensimmy/Gensimmy is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
