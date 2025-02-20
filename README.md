# Automated-Internship-and-Job-Application-System-Using-Web-Automation
## AIM:
This project aims to automate the process of applying for internships and jobs using web automation techniques. The system will extract job listings from various platforms, filter them based on user preferences, and automatically submit applications, reducing manual effort and improving efficiency.

## KEY FEATURES: 
### 1. Web Scraping & Job Extraction:
Extract job postings from platforms like LinkedIn, Indeed, and Internshala using Selenium and BeautifulSoup.

### 2. Filtering & Customization:
Apply filters such as job role, location, experience, and company preference.
Use Natural Language Processing (NLP) to match job descriptions with user skills.

### 3. Automated Resume & Cover Letter Submission:
Fill in application forms automatically.
Upload a resume and cover letter based on the job requirements.

### 4. User Authentication & Dashboard:
Store user credentials securely (OAuth or encrypted storage).
Show application status and history on a dashboard.

### 5.Error Handling & Logging:
Log failed attempts and retry mechanisms.
https://github.com/Yugendaran/Automated-Internship-and-Job-Application-System-Using-Web-Automation/blob/7409ff9d08aeac3cc555fc9613d64fe5139055ec/demo.gif

## Implementation Code (Using Python & Selenium)
### 1. Install Required Libraries
```
pip install selenium beautifulsoup4 pandas requests
```
### 2. Import Required Modules
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time
import pandas as pd
```
### 3. Configure WebDriver
```
```
### 4. Job Scraper for LinkedIn
```
def scrape_linkedin_jobs(keyword, location):
    driver.get("https://www.linkedin.com/jobs/search/")
    time.sleep(3)

    search_box = driver.find_element(By.XPATH, '//input[@aria-label="Search by title, skill, or company"]')
    search_box.send_keys(keyword)
    search_box.send_keys(Keys.RETURN)
    time.sleep(3)

    jobs = driver.find_elements(By.CLASS_NAME, 'job-card-list__title')

    job_list = []
    for job in jobs[:10]:  # Extracting top 10 jobs
        job_title = job.text
        job_list.append(job_title)

    return job_list

# Example Usage
jobs = scrape_linkedin_jobs("Software Engineer Intern", "Remote")
print(jobs)
```
### 5. Auto-Fill Application
```
def auto_apply_linkedin():
    driver.get("https://www.linkedin.com/login")
    time.sleep(3)

    # Login
    email = driver.find_element(By.ID, "username")
    password = driver.find_element(By.ID, "password")
    
    email.send_keys("your_email@example.com")
    password.send_keys("your_password")
    password.send_keys(Keys.RETURN)
    time.sleep(5)

    # Go to job application page (Example URL)
    driver.get("https://www.linkedin.com/jobs/apply/some-job-id")
    time.sleep(3)

    # Click Apply Button
    apply_button = driver.find_element(By.CLASS_NAME, 'jobs-apply-button')
    apply_button.click()
    time.sleep(3)

    # Fill Application Form
    submit_button = driver.find_element(By.CLASS_NAME, 'artdeco-button--primary')
    submit_button.click()

    print("Application Submitted!")

# Example Usage
auto_apply_linkedin()
```
## Future Enhancements
* Implement AI-based resume matching.
* Store job application history in a database.
* Expand to multiple job platforms.


