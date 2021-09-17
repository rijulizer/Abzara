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

