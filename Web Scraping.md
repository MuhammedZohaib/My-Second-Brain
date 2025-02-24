# Web Scraping

Make sure you have scrapy installed globally or in your virtual environment as:

```python
pip install scrapy
# Then we can make a new scrapy project as:
scrapy startproject project-name
cd project-name
# create a new spider
scrapy genspider spiderName domainName(chocolate.co.uk)
# to run scrapy shell
scrapy shell
# to list available spiders
scrapy list
# to crawl a spider
scarpy crawl spiderName -o output.json/output.csv
```

```python
# A simple spider
import scrapy

class ChocolaterspiderSpider(scrapy.Spider):
    name = "chocolaterSpider"
    allowed_domains = ["chocolate.co.uk"]
    start_urls = ["https://chocolate.co.uk/collections/all"]

    def parse(self, response):
        products = response.css('product-item')

        for product in products:
            yield {
                'name': product.css('a.product-item-meta__title::text').get(),
                'price': product.css('span.price').get().replace('<span class="price">\n              <span class="visually-hidden">Sale price</span>', '').replace('</span>', ''),
                'url': product.css('div.product-item-meta a').attrib['href']
            }
        
        
        next_page = response.css('a.pagination__nav-item').attrib['href']
        if next_page is not None:
            next_page_url = f'https://chocolate.co.uk{next_page}'
            yield response.follow(next_page_url, callback=self.parse)
```

---

### 1. **Installation**

```other
pip install scrapy
```

### 2. **Creating a New Project**

```other
scrapy startproject project_name
cd project_name
```

### 3. **Project Structure**

- `project_name/`
   - `scrapy.cfg`: Project configuration file
   - `project_name/`
      - `__init__.py`
      - `items.py`: Define your data models
      - `middlewares.py`: Custom middleware for processing requests/responses
      - `pipelines.py`: Processing items extracted by spiders
      - `settings.py`: Project settings
      - `spiders/`: Directory for spiders
         - `__init__.py`

### 4. **Creating a Spider**

```other
scrapy genspider spider_name domain.com
```

### 5. **Spider Structure**

```python
import scrapy

class ExampleSpider(scrapy.Spider):
    name = "example"
    allowed_domains = ["example.com"]
    start_urls = ["http://example.com"]

    def parse(self, response):
        # Parsing logic here
        pass
```

### 6. **Extracting Data**

- **XPath Selectors**

```python
titles = response.xpath('//h1/text()').getall()
```

- **CSS Selectors**

```python
titles = response.css('h1::text').getall()
```

- **Get and Getall**

```python
title = response.xpath('//h1/text()').get()
titles = response.xpath('//h1/text()').getall()
```

### 7. **Item Definition**

```python
# items.py
import scrapy

class ExampleItem(scrapy.Item):
    title = scrapy.Field()
    description = scrapy.Field()
```

### 8. **Yielding Items in Spiders**

```python
import scrapy
from project_name.items import ExampleItem

class ExampleSpider(scrapy.Spider):
    name = "example"
    start_urls = ["http://example.com"]

    def parse(self, response):
        item = ExampleItem()
        item['title'] = response.xpath('//h1/text()').get()
        item['description'] = response.xpath('//p/text()').get()
        yield item
```

### 9. **Running the Spider**

```other
scrapy crawl example
```

### 10. **Exporting Data**

```other
scrapy crawl example -o output.json
scrapy crawl example -o output.csv
scrapy crawl example -o output.xml
```

### 11. **Settings**

- **Basic Settings**

```python
# settings.py
BOT_NAME = 'project_name'
SPIDER_MODULES = ['project_name.spiders']
NEWSPIDER_MODULE = 'project_name.spiders'
ROBOTSTXT_OBEY = True
```

- **User Agent**

```python
# settings.py
USER_AGENT = 'your_user_agent'
```

- **Concurrent Requests**

```python
# settings.py
CONCURRENT_REQUESTS = 16
```

- **Download Delay**

```python
# settings.py
DOWNLOAD_DELAY = 1
```

### 12. **Middlewares**

- **Enabling a Middleware**

```python
# settings.py
DOWNLOADER_MIDDLEWARES = {
   'project_name.middlewares.ProjectNameDownloaderMiddleware': 543,
}
```

- **Custom Middleware Example**

