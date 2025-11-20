# HotelManagementHub 🏨

[![Django](https://img.shields.io/badge/Django-5.1.8-green.svg)](https://www.djangoproject.com/)
[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-✓-blue.svg)](https://www.docker.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-blue.svg)](https://www.postgresql.org/)
[![Redis](https://img.shields.io/badge/Redis-6.0+-red.svg)](https://redis.io/)
[![Elasticsearch](https://img.shields.io/badge/Elasticsearch-8.0+-green.svg)](https://www.elastic.co/)
[![Celery](https://img.shields.io/badge/Celery-✓-green.svg)](https://docs.celeryq.dev/)

HotelHub is a modern, scalable hotel management system built with Django, featuring real-time chat capabilities, comprehensive booking management, and robust user authentication. Designed for both small boutique hotels and large hotel chains, HotelHub provides a complete solution for managing accommodations, bookings, and guest communications.
## 👥  Project Owners 
- Eyyub, Ehmed, Əbil – [Eyyub](https://github.com/Eyyub01) | [Əhmed](https://github.com/hmd37) | [Əbil](https://github.com/ebilebilli)


## 🌟 Key Features

### 🔐 User Authentication & Authorization
- **JWT-based Authentication**
  - Secure token-based authentication
  - Refresh token mechanism
  - Token blacklisting for security
- **User Management**
  - Custom user model with extended fields
  - Profile management with avatar support
  - Role-based access control (Admin, Staff, Guest)
- **Security Features**
  - Password validation and hashing
  - Rate limiting for API endpoints
  - CSRF protection

### 🏢 Hotel Management
- **Hotel Operations**
  - Comprehensive hotel listing with detailed information
  - Room type management and pricing
  - Amenities and facilities tracking
  - Location-based search with geocoding
- **Room Management**
  - Dynamic room availability system
  - Room type categorization
  - Pricing and seasonal rates
  - Room status tracking

### 📅 Booking System
- **Reservation Management**
  - Real-time availability checking
  - Multi-room booking support
  - Booking modification and cancellation
  - Automated confirmation emails
- **Payment Integration**
  - Secure payment processing (coming soon)
  - Multiple payment method support
  - Refund management
  - Invoice generation

### 💬 Real-time Chat
- **Communication Features**
  - WebSocket-based chat rooms
  - Real-time messaging
  - File sharing capabilities
  - Message history
- **Room Management**
  - Private and group chat rooms
  - Room moderation tools
  - User presence indicators
  - Message notifications

### ⭐ Favorites System
- **User Preferences**
  - Save favorite hotels
  - Custom lists and categories
  - Quick access to preferred accommodations
  - Price alerts for saved hotels

### 🤖 AI-Powered Hotel & Room Info
- **OpenAI API**
  - Fetch hotel and room details
  - Generate descriptions from data
- **Features**
  - Real-time AI content
  - Enhanced data retrieval
- **Implementation**
  - Secure API key storage
  - Rate limiting for requests
  - Redis caching
  - Error handling

## 🛠️ Technology Stack

### Backend
- **Framework & Libraries**
  - Django 5.1.8 - Web framework
  - Django REST Framework - API development
  - Django Channels - WebSocket support
  - Celery - Task queue management
  - Celery Beat - Periodically check, Automatically set
  - Redis - Caching and message broker
  - Elasticsearch - Search functionality
  - DRF Spectacular - API documentation

### Database
- **Development**: SQLite
- **Production**: PostgreSQL 
- **Search**: Elasticsearch
- **Cache**: Redis

### Containerization & Deployment
- Docker
- Docker Compose
- Nginx (planned)


## 📦 Prerequisites

- Python 3.12+
- Docker and Docker Compose
- Redis 6.0+
- Elasticsearch 8.0+
- PostgreSQL 15+ (for production)

## 📚 API Documentation

The API documentation is available at:
- Swagger UI: `http://localhost:8000/api/schema/swagger-ui/`
- ReDoc: `http://localhost:8000/api/schema/redoc/`

### API Endpoints

-- **Authentication**
  - `POST /api/v1/auth/register/` - User registration
  - `POST /api/v1/auth/login/` - User login
  - `POST /api/v1/auth/refresh/` - Refresh token
  - `POST /api/v1/auth/logout/` - User logout

- **Hotels**
  - `GET /api/v1/hotels/` - List hotels
  - `POST /api/v1/hotels/` - Create hotel
  - `GET /api/v1/hotels/{id}/` - Hotel details
  - `PUT /api/v1/hotels/{id}/` - Update hotel
  - `DELETE /api/v1/hotels/{id}/` - Delete hotel
  - `GET /api/v1/hotels/{id}/photos/` - List hotel photos
  - `POST /api/v1/hotels/{id}/photos/` - Create hotel photo
  - `DELETE /api/v1/hotels/{id}/photos/{photo_id}/` - Delete hotel photo

- **Rooms**
  - `GET /api/v1/rooms/` - List rooms
  - `POST /api/v1/room/create/` - Create room
  - `GET /api/v1/room/{id}/` - Room details
  - `GET /api/v1/rooms/{id}/hotel/` - List rooms for hotel
  - `GET /api/v1/rooms/search/` - Search rooms
  - `GET /api/v1/room/photos/{id}/` - List room photos

- **Bookings**
  - `GET /api/v1/bookings/` - List bookings
  - `POST /api/v1/bookings/` - Create booking
  - `GET /api/v1/bookings/{id}/` - Booking details
  - `PUT /api/v1/bookings/{id}/` - Update booking
  - `DELETE /api/v1/bookings/{id}/` - Cancel booking

- **Favorites**
  - `GET /api/v1/favorites/` - List favorites
  - `GET /api/v1/favorite/{id}/` - Favorite details
  - `POST /api/v1/favorite/room/{id}/create/` - Create favorite for room
  - `POST /api/v1/favorite/hotel/{id}/create/` - Create favorite for hotel

- **Cities**
  - `GET /api/v1/cities/` - List cities
  - `GET /api/v1/cities/{pk}/` - City details
 
- **Ai**
  - `POST /api/v1/support/request/<int:room_id>/` - Ai support request
  - `GET /api/v1/support/response/<int:room_id>/` - Ai support response

## 🧪 Testing

### Running Tests
```bash
# Run all tests
python manage.py test

# Run specific app tests
python manage.py test accounts
python manage.py test hotels
python manage.py test bookings

# Run with coverage
coverage run --source='.' manage.py test
coverage report
```

### Test Categories
- Unit Tests
- API Tests
- Integration Tests
- WebSocket Tests

## 🔍 Code Quality


## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Pull Request Guidelines
- Follow PEP 8 style guide
- Write meaningful commit messages
- Include tests for new features
- Update documentation as needed
- Ensure all tests pass

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Django team for the amazing framework
- All contributors who have helped shape this project
- Open source community for their invaluable tools and libraries

## 📞 Support

For support, email support@hotelhub.com or join our Slack channel.

## 📁 Project Structure

```
hotelhub/
├── accounts/                 # User authentication and profile management
├── bookings/                # Booking system and reservation management
├── chat/                    # Real-time chat functionality
├── favorites/               # User favorites and saved items
├── hotels/                  # Hotel management and operations
├── rooms/                   # Room management and availability
├── utils/                   # Utility functions and helpers
├── logging/                 # Logging configuration and handlers
├── hotelhub/                # Project configuration
│   ├── settings.py          # Django settings
│   ├── urls.py              # Main URL routing
│   ├── asgi.py              # ASGI configuration
│   ├── celery.py            # Celery configuration
│   ├── wsgi.py              # WSGI configuration
│   └── middlewares/         # Custom middleware
├── docs/                    # Documentation
├── manage.py                # Django management script
├── requirements.txt         # Python dependencies
├── Pipfile                  # Pipenv dependencies
├── Dockerfile              # Docker configuration
├── docker-compose.yml      # Docker services configuration
├── Makefile                # Common commands
└── .dockerignore           # Docker ignore rules
```

### Key Components

- **accounts/**: Handles user authentication, registration, and profile management
- **bookings/**: Manages room reservations, availability, and booking operations
- **chat/**: Implements real-time messaging using WebSockets
- **favorites/**: Manages user's saved hotels and rooms
- **hotels/**: Core hotel management functionality
- **rooms/**: Room type management and availability system
- **utils/**: Shared utilities and helper functions
- **logging/**: Centralized logging configuration
- **hotelhub/**: Project configuration and settings


### Docker Setup

1. **Build and start containers**
```bash
docker-compose up --build
```

2. **Run migrations**
```bash
docker-compose exec web python manage.py migrate
```

3. **Create superuser**
```bash
docker-compose exec web python manage.py createsuperuser
```

## 🔧 Technology Stack Details

### Backend Services

- **Django 5.1.8**
  - Django REST Framework for API development
  - Django Channels for WebSocket support
  - Django Celery Beat for scheduled tasks
  - Django Debug Toolbar for development
  - Django CORS Headers for cross-origin requests

- **Database**
  - PostgreSQL 15+ for production
  - SQLite for development
  - Redis for caching and message broker
  - Elasticsearch for advanced search functionality

- **Task Queue**
  - Celery for asynchronous tasks
  - Redis as message broker
  - Flower for monitoring Celery tasks

- **Search**
  - Elasticsearch 8.0+ for full-text search
  - Django Elasticsearch DSL for integration

### Development Tools

- **Code Quality**
  - Black for code formatting
  - Flake8 for linting
  - isort for import sorting
  - mypy for type checking

- **Testing**
  - pytest for testing framework
  - pytest-django for Django integration
  - coverage for code coverage
  - factory-boy for test factories

- **Documentation**
  - DRF Spectacular for API documentation
  - Sphinx for project documentation
  - Swagger/OpenAPI for API specification

## 📊 Monitoring and Logging

### Logging Configuration
- Structured logging with JSON format
- Different log levels for development and production
- Log rotation and file management
- Integration with monitoring services

### Performance Monitoring
- Django Debug Toolbar for development
- Prometheus metrics
- Grafana dashboards
- Error tracking with Sentry

## 🔐 Security Features

- JWT-based authentication
- Rate limiting for API endpoints
- CORS protection
- CSRF protection
- Password hashing with Argon2
- Secure session management
- Input validation and sanitization
- SQL injection protection
- XSS protection

