<<<<<<< HEAD
# BACKEND-PROACTIVELY
![image](https://github.com/user-attachments/assets/27152036-08ae-4a4d-89c8-7f50e2b33bde)
=======
# Collaborative Form Filling System

A real-time collaborative form filling system that allows multiple users to work together on a single form response, similar to Google Docs but for structured forms.

## Features

### Admin Features
- Create multiple forms with dynamic fields (text, number, dropdown, textarea)
- Define field requirements and options
- Generate unique share codes for form access
- Manage form participants

### User Features
- Join forms using share codes
- Real-time collaborative editing
- See live updates as others type
- Visual indicators for field locks and active participants

### Real-time Features
- WebSocket-based real-time synchronization
- Field-level locking to prevent conflicts
- Live participant tracking
- Instant updates across all connected users

## Tech Stack

### Backend
- **Next.js 14** with App Router - Full-stack framework
- **PostgreSQL** (via Neon) - Primary database for persistent data
- **In-Memory Store** - Real-time state management for participants and field locks
- **Socket.IO** - WebSocket implementation for real-time communication
- **JWT** - Authentication and authorization

### Frontend
- **React 18** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **shadcn/ui** - UI components

## Architecture Decisions

### Database Choice: PostgreSQL + In-Memory Store
- **PostgreSQL**: Chosen for ACID compliance and complex relational queries needed for forms, fields, and user management
- **In-Memory Store**: Custom implementation for real-time state (active participants, field locks) that needs fast read/write operations

### Real-time Strategy: WebSockets
- **Socket.IO**: Provides reliable real-time bidirectional communication
- **Field-level locking**: Prevents conflicts by locking fields during editing
- **Participant tracking**: Real-time awareness of who's actively editing

### Conflict Resolution Strategy
1. **Field Locking**: When a user focuses on a field, it gets locked for other users
2. **Visual Indicators**: Locked fields show who is currently editing
3. **Automatic Unlocking**: Fields unlock when users blur or disconnect
4. **Debounced Updates**: Changes are sent after 500ms of inactivity to reduce network traffic

## Setup Instructions

### Prerequisites
- Node.js 18+ 
- PostgreSQL database (Neon recommended)

### Environment Variables
Create a \`.env.local\` file with:

\`\`\`env
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret_key
\`\`\`

### Installation

1. Clone the repository
\`\`\`bash
git clone <repository-url>
cd collaborative-forms
\`\`\`

2. Install dependencies
\`\`\`bash
npm install
\`\`\`

3. Set up the database
\`\`\`bash
# Run the SQL scripts in order
# Execute scripts/01-create-tables.sql
# Execute scripts/02-seed-data.sql
\`\`\`

4. Start the development server
\`\`\`bash
npm run dev
\`\`\`

5. Open [http://localhost:3000](http://localhost:3000)

## API Endpoints

### Authentication
- \`POST /api/auth/login\` - User login/registration

### Forms Management
- \`GET /api/forms\` - Get user's forms
- \`POST /api/forms\` - Create new form (admin only)
- \`GET /api/forms/[id]\` - Get form details
- \`POST /api/forms/join\` - Join form with share code

### WebSocket Events
- \`join-form\` - Join a form room
- \`update-field\` - Update field value
- \`lock-field\` - Lock field for editing
- \`unlock-field\` - Release field lock

## Usage

### For Admins
1. Login with your credentials
2. Go to "Create Form" tab
3. Define form title, description, and fields
4. Share the generated share code with participants

### For Users
1. Login with your credentials
2. Go to "Join Form" tab
3. Enter the share code provided by admin
4. Start collaborating on the form

### Sample Data
The system includes sample data:
- Admin user: admin@example.com
- Sample form with share code: TEAM2024
- Regular users: user1@example.com, user2@example.com

## Key Features Implemented

### Real-time Synchronization
- Instant field updates across all participants
- Live participant list with join/leave notifications
- Field locking with visual indicators

### Conflict Resolution
- Field-level locking prevents simultaneous edits
- Automatic lock release on disconnect
- Visual feedback for locked fields

### Scalability Considerations
- Redis for fast real-time operations
- Debounced updates to reduce server load
- Indexed database queries for performance
- Connection pooling for database efficiency

### Security
- JWT-based authentication
- Role-based access control
- Form access validation
- SQL injection prevention with parameterized queries

## Deployment

The application is designed to be deployed on platforms like:
- **Vercel** (recommended for Next.js)
- **Railway**
- **Render**

Ensure environment variables are configured in your deployment platform.

## Future Enhancements

- File upload fields
- Form templates
- Advanced field validation
- Export responses to CSV/PDF
- Form analytics and insights
- Mobile app support
- Advanced conflict resolution (operational transforms)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

MIT License - see LICENSE file for details

## Important Notes

### In-Memory Store Limitations
- **Server Restart**: All real-time state (participants, locks) is lost when the server restarts
- **Single Instance**: Works only with single server instance (not suitable for load balancing without sticky sessions)
- **Memory Usage**: State grows with active users and forms

For production use with multiple server instances, consider upgrading to Redis or another distributed cache solution.
>>>>>>> 34fdcfb (Initial commit)
