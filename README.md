# 👨‍👨‍👦‍👦🛠️ CrewAi-Tools 🚀

## 🛠️ List of Crew Ai Tools :
- WebsiteSearchTool
- YoutubeVideoSearchTool
- GithubSearchTool
- PDFSearchTool
- ScrapeWebsiteTool
- ComposioTool
- SeleniumScrapingTool

## ⚙️

> WebsiteSearchTool

```python
from crewai_tools import WebsiteSearchTool

# Example of initiating tool that agents can use to search across any discovered websites
tool = WebsiteSearchTool()

# Example of limiting the search to the content of a specific website, so now agents can only search within that website
tool = WebsiteSearchTool(website='https://example.com')
```

> YoutubeVideoSearchTool

```python
from crewai_tools import YoutubeVideoSearchTool

# General search across Youtube content without specifying a video URL, so the agent can search within any Youtube video content it learns about irs url during its operation
tool = YoutubeVideoSearchTool()

# Targeted search within a specific Youtube video's content
tool = YoutubeVideoSearchTool(youtube_video_url='https://youtube.com/watch?v=example')
```

> GithubSearchTool

```python
from crewai_tools import GithubSearchTool

# Initialize the tool for semantic searches within a specific GitHub repository
tool = GithubSearchTool(
    github_repo='https://github.com/example/repo',
    content_types=['code', 'issue'] # Options: code, repo, pr, issue
)

# OR

# Initialize the tool for semantic searches within a specific GitHub repository, so the agent can search any repository if it learns about during its execution
tool = GithubSearchTool(
    content_types=['code', 'issue'] # Options: code, repo, pr, issue
)
```

> PDFSearchTool

```python
from crewai_tools import PDFSearchTool

# Initialize the tool allowing for any PDF content search if the path is provided during execution
tool = PDFSearchTool()

# OR

# Initialize the tool with a specific PDF path for exclusive search within that document
tool = PDFSearchTool(pdf='path/to/your/document.pdf')
```

> ScrapeWebsiteTool

```python
from crewai_tools import ScrapeWebsiteTool

# To enable scrapping any website it finds during it's execution
#tool = ScrapeWebsiteTool()

# Initialize the tool with the website URL, so the agent can only scrap the content of the specified website
website_url = 'https://mairie-quincy-sous-senart.fr/fr/'
tool = ScrapeWebsiteTool(website_url=website_url)

# Extract the text from the site
text = tool.run()
print(text)
```

> ComposioTool : https://docs.composio.dev/introduction/intro/overview

```python
from composio import App
from crewai_tools import ComposioTool
from crewai import Agent, Task

# Composio

tools = [ComposioTool.from_action(action=Action.GITHUB_ACTIVITY_STAR_REPO_FOR_AUTHENTICATED_USER)]
```

> SeleniumScrapingTool

```python
from crewai_tools import SeleniumScrapingTool

# The SeleniumScrapingTool is crafted for high-efficiency web scraping tasks. It allows for precise extraction of content from web pages by using CSS selectors to target specific elements. Its design caters to a wide range of scraping needs, offering flexibility to work with any provided website URL.

# Example 1: Initialize the tool without any parameters to scrape the current page it navigates to
tool = SeleniumScrapingTool()

# Example 2: Scrape the entire webpage of a given URL
tool = SeleniumScrapingTool(website_url='https://example.com')

# Example 3: Target and scrape a specific CSS element from a webpage
tool = SeleniumScrapingTool(website_url='https://example.com', css_element='.main-content')

# Example 4: Perform scraping with additional parameters for a customized experience
tool = SeleniumScrapingTool(website_url='https://example.com', css_element='.main-content', cookie={'name': 'user', 'value': 'John Doe'}, wait_time=10)
```

