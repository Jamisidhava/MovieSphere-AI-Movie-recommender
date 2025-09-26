# MovieSphere AI Movie Recommender

MovieSphere AI is a modern, interactive movie recommendation web app powered by machine learning and natural language processing. It provides personalized movie recommendations based on user input, leveraging fuzzy title matching, TF-IDF vectorization, and nearest neighbors search. The app features a beautiful UI and integrates with The Movie Database (TMDb) API for movie posters and metadata.

## Features

- **AI-Powered Recommendations:** Enter a movie title to get similar movie suggestions using advanced NLP and ML models.
- **Fuzzy Search:** Handles typos and partial matches for movie titles.
- **Popular Movies Slider:** Showcases trending/popular movies on the homepage.
- **Detailed Movie Info:** Displays cast, genres, studios, languages, runtime, and overview.
- **Modern UI:** Responsive, animated, and visually appealing interface.
- **Fast & Asynchronous:** Uses async requests for fetching posters and metadata.

## Demo

<!-- Add a screenshot if available -->
<!-- ![MovieSphere Screenshot](screenshot.png) -->

## Project Structure

```
.
├── api/
│   └── index.py              # Flask API and web app logic
├── templates/
│   ├── index.html            # Main HTML template (Jinja2)
│   └── README.md
├── movies_data.pkl           # Movie metadata (pandas DataFrame)
├── nearest_neighbors_model.pkl # Trained NearestNeighbors model
├── tfidf_vectorizer.pkl      # Trained TF-IDF vectorizer
├── tfidf_matrix.npz          # Sparse matrix of movie features
├── popular_movies.pkl        # Precomputed list of popular movies
├── requirements.txt          # Python dependencies
├── Procfile                  # For deployment (e.g., Heroku)
├── README.md                 # This file
└── notebook/
	 └── MovieSphere.ipynb     # Data exploration and model training
```

## Getting Started

### Prerequisites

- Python 3.8+
- [pip](https://pip.pypa.io/en/stable/)
- TMDb API Key (for fetching posters and metadata)

### Installation

1. **Clone the repository:**
	```bash
	git clone https://github.com/Jamisidhava/MovieSphere-AI-Movie-recommender.git
	cd MovieSphere-AI-Movie-recommender
	```

2. **Install dependencies:**
	```bash
	pip install -r requirements.txt
	```

3. **Set up environment variables:**
	- Create a `.env` file in the root directory:
	  ```
	  TMDB_API_KEY=your_tmdb_api_key_here
	  ```

4. **Run the app locally:**
	```bash
	python -m api.index
	```
	Or with Gunicorn (recommended for production):
	```bash
	gunicorn api.index:app
	```

5. **Open your browser:**
	- Visit [http://localhost:8000](http://localhost:8000) (or the port shown in your terminal).

## Deployment

- **Heroku:** The included `Procfile` allows easy deployment to Heroku.
- **Other Platforms:** Any platform supporting Python and Gunicorn/Flask.

## Usage

- Enter a movie title in the search bar and get instant recommendations.
- Browse popular movies on the homepage.
- Click on any recommended movie to get further suggestions.

## Data & Models

- **movies_data.pkl:** Contains movie metadata (title, genres, cast, etc.).
- **tfidf_vectorizer.pkl & tfidf_matrix.npz:** Used for transforming movie overviews into feature vectors.
- **nearest_neighbors_model.pkl:** Scikit-learn NearestNeighbors model for similarity search.
- **popular_movies.pkl:** List of popular movies for the homepage slider.

## API & Tech Stack

- **Backend:** Python, Flask, scikit-learn, pandas, joblib, aiohttp, rapidfuzz
- **Frontend:** Jinja2 templates, HTML5, CSS3, JavaScript
- **Deployment:** Gunicorn, Procfile
- **External API:** [TMDb API](https://www.themoviedb.org/documentation/api)

## Environment Variables

- `TMDB_API_KEY`: Your TMDb API key (required for fetching posters and metadata).

## License

MIT License. See [LICENSE](LICENSE) for details.

## Acknowledgements

- [The Movie Database (TMDb)](https://www.themoviedb.org/)
- [scikit-learn](https://scikit-learn.org/)
- [Flask](https://flask.palletsprojects.com/)
- [RapidFuzz](https://github.com/maxbachmann/RapidFuzz)