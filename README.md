# ai-times News Database

This repository contains the database for ai-times, a collection of structured data scraped and processed from various news sources. Below is an overview of the structure and contents of the database.

---

## Project Structure

### 1. **Date-Based Folders**
Each folder is named according to a specific date (e.g., `2025-01-07`) and contains the following files:

#### a. **Date JSON File**
- **Filename**: `YYYY-MM-DD.json`
- **Description**: Holds all the scraped news articles for the specified date.
- **Key Explanations:**
  - `authors`: A list of authors credited for the article.
  - `date_download`: The timestamp when the article was downloaded.
  - `date_modify`: Modification date, if available.
  - `date_publish`: The publication date of the article.
  - `description`: A short summary or description of the article.
  - `filename`: Encoded filename representing the source URL.
  - `image_url`: URL of the main image associated with the article.
  - `language`: Language of the article (e.g., "el" for Greek).
  - `localpath`: Path to the local copy of the article, if applicable.
  - `maintext`: Full text of the article.
  - `source_domain`: Domain name of the source website.
  - `text`: Reserved for additional processing or data (often null initially).
  - `title`: Title of the article.
  - `title_page`: Title as it appears on the webpage (optional).
  - `title_rss`: Title as it appears in the RSS feed (optional).
  - `url`: Original URL of the article.

#### b. **Journalist JSON File**
- **Filename**: `YYYY-MM-DD_JournalistName.json`
- **Description**: Contains a randomized selection of at least five articles from each news source scraped on the given date.
- **Key Explanations:**
  - Includes all keys from the Date JSON File, plus:
    - `llm_text`: Text processed and prepared as input for the language model (LLM).

#### c. **Final LLM Response Entry**
- The last entry in the `JournalistName.json` file includes additional keys to represent the LLM's generated response:
  - `title`: The title of the article generated by the LLM, reflecting the key theme of the content.
  - `text`: The main body of the text generated by the LLM, summarizing or rephrasing the input.
  - `categories`: A list of categories assigned to the article, indicating its topics (e.g., "economy," "greece").
  - `headline`: A short, impactful headline summarizing the generated content, designed to capture attention.

---

## Usage

1. **Scraped News:**
   - The primary JSON file for each date contains all scraped news articles.

2. **Randomized Articles:**
   - The `JournalistName.json` files provide a curated, randomized subset of articles with additional processing.

3. **LLM Outputs:**
   - Each journalist JSON file includes the LLM-generated responses for selected articles, making it easy to trace the input-output process.

---



