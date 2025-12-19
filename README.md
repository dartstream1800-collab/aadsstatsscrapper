# Atlantic Amateur Dart Series - Stats Tracker

A comprehensive event-based dart statistics tracking system that automatically scrapes match data from DartConnect and provides detailed player profiles across the entire series.

## 🎯 Features

### Event-Based Tracking
- **Individual Event Stats**: Each AADS event (Events 1-7 + Tournament of Champions) is tracked separately
- **Event-Specific Player Profiles**: Players have individual performance records for each event they participate in
- **Overall Series Statistics**: Combined stats across all events for championship qualification tracking

### Automated Data Scraping
- **One-Click Event Processing**: Simply enter a DartConnect event URL to automatically extract all match data
- **Smart Data Processing**: Automatically extracts player performance, match results, and statistical data
- **Event Metadata**: Captures event name, date, and tournament structure information

### Comprehensive Player Profiles
- **Per-Event Performance**: View how a player performed in each individual event
- **Series Progression**: Track player improvement and consistency across the series
- **Statistical Breakdown**: Averages, 180s, high finishes, and more for both individual events and overall series

### Championship Qualification
- **Qualification Tracking**: Monitor which players have qualified for the Tournament of Champions
- **Series Leaderboard**: Overall rankings across all events in the series
- **Performance Analysis**: Identify top performers and consistent players

## 🏗️ Technical Architecture

### Backend - Supabase
- **PostgreSQL Database**: Robust relational database with proper event-player relationships
- **Edge Functions**: Serverless functions for data processing and API endpoints
- **Real-time Subscriptions**: Live data updates as new events are processed

### Frontend - GitHub Pages
- **Single Page Application**: Modern, responsive interface for viewing stats
- **Real-time Updates**: Live data loading from Supabase APIs
- **Mobile Responsive**: Works seamlessly on desktop, tablet, and mobile devices

### Data Pipeline
- **DartConnect Integration**: Direct API integration with DartConnect's match system
- **Event Processing**: Intelligent parsing of tournament structures and match results
- **Data Normalization**: Clean, consistent data storage for reliable statistics

## 🚀 Getting Started

### For Users
1. **Visit the Stats Tracker**: Navigate to the GitHub Pages site
2. **Scrape an Event**: Enter a DartConnect event URL in the scraping interface
3. **Explore the Data**: Browse individual event stats, overall leaderboards, and player profiles
4. **Track Progress**: Monitor series progression and championship qualification

### For Developers
1. **Clone the Repository**
   ```bash
   git clone https://github.com/dartstream1800-collab/aadsstatsscrapper.git
   cd aadsstatsscrapper
   ```

2. **Set Up Supabase**
   - Create a new Supabase project
   - Run the database migrations (see `/migrations` folder)
   - Deploy the Edge Functions (see `/functions` folder)

3. **Configure Environment**
   - Update API endpoints in `index.html`
   - Set up Supabase environment variables

4. **Deploy**
   - Enable GitHub Pages for the repository
   - The site will be automatically deployed from the `main` branch

## 📊 Database Schema

### Core Tables
- **`events`**: Individual tournament events with metadata
- **`matches`**: Individual dart matches with results
- **`aads_players`**: Overall player statistics across the series
- **`player_performances`**: Event-specific player performance data

### Views
- **`aads_leaderboard`**: Overall series rankings
- **`aads_qualified_players`**: Championship qualified players
- **`aads_event_summary`**: Event completion and participation summary

## 🔧 API Endpoints

### Event Management
- `GET /events` - List all events in the series
- `GET /event-stats?event_id={id}` - Get event-specific player statistics
- `POST /scrape-event` - Process a new event from DartConnect URL

### Player Data
- `GET /stats` - Overall series leaderboard
- `GET /player-profile?player_name={name}` - Individual player profile with event breakdown
- `GET /qualified` - Championship qualified players

### Series Information
- `GET /series-summary` - Overall series progress and statistics
- `GET /health` - API health check

## 🎮 Event Types Supported

The system is specifically designed for the Atlantic Amateur Dart Series structure:

1. **Regular Events (Events 1-6)**: Individual tournaments with their own leaderboards
2. **Tournament of Champions (Event 7)**: Championship event for qualified players
3. **Special Events**: Additional tournaments that count toward overall series statistics

## 📈 Statistics Tracked

### Individual Event Stats
- Event-specific averages and performance
- Legs played in that event
- 180s and high finishes for the event
- Event ranking and placement

### Overall Series Stats
- Combined average across all events
- Total legs played in the series
- Total 180s and maximum scores
- Series ranking and qualification status
- Consistency metrics across events

## 🏆 Championship Qualification

The system automatically tracks championship qualification based on:
- Minimum event participation requirements
- Performance consistency across multiple events
- Overall series ranking and averages
- Special qualification criteria as defined by series rules

## 🔄 Data Flow

1. **Event URL Input**: User enters a DartConnect event URL
2. **API Integration**: System fetches match data from DartConnect API
3. **Data Processing**: Matches are parsed and player statistics are calculated
4. **Database Storage**: Event-specific and overall statistics are stored
5. **Real-time Updates**: Frontend displays updated statistics and rankings

## 📱 User Interface

### Navigation Sections
- **📊 Scrape Event**: Add new event data
- **🎯 Events**: Browse individual event statistics
- **🏆 Overall Leaderboard**: Series-wide player rankings
- **✨ Championship**: Qualified players and standings
- **🔍 Player Search**: Individual player profile lookup
- **📈 Series Summary**: Overall series progress and statistics

### Features
- **Responsive Design**: Works on all device sizes
- **Real-time Loading**: Live data updates from the API
- **Interactive Tables**: Click players to view detailed profiles
- **Event Navigation**: Easy switching between individual event views
- **Search Functionality**: Quick player profile lookup

## 🛠️ Development

### Prerequisites
- Node.js and npm (for local development)
- Supabase account and project
- GitHub account for hosting

### Local Development
```bash
# Install dependencies (if using build tools)
npm install

# Start local development server
npm start

# Or simply open index.html in a browser for static development
```

### Deployment
The application is automatically deployed to GitHub Pages when changes are pushed to the `main` branch.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **DartConnect**: For providing the tournament data API
- **Supabase**: For the robust backend infrastructure
- **GitHub Pages**: For free and reliable hosting
- **Atlantic Amateur Dart Series**: For the inspiration and tournament structure

## 📞 Support

For questions, issues, or feature requests:
1. Open an issue on GitHub
2. Check the documentation in this README
3. Review existing issues for similar problems

---

**Built with ❤️ for the Atlantic Amateur Dart Series community**