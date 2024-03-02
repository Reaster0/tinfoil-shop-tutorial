
# tinfoil-shop-tutorial

This is a homemade tutorial on how to run your own instance of a tinfoil shop (just like pixel shop and such) 

## TLDR: i just want to run the project don't try to teach me anything!

Clone the project

```bash
  git clone https://github.com/Reaster0/tinfoil-shop-tutorial.git
```

Go to the project directory

```bash
  cd tinfoil-shop-tutorial
```

- Add the ```prod.keys``` file in the library-manager directory

Launch the docker-compose

```bash
  docker compose up --build -d
```

- Add your nsp/nsz/xci games to the new "games" folder

(Ocasionally) restart the server to update the newly added files

```bash
  docker compose restart
```
or
```bash
  docker-compose restart
```

#### everything is now accessible at your local ip (or localhost) at the port : 8000
```
http://my-local-ip:8000
```
## How does it work?

it's actually simple, i won't go into the detail of how the tinfoil webserver is running in itself but more in HOW you deploy it (so you can deploy any versions or type of tinfoil-web-server)
#### in short it's two services, ```tinfoil-web-server``` that run the server in itself and ```library-manager``` that will rearrange correctly our library
- the tinfoil-web-server that will be used here is this one : ```https://github.com/Myster-Tee/TinfoilWebServer/```
- the library-manager that will ve used here is this one: ```https://github.com/giwty/switch-library-manager```

### As the dockerman i command you to raise

we will use a very used tool named docker compose that is an orchestrator of containers, but john what's a containers? we'll it's like a tiiiiny virtual computer os (like your shitty windows but better because it's linux and it's also tiny), so you can run your programs not in your ""own computer"" but on a "smol virtual computer in a big computer" (so it will run on any computer (windoshit, macos, linux), that's the point)

so we make a docker compose file ```docker-compose.yml``` 

in it you'll find a description of the services that we want to run and how (read the comments there)
```the game directory that we mount is "games" by default```
- but what is a dockerfile?
well it's the file in wich we will say what our "smol virtual computer in a big computer" is

### As the dockerfile i raise
so we have a dockerfile in each directory, it's composed of command that it run in the smol linux to get us the programs that we need to run the program (yeah we need programs to run programs, funny isin't it?)
```don't worry if you don't understand much, it's the same for my parents when i explain to them my job```
- once the docker have builded they will stay in cache and it will be faster to relaunch the app after

### How do i run this blackmagic fuckery?
well it's easy, first of all
- step 1
you can download the files using git (if you know how to do it), else you can download the files as a zip using the green "code" button, then you will need to have docker and docker-compose installed on your computer, you can install docker-desktop to have both if you are on windoshit or macos there ```https://www.docker.com/products/docker-desktop```, if you are on linux, well do it yourself chad

- step 2
modify the config files at your will, you don't have much to change for library-manager but for the tinfoil-web-server you can change the welcome message of your server and also the user/password (you can set many if you want)
- by default its ```user: macron pswd: demission```
add the ```prod.keys``` file in the library-manager-dir, without it the program will try to guess the game from the name and it won't work well, i suppose that you know where to find this file right?

- step 7
open the terminal/cmd, go to the directory of the project (where the docker compose file is) then...

Launch the docker-compose

```bash
  docker compose up --build -d
```
or
```bash
  docker-compose up --build -d
```

- Add your nsp/nsz/xci games to the new "games" folder

(Ocasionally) restart the server to update the newly added files

```bash
  docker compose restart
```

#### everything is now accessible at your local ip (or localhost) at the port : 8000
```
http://my-local-ip:8000
``` 

the containers will run in the background while docker is running (even if you restart your computer the containers will re up themselves)
if you want to stop them just use the following command:
```
  docker compose down
```
or
```
  docker-compose down
```


## wasen't so hard no?

### if you have found this tutorial helpfull you can always tip me some monero (they're soo crunchy) : ```46gXH9dmfReixASkA5c8jN9eR6At4ZSJBQ5DqWkaAEMsLXquiWQQuBe4D8wVT2Utuh54bDTHnF1ScjBT3vUtAgUX1uu5Baw``` cheers mates!