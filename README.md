# DONEX - Blood Donor Finder

A web application to connect blood donors with those in need, featuring real-time location-based donor search and MapTiler integration.

## Features

- User registration and authentication
- Blood donor registration and management
- Location-based donor search with distance calculation
- Interactive maps with MapTiler tiles
- Responsive design for mobile and desktop

## Tech Stack

- **Backend**: Node.js, Express.js, SQLite
- **Frontend**: HTML, CSS, JavaScript, Leaflet Maps
- **Authentication**: JWT tokens
- **Maps**: MapTiler Free Tier + OpenStreetMap fallback
- **Deployment**: Vercel (serverless)

## Local Development

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file with the following variables:
   ```
   PORT=3000
   JWT_SECRET=your-secret-key-change-this-in-production
   DB_NAME=donex.db
   MAPTILER_API_KEY=your-maptiler-api-key
   ```
4. Start the development server:
   ```bash
   npm start
   ```
5. Open `http://localhost:3000` in your browser

## Vercel Deployment

The application is configured for Vercel deployment:

### Environment Variables in Vercel

Set the following environment variables in your Vercel dashboard:

- `JWT_SECRET`: Your JWT secret key (generate a secure random string)
- `MAPTILER_API_KEY`: Your MapTiler API key (4RXxPEKTXQsy9daiMART)

### Deploy Steps

1. Push your code to GitHub
2. Connect your GitHub repository to Vercel
3. Vercel will automatically detect the configuration and deploy
4. Your app will be available at: `https://your-app-name.vercel.app`

### Database Note

Since Vercel uses serverless functions, SQLite database persistence may be limited. Consider using a cloud database service like PlanetScale or Railway for production deployments.

## API Endpoints

- `POST /api/register` - User registration
- `POST /api/login` - User authentication
- `POST /api/donors` - Search for donors (requires authentication)
- `GET /api/config` - Get client-side configuration

## Project Structure

```
/donex
├── server.js          # Express server and API routes
├── vercel.json        # Vercel deployment configuration
├── package.json       # Dependencies and scripts
├── .env              # Environment variables (local only)
├── index.html        # Landing page
├── login.html        # Login page
├── register.html     # Registration page
├── dashboard.html    # Main dashboard with map
├── styles.css        # Global styles
├── dashboard.js      # Dashboard functionality
├── script.js         # General scripts
└── donex.db          # SQLite database (local only)
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

ISC License - see package.json for details
