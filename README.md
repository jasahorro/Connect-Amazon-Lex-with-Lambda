<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Connect Amazon Lex with Lambda

**Project Link:** [View Project](https://nextwork.ai/projects/05a8853b-a1e0-5be3-a93f-adeecd72e61c)

**Author:** Maria Jasmin Ahorro

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate how to connect an Amazon Lex chatbot to an AWS Lambda function using fulfillment code hooks so that BankerBot can dynamically generate and return a random bank balance to the user. I'm doing this project to learn how to integrate serverless code with conversational AI models, configure bot aliases, and handle complex backend logic during chat interactions.

### ✍️ What are we doing in this step?

In this step, I will set up a new Lex chatbot (BankerBot) and recreate its foundational components including the WelcomeIntent, a custom-customized FallbackIntent, and the CheckBalance intent featuring an accountType custom slot because we need a fully functioning baseline chatbot in place before we can connect it to an external AWS Lambda function for backend fulfillment.

### ✍️ What are we doing in this step?

In this step, I will create a new AWS Lambda function named BankingBotEnglish using Python 3.12, paste the provided Python source code to handle random bank balance generation, and deploy the function because we need a serverless backend calculator ready to supply account balance figures when triggered by Amazon Lex.

### What is Amazon Lex?

Amazon Lex is a fully managed artificial intelligence service with advanced natural language models designed for building conversational interfaces and chatbots into any application. It is useful because it enables developers to build, test, and scale lifelike conversational bots quickly using voice and text without needing to manage complex underlying natural language processing (NLP) infrastructure.

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to build a conversational interface for a banking chatbot (BankerBot), define intents and custom slots, and connect it with an AWS Lambda function via a fulfillment code hook so it can dynamically generate and return a random bank balance to users.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how smoothly Amazon Lex and AWS Lambda integrate to handle backend logic in real-time, instantly converting user inputs into customized conversational responses like generated bank balances without needing to build complex server infrastructure from scratch.

### This project took me...

This project took me 20 minute to complete, giving me hands-on practice connecting conversational AI interfaces in Amazon Lex with serverless backend logic in AWS Lambda.

### ❤️ Thanks for doing this project!

I chose to do this project today because I wanted to learn how to bridge conversational AI interfaces in Amazon Lex with serverless backend logic in AWS Lambda to build practical, real-world applications. Something that would make learning with NextWork even better is having more interactive troubleshooting sandboxes where we can practice debugging common IAM and Lambda permission errors live.

## AWS Lambda Functions

AWS Lambda is a service that lets you run code in the cloud without needing to manage any computers or servers—Lambda manages them for you. It is useful because it runs your code only when needed and scales automatically, from a few requests per day to thousands per second, allowing you to easily handle backend logic like generating bank balances on the fly.

In this project, I created a Lambda function to dynamically generate a random bank balance and return it to Amazon Lex whenever a user asks to check their account balance, bridging the gap between the conversational interface and the serverless backend logic.

### ✍️ What are we doing in this step?

In this step, I will connect the default TestBotAlias of our BankerBot to the BankingBotEnglish AWS Lambda function because we need to create a pointer and established link between Amazon Lex and our serverless backend so that the bot knows which function to trigger during conversations.

![AWS Lambda Functions](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_97dc2351)

## Chatbot Alias

An alias is a pointer for a specific version of your bot, allowing external applications and AWS services to connect to a stable reference point rather than directly to the draft or latest version, making updates seamless.

TestBotAlias is a default version of your bot created specifically for testing and development, serving as a playground version to ensure everything works smoothly before rolling out updates to production.

To connect Lambda with my BankerBot, I visited my bot's TestBotAlias, selected the English (US) language support panel, and linked the source to the BankingBotEnglish Lambda function using the $LATEST version so that Amazon Lex can trigger our backend code seamlessly.

### ✍️ What are we doing in this step?

In this step, I will navigate to the CheckBalance intent in Amazon Lex, expand the fulfillment panel, and check the box to use the BankingBotEnglish Lambda function for fulfillment under advanced options because we need to create a direct link between the intent and our serverless code so that Lex can invoke the function to calculate and return the bank balance once all required slots are collected.

![Chatbot Alias](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_c4fc89af)

## Code Hooks

A code hook is a mechanism that connects your chatbot to custom AWS Lambda functions to perform specific tasks or handle complex actions during a conversation—such as checking data from a database or running backend fulfillment logic—that the basic chatbot setup cannot handle on its own.

Even though I already connected my Lambda function with my chatbot's alias, I had to use code hooks because the alias link only tells Lex where to find the Lambda function globally, whereas code hooks specifically tell Lex which individual intent (like CheckBalance) has permission to trigger that backend code and when to invoke it during the conversation.

I could find code hooks at the bottom of the Fulfillment panel inside the specific intent configuration (such as CheckBalance), under Advanced options where the Lambda function for fulfillment is enabled.

![Code Hooks](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_505be5b9)

## The final result!

I've set up my chatbot to trigger Lambda and return a random dollar figure when a user asks to check their account balance, provides their account type (like Credit or Savings), and completes the date of birth verification step.

![The final result!](https://nextwork.ai/overjoyed_magenta_proud_yak/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_505be5b8)
