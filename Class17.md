# Web Scraping

- Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.

## Techniques

- Human copy-and-paste

*The simplest form of web scraping is manually copying and pasting data from a web page into a text file or spreadsheet.

- Text pattern matching

*A simple yet powerful approach to extract information from web pages can be based on the UNIX grep command or regular expression-matching facilities of programming languages (for instance Perl or Python).*

- HTTP programming

*Static and dynamic web pages can be retrieved by posting HTTP requests to the remote web server using socket programming.*

- you can find more techniques [here](https://en.wikipedia.org/wiki/Web_scraping)


## How to Scrape Websites Without Getting Blocked


- Basic Rule: “Be Nice”

An overarching rule to keep in mind for any kind of web scraping is
BE GOOD AND FOLLOW A WEBSITE’S CRAWLING POLICIES

- Respect Robots.txt

Web spiders should ideally follow the robot.txt file for a website while scraping.

- How do you find out if a website has blocked or banned you?

If any of the following signs appear on the site that you are crawling, it is usually a sign of being blocked or banned.

- CAPTCHA pages
- Unusual content delivery delays
- Frequent response with HTTP 404, 301 or 50x errors
- Frequent appearance of these HTTP status codes
- is also indication of blocking

- 301 Moved Temporarily
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 408 Request Timeout
- 429 Too Many Requests
- 503 Service Unavailable
