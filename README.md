# Scalper-Bot
This scalper bot was made at the request of my friend to buy Nvidia GPU 5090s founders edition. I utilised TypeScript, Python, and Javascript for the implementation of Playwright, Puppeteer, and/or selenium. 

**#update#** unable to secure a piece, due to limited quantity sold (100p), paper launch. but happy to learn new things everyday! :)

Initially set as private as I'm not proud to have made a scalper bot, but will be making others and this one public in the future, for University Applications.


**Challenges and Solutions**
1. Speeding Up Web Scraping
Issue: The script initially loaded all resources on the page, which made it run slower than expected.
Solution: To make things faster, I added a function to block unnecessary resources like images, fonts, CSS, and JavaScript, cutting down load times significantly.
Takeaway: Reducing extra network requests is an easy way to boost automation speed.


2. Extracting SKU from URL with Regex
Issue: The script needed to dynamically grab the SKU ID from the product URL to locate the "Add to Cart" button.
Solution: I used a **simple regular expression (re.search(r"skuId=(\d+)", url))** to pull out the numeric SKU from the URL.
Takeaway: Regex is a handy tool for extracting structured data like IDs from URLs.


3. Handling Region Selection
Issue: The website sometimes prompted a manual region selection before proceeding.
Solution: I added a check to detect and click the "United States" region selection button whenever it appeared.
Takeaway: Websites with regional redirects can disrupt automation, so handling them properly ensures smooth navigation.


4. Ensuring the "Add to Cart" Button Works
Issue: Sometimes, the "Add to Cart" button wasn’t available due to stock issues or slow page loading.
Solution: I used **wait_for_selector()** with a timeout to make sure the button appeared before interacting with it.
Takeaway: Adding proper wait times helps prevent automation failures caused by elements not loading in time.

5. Confirming the Item Was Added to Cart
Issue: Clicking "Add to Cart" didn’t always mean the item was successfully added.
Solution: I added a check for the **cart icon ("a.cart-link")** to confirm that the cart was updated properly.
Takeaway: Double-checking actions like adding items to a cart prevents false positives in automation scripts.


6. Handling Page Navigation and Errors
Issue: Sometimes, page redirections failed due to slow network conditions.
Solution: I increased timeout settings and used **"wait_until='networkidle'"** to ensure the page was fully loaded before proceeding.
Takeaway: Adjusting timeout settings prevents the script from interacting with incomplete pages.


7. Automating Checkout Securely
Issue: Entering sensitive payment information in an automated way needed to be done carefully.
Solution: I used **page.fill()** to enter payment details dynamically. (For real-world applications, secure storage should be used instead of hardcoding data.)
Takeaway: Automating form filling is useful, but security measures are necessary when handling sensitive information.

