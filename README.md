<div align="center"><img src="resources/icon.png", width=150></div>

# Shopify Spy

Shopify Spy is a simple but powerful [Scrapy](https://docs.scrapy.org/en/latest/index.html) application for scraping Shopify websites. Its main feature is `shopify_spider`, a universal Shopify spider. The spider is designed to extract detailed data from *any* Shopify store, including high-value information like vendor names and inventory levels.

Supports dynamic website content via scrapy-playwright. See browser settings in `custom_settings` in `shopify_spy/spiders/shopify.py`.

To find Shopify stores to scrape, try searching Google with the argument `site:myshopify.com`.

## Forking

Shopify Spy is just a project built using the Scrapy framework. To use it, fork and/or clone the repository. Forking is recommended, since you might want to adjust the settings in `shopify_spy/settings.py`, and can fetch updates.

## Usage

The spider can be used like any Scrapy spider, but you must provide it with an URL. Set your working directory to the project directory and execute one of the following commands.

Install scrapy-playwright

```
pip install scrapy-playwright
```


Scrape a single Shopify store:
```shell
scrapy crawl shopify_spider -a url=https://www.example.com/
```
Scrape multiple Shopify stores at once using a text file with one URL per line:
```shell
scrapy crawl shopify_spider -a url_file=resources/urls.txt
```
Specify which items to scrape:
```shell
scrapy crawl shopify_spider -a url=https://www.example.com/ -a products=False -a collections=True
```
 Arguments must always be preceded with the `-a` flag, as is standard for Scrapy. The results will be stored in a JSON lines file in `/resources/shopify_spider`.

Please refer to the [Scrapy documentation](https://docs.scrapy.org/en/latest/index.html) for questions about adjusting the settings, more advanced usage, or the Scrapy framework in general.

## Limitations

Attempting to scrape a large store may result in a temporary ban. This can be mitigated by configuring AutoThrottle, which is disabled by default.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change. Make sure to update the tests in `tests.py` and contracts in the spider.

## License

[MIT](https://choosealicense.com/licenses/mit/)


## Credits

Icon by [Bartama Graphic](https://www.flaticon.com/authors/bartama-graphic).
