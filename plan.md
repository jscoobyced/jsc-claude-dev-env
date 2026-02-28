# Real-Estate Flipping Marketplace - Implementation Plan

## Project Overview
A full-stack marketplace website connecting property owners with real-estate flippers. Owners can list damaged/old properties they want to sell, and flippers can browse and make enquiries. The application features a modern React frontend with TypeScript, Express.js backend with PostgreSQL, and support for multiple languages.

## Tech Stack

### Frontend
- **Framework**: React 18+ with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS v4
- **Package Manager**: yarn
- **Testing**: Jest with React Testing Library
- **Linting**: ESLint with TypeScript support
- **State Management**: Context API / React Hooks (simple) or Redux (if complexity grows)

### Backend
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL
- **Authentication**: JWT (JSON Web Tokens)
- **File Upload**: Local storage in backend
- **Package Manager**: yarn
- **Testing**: Jest
- **Linting**: ESLint with TypeScript support
- **Email**: Email notifications for enquiries

### Repository Structure
```
project-root/
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── vite.config.ts
│   ├── tailwind.config.js
│   ├── jest.config.js
│   └── eslint.config.js
├── backend/
│   ├── src/
│   ├── package.json
│   ├── jest.config.js
│   └── eslint.config.js
└── README.md
```

## Data Models

### Users
- User ID (primary key)
- Email (unique)
- Password (hashed with bcrypt)
- Name
- Phone
- User Type (FLIPPER or OWNER)
- Profile Picture
- Bio/Description
- Timestamps (created_at, updated_at)

### Flippers (extends Users)
- Specializations (types of properties)
- Portfolio Projects (count)
- Rating/Reviews

### Owners (extends Users)
- Company Name (optional)
- Tax ID (optional)

### Properties (Listings)
- Property ID
- Owner ID (foreign key)
- Title
- Description
- Location (address, city, state, zip)
- Coordinates (latitude, longitude)
- Property Type (single-family, multi-family, commercial, etc.)
- Square Footage
- Year Built
- Condition (poor, fair, needs-work, etc.)
- Asking Price
- Images (multiple, stored locally)
- Status (active, sold, archived)
- Timestamps (created_at, updated_at)

### Enquiries
- Enquiry ID
- Property ID (foreign key)
- Flipper ID (foreign key)
- Message
- Contact Info
- Status (pending, contacted, accepted, rejected)
- Timestamps (created_at, updated_at)

## Feature Implementation Plan

### Phase 1: Core Infrastructure & Auth
1. **Backend Setup**
   - Initialize Express.js project with TypeScript
   - Set up database connection (PostgreSQL)
   - Create User and Property data models
   - Implement JWT authentication middleware
   - Set up CORS and error handling

2. **Frontend Setup**
   - Initialize Vite + React + TypeScript project
   - Set up Tailwind CSS
   - Create folder structure (components, pages, hooks, utils, services)
   - Set up routing with React Router
   - Create language/i18n setup (JS file translations)

### Phase 2: Authentication Features
3. **User Registration**
   - Backend: Create registration endpoint (flipper & owner)
   - Backend: Password hashing with bcrypt
   - Frontend: Registration form with validation
   - Frontend: Error handling and success messages

4. **User Login**
   - Backend: Login endpoint returning JWT token
   - Frontend: Login form
   - Frontend: Token storage (localStorage/sessionStorage)
   - Frontend: Protected routes implementation

### Phase 3: User Profiles
5. **Flipper Profile Page**
   - Backend: GET /api/flippers/:id endpoint
   - Frontend: Display flipper info, portfolio, ratings
   - Frontend: Edit profile functionality (if viewing own profile)

6. **Owner Profile Page**
   - Backend: GET /api/owners/:id endpoint
   - Frontend: Display owner info
   - Frontend: Edit profile functionality (if viewing own profile)

### Phase 4: Property Listings
7. **Owner Listings Page**
   - Backend: GET /api/properties?owner_id=X endpoint with pagination
   - Frontend: Display user's own properties
   - Frontend: List view with basic property info

8. **Property Creation**
   - Backend: POST /api/properties endpoint with file upload handling
   - Backend: Image upload and storage to local filesystem
   - Frontend: Multi-step form for property creation
   - Frontend: Image upload with preview

9. **Property Update**
   - Backend: PUT /api/properties/:id endpoint
   - Frontend: Edit property form
   - Frontend: Image management (add/remove images)

### Phase 5: Search & Discovery
10. **Search Results Page**
    - Backend: GET /api/properties/search endpoint with filters
    - Backend: Implement text search and advanced filters (location, price, type, condition)
    - Frontend: Search form with filters
    - Frontend: Results grid/list view with pagination
    - Frontend: Skeleton loading while fetching