```python
# middlewares.py
class ProjectNameDownloaderMiddleware:
    def process_request(self, request, spider):
        # Custom request processing
        pass

    def process_response(self, request, response, spider):
        # Custom response processing
        return response
```

### 13. **Pipelines**

- **Enabling a Pipeline**

```python
# settings.py
ITEM_PIPELINES = {
   'project_name.pipelines.ProjectNamePipeline': 300,
}
```

- **Custom Pipeline Example**

```python
# pipelines.py
class ProjectNamePipeline:
    def process_item(self, item, spider):
        # Item processing logic
        return item
```

### 14. **Scrapy Shell**

- **Starting Scrapy Shell**

```other
scrapy shell 'http://example.com'
```

- **Using Shell**

```python
response.xpath('//title/text()').get()
response.css('title::text').get()
```

### 15. **Handling Requests and Responses**

- **Making Requests**

```python
import scrapy

class ExampleSpider(scrapy.Spider):
    name = "example"
    start_urls = ["http://example.com"]

    def parse(self, response):
        yield scrapy.Request(url='http://example.com/page2', callback=self.parse_page2)

    def parse_page2(self, response):
        # Parsing logic for page 2
        pass
```

- **Passing Data Between Callbacks**

```python
class ExampleSpider(scrapy.Spider):
    name = "example"
    start_urls = ["http://example.com"]

    def parse(self, response):
        item = ExampleItem()
        item['title'] = response.xpath('//h1/text()').get()
        request = scrapy.Request(url='http://example.com/page2', callback=self.parse_page2)
        request.meta['item'] = item
        yield request

    def parse_page2(self, response):
        item = response.meta['item']
        item['description'] = response.xpath('//p/text()').get()
        yield item
```

### 16. **Logging**

```python
import logging

class ExampleSpider(scrapy.Spider):
    name = "example"

    def parse(self, response):
        self.logger.info('Parsed URL: %s', response.url)
```

### 17. **Debugging and Testing**

- **Unit Testing**

```python
# tests/test_spider.py
import unittest
from scrapy.http import HtmlResponse
from project_name.spiders.example import ExampleSpider

class TestExampleSpider(unittest.TestCase):

    def test_parse(self):
        spider = ExampleSpider()
        response = HtmlResponse(url='http://example.com', body='<html><body><h1>Title</h1></body></html>', encoding='utf-8')
        result = next(spider.parse(response))
        self.assertEqual(result['title'], 'Title')
```

### 18. **Advanced Topics**

- **Using Scrapy with Splash**

```other
pip install scrapy-splash
```

```python
# settings.py
SPLASH_URL = 'http://localhost:8050'
DOWNLOADER_MIDDLEWARES.update({
    'scrapy_splash.SplashCookiesMiddleware': 723,
    'scrapy_splash.SplashMiddleware': 725,
})
SPIDER_MIDDLEWARES.update({
    'scrapy_splash.SplashDeduplicateArgsMiddleware': 100,
})
DUPEFILTER_CLASS = 'scrapy_splash.SplashAwareDupeFilter'
HTTPCACHE_STORAGE = 'scrapy_splash.SplashAwareFSCacheStorage'
```

```python
import scrapy
from scrapy_splash import SplashRequest

class ExampleSpider(scrapy.Spider):
    name = "example"

    def start_requests(self):
        yield SplashRequest(url='http://example.com', callback=self.parse)

    def parse(self, response):
        # Parsing logic here
        pass
```

- **Scrapy with Selenium**

```other
pip install scrapy-selenium
```

```python
# settings.py
from shutil import which

SELENIUM_DRIVER_NAME = 'chrome'
SELENIUM_DRIVER_EXECUTABLE_PATH = which('chromedriver')
SELENIUM_DRIVER_ARGUMENTS = ['--headless']
DOWNLOADER_MIDDLEWARES.update({
    'scrapy_selenium.SeleniumMiddleware': 800
})
```

```python
import scrapy
from scrapy_selenium import SeleniumRequest

class ExampleSpider(scrapy.Spider):
    name = "example"

    def start_requests(self):
        yield SeleniumRequest(url='http://example.com', callback=self.parse)

    def parse(self, response):
        # Parsing logic here
        pass
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Web+Scraping.md&fileType=undefined&fileExtension=md