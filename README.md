# Hello 👋

Its’ finally here 🎉, I’m incredibly excited to announce my first web-dev project – [PyOoshi](https://pythongeneration.ooshimus.com). [PyOoshi](https://pythongeneration.ooshimus.com) came after a week of hard work learning HTML, CSS and JS from scratch leading to my first project. After trial and error, organisation and lots of SO I came to my final project✨️

In the spirit of open-source, I've released my project on  [Github](https://github.com/Aiyush-G/CodeGenerator) under the [Common Clause](https://commonsclause.com) license. If you would like to make a change then feel free to do so and create a pull request, thanks.


![pyOoshi.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628521566696/AcKb-lwvy.png)

# Why?
I will be the first to admit it, learning a new language (never mind Stack) can be daunting, especially when you don’t know where to start. With this in mind, I attempted to solve 2 problems at once 1. Learn a new stack 2. Create an educational tool to help people learn a new programming language. 

Although the project doesn’t yet work perfectly (I need to add more context to my model) it demonstrates perfectly what you can create in the same week of starting Web Dev  🚀

![That's Progress Gif](https://media4.giphy.com/media/3o7TKLy0He9SYe8niE/200.gif)

# Introducing [PyOoshi](https://pythongeneration.ooshimus.com) ✨️
[PyOoshi](https://pythongeneration.ooshimus.com) is a powerful, experimental and easy-to-use code generation toy project that successfully generates beautiful code just by inputting some general prompt. Whilst this project was created in <6 hours it is fully functional and I thought the best way to demonstrate what is possible with a little dedication. It can handle simple prompts such as “make a password generator” or “covert Celsius to Fahrenheit” but struggles with more ambiguous and general tasks. 

# Inspiration 👀
After getting access to GPT-3 last year, I was fascinated by the tasks it could complete and how rapid and accurate its’ output was. Ever since, I have been waiting for ‘Open’-AI to release an open-source version or someone to recreate it. Along came GPT-J-6B, read my blog post about it here. https://ooshimus.com/is-gpt-3-still-king-introducing-gpt-j-6b 

Combined with a few google searches, I knew it was possible so it was my turn to give it a crack. There was one small problem though, I had never touched HTML, CSS or JS beyond the classic inspect-element to change my score on online HTML5 games.

%[https://analyticsindiamag.com/open-ai-gpt-3-code-generator-app-building/ ]
%[https://becominghuman.ai/gpt-3-and-code-generation-ai-enabled-instant-software-development-270795077cbd?gi=ee8848901a8e ]
%[https://youtu.be/z8K07a2EIcE]

# How to Use?
Visit  [PyOoshi](https://pythongeneration.ooshimus.com) , you will see the UI (created using Tailwind – which I love), you can ignore the options at the top for now and you can enter something like `Divide A by B and store it in result` and then click on the `go` button. You will see the web-page load, it may take up to 60 seconds if under heavy load. At the moment, it works better on Desktop than mobile since I am having issues with the responsiveness (which works on localhost) but not upon deployment. 

# Local Development
Clone the files, run main.py and install dependencies (all in main.py).

![screenshot-rocks.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628521587064/B_yGv95ir.png)

## Prompt Guide
**Showing**, not just **telling**, is the secret to a good prompt. Even people familiar with machine learning accustomed to chatbots and single-purpose text models can get confused by this. The API’s power is its adaptability. The key to unlocking this adaptability is in learning how to show it what you want. The API tries to guess what you want from the prompt. If type the words “Give me a list of numbers,” the AI (GPT-J-6B), wouldn’t automatically assume that you’re asking for a list of numbers. You could just as easily be asking the API to continue a conversation where the first words are “Give me a list of numbers and ensure they are miltiples of 2.” If the API only assumed that you wanted a list of numbers it wouldn’t be as good at classification or code generation
**TL;DR Keep It Simple**

![Keep It Simple](https://media1.tenor.com/images/5f5f6df9624301ebea3abdec1af4cd4a/tenor.gif?itemid=9276124)

**Examples:**
Divide A by B and store it in result 
Generate the sine values from 0 to 1. 
Convert input from Celcius to Farenheit 
Perform a google search of what the user wants and print the top result 
Print what part of the day is going on right now 
Make a password generator

**Output**
Once the output has been generated, you will see it in the green `output` box. Note, if your output has tonnes of random text at the bottom of it, or cuts of randomly then carry on reading to learn about setting `max-tokens`, `temperature` and `max-probability`

**Token**
Recommended max amount of tokens is 2048, this is the maximum output length in characters including spaces.

**Temperature**
Controls how random the model is, recommended setting > 1.0 
A higher temperature means more creativity and a low temperature means less changes will be made when completing the prompt. The value must be a float.

**Probability**
An alternative method to setting the creativity if the temperature is set then probability must equal 1, vice-vera.

# Built With:
-  [Python ](https://www.python.org) 
-  [HTML](https://html5.org) 
-  [Tailwind](https://tailwindcss.com) 
-  [JS](https://www.javascript.com) 

![HTML CSS JS](https://media4.giphy.com/media/fuJPZBIIqzbt1kAYVc/giphy.gif)

# Planning, Coding, Deploying 🏗️

- Planning
All I needed was a piece of paper and a pen, I quickly sketched out a rough wireframe and looked at the pre-existing components of DaisyUI and built it around that. Since it was all input and buttons, I could be quite flexible in the layout. I built it using a mobile-first approach, however, this stopped working on deployment and my responsive aspects aren’t happening. If anyone knows why this is happening then please reach out.

- Coding
I had spent 5 days learning HTML, CSS and JS by following an array of tutorials on YouTube. Now, I was ready to get started. 

**Building with Tailwind**
I had two options, to use the CDN or the CLI. Since the CDN is much heavier than the CLI and lacked some important features for this project, I decided to use the CLI. However, to setup the CDN just add this to your head.

```
<link href=https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css
```
 

1. 
 To use the CLI, you should create a project structure 

```
.
└── Project/
    ├── css/
    │   └── tailwind.css
    └── index.html
```
2.
You should populate `css/tailwind.css` with 
 
```css
@tailwind base; /* Entry Point Directive */
@tailwind components; 
@tailwind utilities; 
```
This is the entry point directive

3.
`npx tailwindcss-cli build -i css/tailwind.css -o build/tailwind.css` This processes your css into a build directory .

`npm init -y`
`npm install -D tailwindcss postcss autoprefixer vite` Install the required libraries, vite provides us with a server to see our changes in real time.

4.
To reflect the installation of vite I adjusted the `package.json` with a new script.
``` 
{
  "name": "TailwindLabsCSS",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "vite" // Change here
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "autoprefixer": "^10.3.1",
    "postcss": "^8.3.6",
    "tailwindcss": "^2.2.7",
    "vite": "^2.4.4"
  }
}
```

5.
Generate the configuration file, this is where we can install plugins etc…
npx tailwindcss init -p 

6. 
`npm i daisyui`  The daisyUI library provides a great way to rapidly prototype designs.

7. 
Lastly, link the CSS file in your index.html in the root project directory.
<link href="/css/tailwind.css" rel="stylesheet">

8. 
Start the Vite development server using `npm run dev` 

Since I had setup tailwind after familiarising myself with the documentation & framework, I started to code out the frontend.

Once I had finished with the frontend it looked like this (with a different colour theme applied):

%[https://play.tailwindcss.com/ovm8uPV94r]

<iframe src="https://play.tailwindcss.com/ovm8uPV94r " style="border:0px #ffffff none;" name="myiFrame" scrolling="no" frameborder="1" marginheight="0px" marginwidth="0px" height="650px" width="100%" allowfullscreen></iframe>

<br>

# Connecting the frontend to Python

Connecting to python was a challenge at first since I had no idea how to use tailwind with Flask, luckily I found this:

%[https://www.section.io/engineering-education/integrate-tailwindcss-into-flask/]

![HTML CSS JS](https://media1.giphy.com/media/KAq5w47R9rmTuvWOWa/giphy.gif)

Soon enough, I had created my API and by using `post` and `get` methods on my `@app.route` I could quickly access form fields by their names with ` maxTokens = int(request.form.get('maxTokens'))`, this was some repetition after this and adding authentication to ensure valid responses. Ie. ` maxTokens = 2048 if maxTokens<2048 else maxTokens`.

# Deploying 🚀
I have a  [repl.it](https://replit.com/~)  hacker account so I quickly reproduced my steps on repl.it and within 5 minutes of tinkering and realisation that I could use a custom subdomain of ooshimus.com I quickly got the site up and running. Although this is in very early stages, if you would like to help develop this then just reach out on  [LinkedIn](https://www.linkedin.com/in/aiyush-gupta-2006/)  / [GitHub](https://github.com/Aiyush-G) . Overall, this is my first frontend project and I am quite proud of it.

![Deploy](https://media3.giphy.com/media/mi6DsSSNKDbUY/giphy-downsized-large.gif) 

# Wrapping it up🎁

Thanks 👏👏👏 for reading until the end, I am happy with my project overall and I wouldn’t have been able to do it without all the great content-creators out there. If you have further feedback / enhancements then please comment them down below.

In the spirit of open-source, I've released my project on  [Github](https://github.com/Aiyush-G/CodeGenerator) under the [Common Clause](https://commonsclause.com) license. If you would like to make a change then feel free to do so and create a pull request, thanks.
