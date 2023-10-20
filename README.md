### RakuScraper

<p align="center">
  <img src="logo.png" alt="RakuScraper Logo" width="400"> <!-- Adjust width as necessary -->
</p>

`RakuScraper` is a powerful yet easy-to-use Python library for automated web scraping. The name "Raku" is inspired by the Japanese word that means "easy." True to its name, `RakuScraper` is devoted to simplifying the automation and scraping of websites. With a clean and intuitive API, you can collect the data you need without the hassle.

### Installation

You can easily install `RakuScraper` via pip:

```bash
pip install raku-scraper
```

### Features

- **Ease of Use**: A user-friendly API that makes web scraping a breeze.
- **Flexibility**: Easily customizable for a wide range of web scraping tasks.
- **Robust**: Built to handle errors gracefully and continue the scraping process.

### Quick Start

Here’s a quick example that demonstrates the simplicity and power of `RakuScraper`. In this example, we will automate the process of accepting cookies on a webpage, then scrape the title of the webpage before and after changing the language of the webpage.

```python
# Import the necessary classes from RakuScraper
from raku_scraper import ScrapingTask, RakuScraper  

# Create a scraping task for a specific URL
task = ScrapingTask(url="https://www.example.com", title="Example Page", description="A test page")

# Add steps to the scraping task
task.add_action(step_id="accept_cookies", selector="#cookie_accept", action="click", description="Accept cookies")
task.add_selector(step_id="page_title", selector="h1.title", attribute="text", description="Get the title of the page")
task.add_action(step_id="change_language", selector="#language_toggle", action="click", description="Change language")
task.add_selector(step_id="page_title_after_language_change", selector="h1.title", attribute="text", description="Get the title of the page after language change")

# Create a RakuScraper instance and execute the scraping task
scraper = RakuScraper(task, headless=False)  # Set headless to True for headless mode
results = scraper.scrape()

# Print the scraped data
print("Results:", results)
```

### Contributing

We welcome contributions from the community. If you'd like to contribute, feel free to open an issue or create a pull request. For major changes, please open an issue first to discuss what you would like to change.