11. **View Property Page**
    - Backend: GET /api/properties/:id endpoint
    - Frontend: Full property details with images carousel
    - Frontend: Flipper enquiry form component
    - Frontend: Contact owner information (if authenticated flipper)

### Phase 6: Enquiry System
12. **Property Enquiry**
    - Backend: POST /api/enquiries endpoint
    - Backend: Email notification to property owner
    - Frontend: Enquiry form component on property page
    - Frontend: Success/error messages
    - Backend: Enquiry history tracking

### Phase 7: Static Pages
13. **Home Page**
    - Frontend: Hero section with engaging copy
    - Frontend: Search panel for finding owners/flippers
    - Frontend: Call-to-action buttons (Register as Flipper/Owner)
    - Frontend: Featured properties carousel
    - Frontend: Statistics or testimonials section

14. **Terms of Use Page**
    - Frontend: Static page with ToU content
    - Frontend: Accessible, scrollable content

15. **Privacy Policy Page**
    - Frontend: Static page with Privacy Policy content
    - Frontend: Accessible, scrollable content

### Phase 8: Multi-Language Support & Polish
16. **Internationalization (i18n)**
    - Frontend: Set up translation system to load from CDN
    - Frontend: Language selector component
    - Frontend: Dynamic language switching
    - Frontend: Fallback to default language

17. **UI/UX Polish**
    - Frontend: Implement skeleton loaders for all data-loading pages
    - Frontend: Add loading states for async operations
    - Frontend: Error boundaries and error pages
    - Frontend: Responsive design (mobile, tablet, desktop)

## Non-Functional Requirements

### Performance
- Skeleton components for all async-loaded data
- Image optimization and lazy loading
- Pagination for large lists
- Database query optimization with proper indexes

### Security
- Password hashing with bcrypt
- JWT token validation on all protected routes
- CORS configuration
- Input validation and sanitization
- SQL injection prevention (use parameterized queries)
- CSRF protection (consider for future)

### Internationalization
- Translations as JavaScript files from CDN
- Support for multiple languages with fallback
- Language preference persisted in user profile or localStorage

### Testing
- Unit tests for utility functions
- Component tests for React components
- API integration tests for backend endpoints
- Jest coverage target: 70%+

### Code Quality
- ESLint for code style
- TypeScript strict mode enabled
- Pre-commit hooks (optional but recommended)

## API Endpoints Overview

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/refresh-token` - Refresh JWT token

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update user profile
- `GET /api/flippers/:id` - Get flipper profile
- `GET /api/owners/:id` - Get owner profile

### Properties
- `GET /api/properties` - List properties with pagination
- `GET /api/properties/search` - Search with filters
- `GET /api/properties/:id` - Get single property
- `POST /api/properties` - Create property (owner only)
- `PUT /api/properties/:id` - Update property (owner only)
- `DELETE /api/properties/:id` - Delete property (owner only)
- `GET /api/properties/:owner_id/owner-listings` - Get owner's listings

### Enquiries
- `POST /api/enquiries` - Create enquiry
- `GET /api/enquiries/:id` - Get enquiry details
- `GET /api/enquiries/property/:property_id` - Get enquiries for property

## Implementation Order & Dependencies

1. **Infrastructure** (Database, Backend setup, Frontend setup) - Phase 1
2. **Authentication** (Registration, Login) - Phase 2 - depends on Phase 1
3. **User Profiles** - Phase 3 - depends on Phase 2
4. **Property Management** (Create, Read, Update) - Phase 4 - depends on Phase 2
5. **Search & Discovery** - Phase 5 - depends on Phase 4
6. **Enquiry System** - Phase 6 - depends on Phase 5
7. **Static Pages & Home** - Phase 7 - can be partially done in parallel
8. **i18n & Polish** - Phase 8 - depends on all previous phases

## Development Notes

- Use environment variables for configuration (database URL, JWT secret, email settings)
- Implement proper error handling on both frontend and backend
- Add request validation on backend (schema validation with joi or similar)
- Implement rate limiting on authentication endpoints
- Consider using database migrations for schema management
- Keep frontend components modular and reusable
- Use TypeScript strict mode for type safety
- Document API endpoints (consider Swagger/OpenAPI for future)

## Deployment Considerations

- Frontend: Can be deployed to static hosting (Vercel, Netlify, GitHub Pages)
- Backend: Deploy to Node.js hosting (Heroku, AWS EC2, DigitalOcean, Railway)
- Database: Managed PostgreSQL service (AWS RDS, DigitalOcean)
- Images: Store locally initially, migrate to cloud storage if scaling
- Email: Configure with SendGrid or similar SMTP service
- Translations: Host translation files on CDN (AWS CloudFront, Cloudflare, etc.)
