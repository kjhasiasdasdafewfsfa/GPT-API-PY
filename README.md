Chat Gpt API interface has been made public, which increases the playability of Gpt, 
which is convenient for us to add to the application to achieve intelligence.








First of all, I use the openai official website to publicly bind python to call the api interface method:
Show the first type of source code directly：gpt-api-py-1





1：But it should be noted that the "openai" library needs to be installed: directly in cmd "pip install openai”
2：In addition, the api key of openai needs to be obtained before the code calls the OPENAI API，
Then you also need to save the api key in the environment variable so that this code can carry the apikey for access when it runs.
environment variable added ‘OPENAI_API_KEY=your_api_key_here’，where the latter is your api key










The second is the official method：gpt-api-py-2











Similarly, you need to install the requests and json libraries，Then replace the api key and content
The first method is recommended here, and the second method is still a beta version
Creation is not easy,please add a star for me，guys！

