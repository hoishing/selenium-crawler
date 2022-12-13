# Selenium Crawler

[![GitHub](https://img.shields.io/github/license/hoishing/selenium-crawler)](https://opensource.org/licenses/MIT)

> a web crawler written in python, powered by [Selenium][selenium] and [Tesseract OCR][pytesseract]

## Motivation

In a project I need to collect the name and address of all dental laboratories in Taiwan. Unfortunately the [Ministry of Health and Welfare][mohw] doesn't provide a structured format(csv, json...etc) for download. The data only available as website tables having just 10 records each page... I got to crawl it without other fast and simple options.

## Installation

- headless chrome: `brew install --cask chromedriver`
- python packages:

```js
ipykernel = "^6.19.2"
selenium = "^4.7.2"
webdriver-manager = "^3.8.5"
pytesseract = "^0.3.10"
jupyter = "^1.0.0"
```

## Usage

- run `selenium-crawler.ipynb` in VSCode or JupyterLab

## tech stack

🔗 [source code](https://github.com/hoishing/selenium-crawler)

- [Jupyter][jupyter]: exploratory programming in python
  - effectively try out any CSS selector / XPath combinations
- [Selenium][selenium]
  - First use normal mode to have visual feedback while exploring XPaths
  - then use headless mode in production
- [Tesseract][pytesseract]: Google's OCR library for recognizing captcha
- [PIL][pil]: create image object from the captcha binary retrieved by Selenium

### Rationale

I've been struggling for a while which crawling library should be used. Besides Selenium, other candidates included [Scrapy][scrapy], [Playwright][playwright] and [Puppeteer][puppeteer].

Scrapy is a highly structured framework. I need to follow its structure to write python classes and middle-wares if using it. Then use CLI to run the crawling. The well structured format does provide clear separation of concerns. Its good for creating serious crawler, especially when working with a team that each member responsible for a specific part of a project. However, its a bit overkill for an one-man simple crawling project like this one, so maybe next time.

Playwright, as pytest plugin in python, its more test oriented and depend on [pytest] with CLI. This added an other layer of complication, also not well suited in jupyter's exploratory programming style. Therefore 🙅‍♀️

Puppeteer is the closest competitor. I like its flexible and elegant API on selecting elements. The main reason for not choosing it is that exploratory programming style for javascript is not that "out-of-box" comparing with python. Yes, I can do exploratory programming with js, such as using [Quokka][quokka] in VSCode, installing [iJavascript][ijs] kernel for jupyter, or using [RunKit][runkit] online... etc. The DX of these toolings are just not as smooth and mature as jupyter + python. Also, if using python with jupyter, I can easily "deploy" the finished program online using [Binder][binder], such that my client could try it out immediate by pressing the xxx icon. That greatly speed up the development cycle.

## Need Help?

Open a [github issue](https://github.com/hoishing/selenium-crawler/issues) or ping me on [Twitter](https://twitter.com/hoishing) ![](https://api.iconify.design/logos/twitter.svg?width=20)

[jupyter]: https://docs.jupyter.org/
[mohw]: https://mohw.gov.tw/
[pytesseract]: https://github.com/madmaze/pytesseract
[pil]: https://pillow.readthedocs.io
[selenium]: https://selenium-python.readthedocs.io
[scrapy]: https://scrapy.org
[playwright]: https://github.com/microsoft/playwright
[puppeteer]: https://github.com/puppeteer/puppeteer
[pytest]: https://github.com/pytest-dev/pytest
[runkit]: https://runkit.com
[quokka]: https://quokkajs.com
[ijs]: https://github.com/n-riesco/ijavascript
[binder]: https://mybinder.org
