Recipe Search API for project BiteScan
Contribution: Hoang Nguyen

A lightweight Node.js/Express API that searches the web for recipes based on ingredients, country cuisine, and cooking style.
The API uses Google Custom Search to find recipe URLs, extracts data using JSON-LD parsing, and returns structured recipe info including ingredients, steps, and a relevance score.

Features
Search the web for recipes using Google Custom Search
Parse recipe pages using JSON-LD (schema.org/Recipe)

Extract:
Recipe name
URL
Ingredients
Instructions / Steps
A similarity score based on provided ingredients and cooking style
Sorted results (best matches first)
Built-in error handling
Works with any frontend or backend

Tech Stack:
Node.js
Express
Axios
Cheerio
Google Custom Search API
dotenv
Swagger UI for documentation

I. installation:
git clone https://github.com/hoangarthur/recipeSearchAPI.git
cd recipeSearchAPI
npm install

Environment Variables: Create a .env file in the project root
GOOGLE_API_KEY=your_google_search_api_key
GOOGLE_CX_ID=your_custom_search_engine_id
PORT=3000

Run the Server
node server.js
Server will start at: http://localhost:3000

II. API Endpoints:
POST /search-recipe
Searches the internet for recipes based on ingredients & cooking style.


Request URL: POST /search-recipe

Body (JSON):
{
  "ingredients": ["chicken", "garlic", "lemon"],
  "country": "Italian",
  "style": "healthy"
}

Response (Example)
{
  "count": 3,
  "recipes": [
    {
      "name": "Lemon Chicken Piccata",
      "url": "https://asimplepalate.com/blog/easy-lemon-chicken-piccata/",
      "score": 0.7,
      "ingredients": [
        "2 large boneless and skinless chicken breasts",
        "1/3 cup all-purpose flour",
        "3 Tablespoon salted butter",
        "1 lemon, juiced",
        "1 cup low sodium chicken broth",
        "2-3 garlic cloves",
        "capers",
        "salt & pepper",
        "fresh parsley"
      ],
      "steps": [
        "Whisk sauce ingredients...",
        "Tenderize the chicken...",
        "Dredge in flour...",
        "Brown chicken...",
        "Add sauce and simmer...",
        "Cook the chicken and serve..."
      ]
    }
  ]
}
