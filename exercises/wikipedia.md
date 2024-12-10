# Random Wikipedia walker

Using Selenium, create a small program that, starting from the main page https://www.wikipedia.org/, walks trough a sequence of random links and takes a snapshot of the last page.
The process is as follows:

 1. Navigate to the main page https://www.wikipedia.org/
 2. Select a random link in the page
 3. Navigate to the link
 4. Repeat steps 2 to 3 until you have visited 10 different pages
 5. Take a snapshot of the current page and save it

Include the code of the walker and the snapshot in this document.

## Answer

```python
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.by import By
import random

driver = webdriver.Firefox()
driver.get("http://www.wikipedia.com")

for i in range(10):
    driver.get(random.choice(driver.find_elements(By.XPATH, "//a[@href]")).get_attribute("href"))
```

Page finale après l'execution:
![https://iranicaonline.org/articles/babol-02](Screenshot_20241210_135312.png)
