# Custom-Search-Engine-with-Exa
This project is a web-based custom search engine built using Python and React, powered by the Exa API. It aggregates results from across the internet and displays them in a user-friendly interface.
# Introduction
Imagine this: you saw a hilarious tweet (probably one of ours 😎), but now you can't remember who posted it or where you saw it. Bummer, right? What if there was a smart search engine that could help you find exactly what you're thinking of?

Thanks to natural language processing (NLP), that's now possible. NLP is a field of machine learning that enables computers to understand, interpret, and even generate human language.

In this guide, we’ll show you how to build a custom search engine using an API enhanced with LLM (Large Language Model) features. 🚀

![image](https://github.com/user-attachments/assets/a127f2b1-0193-4e74-a1fb-e37109dba69e)
LLMs are powerful models trained on massive datasets that can comprehend the subtleties of human language. One popular example is GPT-3.

LLMs work by predicting the likelihood of a word or sequence of words, which is called tokenization — breaking down text into smaller, meaningful chunks.

Training these models can be very resource-intensive, but APIs give us easy access to their capabilities. Through them, we can tap into tools for text generation, translation, summarization, and more.

Let’s dive in and build a smart search engine! 👀

## What is Exa API?
Exa (previously known as "Metaphor") is a semantic search API that finds the most relevant content on the web. It doesn’t just match exact words like Google does — it understands your intent and meaning.

Exa uses LLMs at its core to process and understand natural language, making it super useful for rediscovering content based on meaning rather than keywords.

In this tutorial, we’ll use Exa’s capabilities to create a simple yet powerful search tool that can return highly relevant results.

# Getting Set Up
To get started, create an account on Exa to receive your API key — you’ll get 1000 free requests right off the bat. Once signed in, head to the “Overview” page to grab your key.
![image](https://github.com/user-attachments/assets/1b3ee402-7803-4b39-88d3-e3c9dc30b8fe)
⚠️ Important: Always keep your API key safe and never share it publicly!

Make sure you have Python 3 and pip installed. Open your preferred code editor (we suggest VS Code) and create a new file named main.py.

## Installing Packages and Imports
With Python installed, let's go ahead and use pip to download Exa:

<pre> ```pip install exa_py``` </pre>


Title Image
Build a Custom Search Engine with Exa
Prerequisites: Python fundamentals, Command Line
Versions: Python 3.10
Read Time: 45 minutes

# Introduction
Picture this: You read a funny tweet (probably ours...), but you forgot who tweeted it and where you saw it. You’re sad. What if there was a search engine that rediscovers exactly what you’re thinking about?

It's now possible with a specific kind of machine learning called natural language processing (NLP). It teaches computers to understand, interpret, and generate human language.

In this tutorial, we'll build a custom search engine using an API with LLM capabilities! 🚀

LLMs (short for large language models) are a powerful tool within the broader field of NLP. These models are trained on insane amounts of data and can grasp the intricacies of human language. 🤯 A popular LLM that you might already be using is GPT-3.

Tokenization Example
LLMs leverage deep learning techniques to generate text, translate languages, answer questions, and so much more. The model estimates the probability of a token or a sequence of tokens in a sequence. A token refers to a unit of language extracted from a larger piece of text.

However, accessing LLMs is a little tricky since training models is both time-consuming and expensive. APIs solve this. APIs serve as a tool to access NLP tasks, such as text generation, translation, summarization, and more, which we'll explore today!

Let's learn how we can even build our very own custom search engine! 👀

## Exa API
Exa (formerly "Metaphor") is an API (application programming interface) that retrieves the best content on the web. With Exa, anyone can semantically search the web to get high-quality, relevant information. With Exa's technology, we can rediscover the content on the internet. Unlike Google, which relies on keyword search (matching the exact words of the query to the web content), Exa can understand both the user's input and the content out there. Wow, right?

Exa utilizes LLMs as a core component, and has been extensively trained to help computers understand human language.

In this tutorial, we will use Exa's capabilities to build a basic search engine that can help you find exactly what you are searching for.

# Set Up
First, we need to create an Exa account to access an API key for building out the "search" functionality of our search engine! You'll automatically get 1000 free requests just for signing up. After creating an account, navigate to "Overview" to retrieve your API key.

Exa Dashboard
Note: Keep your API keys private and safe and avoid sharing and posting them online. 🔒

For this project, we'll need Python 3 and pip (package installer) installed.

Assuming that we have those two installed, let's open up our preferred code editor (we recommend VS Code) and create a new file called main.py.

## Packages and Imports
Use pip to install the Exa Python package:
<pre> ```pip install exa_py``` </pre>


If that doesn’t work, try:
<pre> ```pip3 install exa_py``` </pre>

In our main.py file, we're going to import Exa, and initialize Exa with our API key!

<pre> ```from exa_py import Exa

exa = Exa('YOUR_KEY_HERE')``` </pre> 
# Performing a Search
In the same file, let's create a variable called query, which will hold the response to the input of what we want to search!
<pre> ```from exa_py import Exa

exa = Exa('YOUR_KEY_HERE')

query = input('Search here: ')``` </pre>
Now, let's take a look at Exa's .search() function:

<pre> ```from exa_py import Exa

exa = Exa('YOUR_KEY_HERE')

query = input('Search here: ')

response = exa.search(
  'Best Chicago cold brew',
  num_results=10,
)``` </pre>
Here's one result (of 10) from the returned data for searching "Best Chicago cold brew":

<pre> ```{
  "score": 0.1940334290266037,
  "title": "13 Innovative Cold Brew Drinks from Coffee Shops Around the Country",
  "id": "https://www.thrillist.com/drink/nation/best-cold-brew-coffee-drinks",
  "url": "https://www.thrillist.com/drink/nation/best-cold-brew-coffee-drinks",
  "publishedDate": "2017-07-10",
  "author": "Dan Gentile"
},``` </pre>
For each search result, we get:

score: The score associated indicates its relevance within the query system; higher scores mean greater relevance.
title: This is the name of the article/blog/website.
id & url: The link to the result's web page.
publishedDate: This lists the publish date.
author: This credits a writer. This will return "None" if there is no credited writer.
To customize our Exa results further, we can play around with Exa's filters to find the exact type of content we need. You can explore the filters here Exa's API Search documentation.

Here are some of our favorite filters:

numResults: Number of search results to return.
includeDomains: List of domains to include in the search.
category: A data category to focus on, with higher comprehensivity and data cleanliness. Categories right now include company, news, pdf, papers, tweet, GitHub, movies, songs, and personal sites.
The search example below will return 10 results for "best pizza in Brooklyn" searching through Twitter since May 2023:

<pre> ```response = exa.search(
  'best pizza in Brooklyn',
  num_results=10,
  start_published_date='2023-05-01', 
  category='tweet', 
  use_autoprompt=True,
)``` </pre>
# Search Coffee on TikTok
This is where the fun customization begins! ✨💖

For this tutorial, you'll learn how to search TikTok to obtain top coffee drink accounts!

In our case, we will want only the top 5 search results, and only from https://www.tiktok.com. Additionally, we're going to treat our search function like a keyword, so we need to declare that as well!

Let's go ahead and use the Exa parameters to accomplish this. To display this, let's also add a print statement at the end of our file to search!
<pre> ```from exa_py import Exa

exa = Exa('YOUR_KEY_HERE')

query = input('Search here: ')

response = exa.search(
  query,
  num_results=5,
  type='keyword',
  include_domains=['https://www.tiktok.com'],
)

print(response)``` </pre>
Run the script by going to your terminal and typing:
<pre> ```python3 main.py``` </pre> 

After pressing enter, you should now see the following:
![image](https://github.com/user-attachments/assets/4b8e3d08-5d71-41a1-a4e9-ed45bb654dc8)
You might notice some information on each result like score, author, and text. Depending on your search query, you may or may not want these to be displayed every time you write a query.

Let's format our code so that for our React documentation search engine, we only get the Title and the URL. Delete the print statement, and add the following to main.py.
<pre> ```for result in response.results:
  print(f'Title: {result.title}')
  print(f'URL: {result.url}')
  print()``` </pre> 
  Now, your search results should look something like this!
  ![image](https://github.com/user-attachments/assets/322399ef-2355-4950-beba-550a53cbc6b3)
A lot easier on the eyes, right? 🤩💫

At this point, your main.py file should look like this:


<pre> ```from exa_py import Exa

exa = Exa('YOUR_KEY_HERE')

query = input('Search here: ')

response = exa.search(
  query,
  num_results=5,
  type='keyword',
  include_domains=['https://www.tiktok.com'],
)

for result in response.results:
  print(f'Title: {result.title}')
  print(f'URL: {result.url}')
  print()``` </pre> 

  # Mission Accomplished!
Congrats, you just created a custom search engine! ✨

![image](https://github.com/user-attachments/assets/77d1788b-b5cc-41d1-8468-a9f1db18bb5a)
