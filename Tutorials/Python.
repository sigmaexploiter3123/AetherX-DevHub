1. Getting Started with Python
Content:

Installing Python
Download and install the latest version of Python from python.org.

Setting Up a Python Development Environment

Install VSCode or PyCharm.
Set up a virtual environment:
bash
Copy
python -m venv myenv
source myenv/bin/activate  # Linux/Mac
myenv\Scripts\activate     # Windows
Writing Your First Python Program
Create a hello.py file with the following content:

python
Copy
print("Hello, World!")
Running the Program

bash
Copy
python hello.py
2. Working with APIs in Python
Content:

Installing requests
Install the necessary library:

bash
Copy
pip install requests
Making a GET Request

python
Copy
import requests
response = requests.get("https://api.github.com")
print(response.json())  # Print the JSON response
Handling Errors

python
Copy
try:
    response = requests.get("https://api.github.com")
    response.raise_for_status()  # Raise an exception for bad status codes
except requests.exceptions.RequestException as e:
    print(f"Error: {e}")
3. Python Web Scraping with BeautifulSoup
Content:

Installing Libraries

bash
Copy
pip install requests beautifulsoup4
Basic Web Scraping Script

python
Copy
import requests
from bs4 import BeautifulSoup

URL = "https://example.com"
response = requests.get(URL)
soup = BeautifulSoup(response.content, "html.parser")

print(soup.prettify())  # Display the parsed HTML
Extracting Data

python
Copy
title = soup.find("h1").text
print(title)
