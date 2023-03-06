# GPT-API-PY
Chat gpt api in python
Chat Gpt API interface has been made public, which increases the playability of Gpt, 
which is convenient for us to add to the application to achieve intelligence.
First of all, I use the openai official website to publicly bind python to call the api interface method:
Show the first type of source code directly：
import openai
import os
#Replace here with your api key
openai.api_key = os.environ["OPENAI_API_KEY"]
def generate_text(prompt, model, max_tokens, temperature):
    response = openai.Completion.create(
        engine=model,
        prompt=prompt,
        max_tokens=max_tokens,
        temperature=temperature
    )
    return response.choices[0].text
#Here is what you want to ask gpt
prompt = "Hello, my name is"
model = "text-davinci-002"
max_tokens = 50
temperature = 0.5
generated_text = generate_text(prompt, model, max_tokens, temperature)
print(generated_text)
1：But it should be noted that the "openai" library needs to be installed: directly in cmd "pip install openai”
2：In addition, the api key of openai needs to be obtained before the code calls the OPENAI API，
Then you also need to save the api key in the environment variable so that this code can carry the apikey for access when it runs.
environment variable added ‘OPENAI_API_KEY=your_api_key_here’，where the latter is your api key
The second is the official method：
import requests
import json
def gpt(url,headers,body):
    response = requests.post(url=url,headers=headers,body=body)
    json_data = json.loads(response.text)
    content = json_data["choices"][0]["text"].strip()
    return content
url = "https://api.openai.com/v1/chat/completions"
headers = {
    'Content-Type': 'application/json',
    #Authorization is your api key
    'Authorization': 'Bearer YOUR_API_KEY'
}
body={
    "model": "gpt-3.5-turbo",
    #content that's what you're asking
    "messages": [{"role": "user", "content": "Hello!"}]
}
print(gpt(url,headers,body))
1：Similarly, you need to install the requests and json libraries，Then replace the api key and content
The first method is recommended here, and the second method is still a beta version
Creation is not easy,please add a star for me，guys！
