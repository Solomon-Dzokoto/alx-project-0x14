# MoviesDatabase API Documentation

## API Overview
The MoviesDatabase API provides comprehensive access to a vast database of movies, TV shows, and related entertainment content. It offers detailed information about titles, including cast, crew, ratings, release dates, and more.

## Version
Current API Version: v1.0

## Available Endpoints
- `/titles`: Get list of movies/shows with filtering options
- `/titles/{id}`: Get detailed information about a specific title
- `/titles/search`: Search for titles by various criteria
- `/titles/x/upcoming`: Get upcoming releases
- `/actors`: Get information about actors
- `/genres`: Get list of available genres

## Request and Response Format
### Request Format
```http
GET /titles HTTP/1.1
Host: moviesdatabase.p.rapidapi.com
X-RapidAPI-Key: your-api-key
X-RapidAPI-Host: moviesdatabase.p.rapidapi.com
```

### Response Format
```json
{
  "page": 1,
  "next": "/titles?page=2",
  "entries": 10,
  "results": [
    {
      "id": "string",
      "primaryImage": {
        "url": "string"
      },
      "titleText": {
        "text": "string"
      },
      "releaseYear": {
        "year": "number"
      }
    }
  ]
}
```

## Authentication
Authentication is handled through RapidAPI:
1. Sign up for a RapidAPI account
2. Subscribe to the MoviesDatabase API
3. Use your API key in the X-RapidAPI-Key header
4. Include X-RapidAPI-Host: moviesdatabase.p.rapidapi.com in headers

## Error Handling
Common error responses:
- 400: Bad Request - Check request parameters
- 401: Unauthorized - Invalid or missing API key
- 403: Forbidden - Usage limits exceeded
- 429: Too Many Requests - Rate limit reached
- 500: Internal Server Error - API service issue

## Usage Limits and Best Practices
- Basic tier: 100 requests per day
- Rate limit: 10 requests per second
- Cache responses when possible
- Use specific endpoints instead of search when possible
- Include error handling in your application
- Implement retry logic for failed requests
- Keep your API key secure
