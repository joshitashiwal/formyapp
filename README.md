# Kahan Hai - Women's Safety App

A comprehensive women's safety application built with React, TypeScript, and Express.js, featuring real-time location tracking, emergency alerts, and community safety reporting.

## Features

### Core Safety Features
- **SOS Emergency Button**: One-touch emergency alerts with location sharing
- **Real-time Google Maps**: Live location tracking with police station highlighting
- **Emergency Contacts**: Manage up to 5 trusted contacts for automatic alerts
- **Safe Walk Timer**: Set check-in timers for solo journeys with automatic alerts
- **Live Location Sharing**: Share real-time location with trusted contacts
- **Fake Call Interface**: Disguised emergency interface for dangerous situations

### Community Features
- **Community Reports**: User-generated safety reports and warnings
- **Nearby Help Centers**: Find police stations, hospitals, and emergency services
- **Location-based Alerts**: Receive safety information from your area

### Security & Privacy
- **Mobile-first Design**: Optimized for smartphones with easy thumb navigation
- **Emergency Mode**: Full-screen emergency overlay with quick actions
- **Privacy Controls**: Granular location sharing permissions

## Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development and optimized builds
- **Tailwind CSS** for responsive styling
- **Shadcn/ui** components for consistent UI
- **TanStack Query** for server state management
- **Wouter** for lightweight routing

### Backend
- **Node.js** with Express.js
- **TypeScript** with ES modules
- **In-memory storage** for development (easily replaceable with PostgreSQL)
- **RESTful API** design

### External Services
- **Google Maps API** with Places service for real-time mapping
- **Geolocation API** for precise location tracking

## Getting Started

### Prerequisites
- Node.js 18+ 
- Google Maps API key with Maps JavaScript API and Places API enabled

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/kahan-hai.git
cd kahan-hai
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
# Create a .env file in the root directory
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_api_key_here
```

4. Start the development server:
```bash
npm run dev
```

The app will be available at `http://localhost:5000`

### Google Maps API Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project or select existing one
3. Enable the following APIs:
   - Maps JavaScript API
   - Places API
4. Create credentials (API Key)
5. Add the API key to your environment variables

## Project Structure

```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Main application pages
│   │   ├── hooks/         # Custom React hooks
│   │   ├── lib/           # Utility functions and configurations
│   │   └── types/         # TypeScript type definitions
├── server/                # Backend Express application
│   ├── index.ts          # Server entry point
│   ├── routes.ts         # API route definitions
│   ├── storage.ts        # Data storage interface
│   └── vite.ts           # Vite development server integration
├── shared/               # Shared code between frontend and backend
│   └── schema.ts         # Database schema and types
└── README.md
```

## API Endpoints

### Users
- `GET /api/users/:id` - Get user information
- `POST /api/users` - Create new user
- `PATCH /api/users/:id/location` - Update user location
- `PATCH /api/users/:id/online` - Update online status

### Emergency Contacts
- `GET /api/users/:userId/contacts` - Get emergency contacts
- `POST /api/emergency-contacts` - Add emergency contact
- `DELETE /api/emergency-contacts/:id` - Remove emergency contact

### SOS Alerts
- `POST /api/sos-alerts` - Create SOS alert
- `PATCH /api/sos-alerts/:id/deactivate` - Deactivate SOS alert

### Safe Walk Sessions
- `GET /api/users/:userId/safe-walk` - Get active safe walk session
- `POST /api/safe-walk` - Start safe walk session
- `PATCH /api/safe-walk/:id/checkin` - Check in to safe walk

### Community Reports
- `GET /api/community-reports` - Get all community reports
- `POST /api/community-reports` - Submit safety report

## Deployment

### Production Build
```bash
npm run build
```

### Environment Variables
Set the following environment variables in production:
- `VITE_GOOGLE_MAPS_API_KEY` - Your Google Maps API key
- `NODE_ENV=production`

### Database Migration
For production deployment, replace the in-memory storage with a proper database:
1. Update `server/storage.ts` to use your preferred database
2. Run database migrations
3. Update connection configuration

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Security Considerations

- Never commit API keys to version control
- Use HTTPS in production for geolocation access
- Implement proper authentication before production use
- Review and configure Google Maps API key restrictions
- Consider implementing rate limiting for API endpoints

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with modern web technologies for optimal performance
- Google Maps integration for real-time location services
- Designed with women's safety as the primary focus
- Community-driven safety reporting system

