# Abzara
## _The HR chat-bot for Abzooba_

Abzara is an chatbot built with RASA to handle HR related FAQ absed questions. 

## Features

- We have tested the chatbot locally
- For frontend we used [chatroom](https://github.com/scalableminds/chatroom), an opensource UI
- Abzara connects seamlessly with MS Teams 
- Dcoker based conatiners can be used for deployement


## Installation
To run in local mode
clone the repo and create a conda venvironment
```sh
git clone [repo](https://github.com/rijulizer/Abzara)
conda create -n env_name python=3.8
conda activate env_name
pip install -r requirements.txt
```

To run the model

```sh
cd location
rasa shell
```



#### Connection to Front End

For production release:

run the abzara_front_end_chatroom.html file
## How to connect the bot to Microsoft Teams:
- Step 1: Make sure that you have MS teams installed on your system. Then open MS teams and login through the Microsoft credentials. Once you are logged in you can see the “Apps” icon on the bottom left on the application, just click on it.
- Step 2: In the search bar, search for the “App Studio” and click on it. Then a pop-up window will open asking you to create it or to open it if you have already created it before.
- Step 3: Now, a new window will appear, go to “Manifest editor” and select “Create a new app”.
Now fill the app details as shown here in the image.
- Step 4: Now, go to Bots and setup the endpoint for the rasa chatbot which is alive and ready to talk to. Here you will get the app_id and app_password (after generating), that you need to setup in the credentials.yml file of the rasa chatbot. After you will add the credentials you will have to rerun the rasa application to take the changes to effect.
- Step 5:Here you have to setup the endpoint, and the endpoint should be the SSL certified, and it will be of below format:
```sh
https://<domain-name>/webhooks/botframework/webhook
```
- Step 6: Once you have added the endpoint, just verify it. If it is verified successfully that means you chatbot alive and have established the successful connection and we are good to go.
- Step 7: Now go to Test and distribute. Here on the right side you will get the description. If it is empty that means everything is proper and now you can download the app (it will download zip file) and install it.


## Docker

Abzara is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd Abzara
docker build -t abzara:img_1 .
```

This will create the image and pull in the necessary dependencies.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
run command: docker run -it -p 8080:8080 abzara:img_1 rasa run --credentials ./credentials.yml  --enable-api --auth-token XYZ123 --model ./models --endpoints ./endpoints.yml --cors "*"

```

> Note: `change commands after run based on requirement'

## License

MIT

