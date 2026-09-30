# News Application

**Problem 2 – Feature Set B**

A simple news application that lets users search for news by keyword, browse headlines with their source and date, read a short description, and open the complete article.

---

## Features

| # | Feature | Description |
|---|---------|-------------|
| 1 | **Search news by keyword** | Enter a keyword or phrase to fetch matching news articles. |
| 2 | **Display headlines** | Each result shows the article's headline/title. |
| 3 | **Display source and date** | Each result shows the publisher name and publication date. |
| 4 | **Display article description** | A short summary of the article is shown under the headline. |
| 5 | **Open the complete article** | Selecting an article opens the full story on the publisher's website. |

---

## How It Works

1. The user types a keyword into the search box and submits.
2. The app sends a request to a news API with the keyword.
3. The API returns a list of matching articles.
4. The app renders each article as a card containing:
   - Headline
   - Source and publication date
   - Description
   - A "Read full article" link
5. Clicking the link opens the original article in a new tab/browser.

---

## Tech Stack (suggested)

- **Frontend:** HTML, CSS, JavaScript (or React / Flutter / Android – adapt as required)
- **Data source:** [NewsAPI](https://newsapi.org/) `everything` endpoint (or any similar news API)
- **Networking:** `fetch` / Axios / Retrofit, depending on platform

---

## Getting Started

### Prerequisites

- A free API key from [newsapi.org](https://newsapi.org/)
- A modern web browser (for the web version)

### Setup

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd news-app

# 2. Add your API key
#    Open config.js (or .env) and set:
#    API_KEY = "YOUR_API_KEY"

# 3. Run the app
#    Open index.html in a browser, or start a local server:
npx serve .
```

---

## API Usage

**Endpoint**

```
GET https://newsapi.org/v2/everything?q={keyword}&sortBy=publishedAt&apiKey={API_KEY}
```

**Fields used from each article**

| Field | Used for |
|-------|----------|
| `title` | Headline |
| `source.name` | Source |
| `publishedAt` | Date |
| `description` | Article description |
| `url` | Link to the complete article |

---

## Project Structure

```
news-app/
├── index.html      # Search box and results container
├── style.css       # Styling for the layout and article cards
├── app.js          # Search logic, API call, rendering
├── config.js       # API key (do not commit to public repos)
└── README.md
```

---

## Usage

1. Launch the app.
2. Type a keyword (e.g. `technology`, `cricket`, `climate`) in the search bar.
3. Press **Search** or hit **Enter**.
4. Browse the list of headlines with their source, date and description.
5. Click **Read full article** to open the complete story.

---

## Edge Cases Handled

- Empty search input → prompts the user to enter a keyword.
- No results found → shows a "No articles found" message.
- Network or API error → shows a friendly error message.
- Missing description or source → displays a fallback such as "No description available".

---

## Future Improvements

- Pagination / infinite scroll
- Filter by date range or source
- Bookmark favorite articles
- Dark mode

---

## Notes

- Keep your API key private and never commit it to a public repository.
- Free API plans may limit the number of requests and the age of articles returned.

---

## License

This project is for educational purposes.
