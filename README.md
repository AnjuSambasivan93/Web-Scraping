<h1> Web scraping reviews from the Uber Eats page on Trustpilot </h1>



<h2>Description</h2>

This project involves web scraping reviews from the Uber Eats page on Trustpilot using R. The goal is to extract and clean data such as review titles, review text, reviewer names, dates, and star ratings. The collected data is organized into a structured format and saved as a CSV file for further analysis. This project demonstrates the use of web scraping techniques to gather and process real-world customer feedback for insights.

<h2> Language and Tools Used </h2>

#### Language:

- **R**: Used for all data scraping, cleaning, and organization tasks.
  
#### Libraries:

- **rvest**: For scraping HTML content from the Trustpilot website.
- **lubridate**: For handling and formatting dates.
- **dplyr**: For data manipulation and cleaning.

#### Environment:

- The project was implemented and tested in RStudio.
  
#### Output:

- A CSV file (scraped_reviews.csv) containing structured review data.
  
<h2> Main Functions Used </h2>


### **1. `paste0()`**
- Combines strings together without any separator.
- Used to construct the URL for each Trustpilot page (e.g., `https://www.trustpilot.com/review/ubereats.com?page=1`).

### **2. `sub()`**
- Searches for a pattern in a string and replaces it with a new value.
- Used in:
  - `extract_dates()` to remove the "Date of experience: " text.
  - `extract_rating()` to extract numeric star ratings.

### **3. `as.integer()`**
- Converts a value or string to an integer.
- Used in `extract_rating()` to convert star ratings from text to numeric format.

### **4. `min()`**
- Finds the smallest value in a numeric vector.
- Used to ensure all extracted lists (titles, text, reviewers, dates, ratings) are of the same length.

### **5. `lapply()`**
- Applies a function to each element of a list or vector.
- Used to apply the `scrape_page` function to scrape multiple pages.

### **6. `do.call()`**
- Combines a list of objects into one using a specified function.
- Used with `rbind` to combine multiple data frames from all pages into one.

### **7. `rbind()`**
- Combines data frames by stacking their rows.
- Used within `do.call()` to combine all scraped data frames into a single data frame.

### **8. `write.csv()`**
- Saves a data frame to a CSV file.
- Used to export the combined and cleaned data to `scraped_reviews.csv`.

### **9. `cat()`**
- Concatenates and prints messages to the console.
- Used to display a confirmation message after the CSV file is saved.

### **10. `grep()`**
- Searches for a pattern in a vector and returns the index of matches.
- Used to find raw text entries starting with "Date of experience:" in the reviews.
