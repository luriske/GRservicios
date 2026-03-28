from flask import Flask, request
import requests

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    data = request.json

    try:
        message = data.get('messageData', {}).get('textMessageData', {}).get('textMessage')
        image = data.get('messageData', {}).get('fileMessageData', {}).get('downloadUrl')

        print("Mensagem:", message)
        print("Imagem:", image)

    except Exception as e:
        print("Erro:", e)

    return "ok"

app.run(host='0.0.0.0', port=5000)
