# Blood Pressure Monitoring Application with AI Integration

A comprehensive blood pressure tracking application developed for both mobile and web platforms, integrating artificial intelligence for enhanced health monitoring and personalized recommendations.

## Overview

This project aims to revolutionize blood pressure management by providing users with precise tools and personalized recommendations to improve their quality of life. The application consists of two main components:
- **Mobile Application** (Flutter): Patient-focused interface for blood pressure tracking
- **Web Application** (Next.js): Doctor dashboard for patient management and analysis

## Features

### For Patients (Mobile App)
- **Blood Pressure Tracking**: Manual entry and OCR-based image recognition from blood pressure devices
- **Data Visualization**: Interactive charts showing blood pressure trends over time
- **Medication Management**: Track medications with intelligent reminder system
- **Activity Monitoring**: BMI calculator and physical activity tracking
- **Real-time Chat**: Communicate directly with healthcare providers
- **Appointment Scheduling**: Book and manage medical appointments
- **Smart Notifications**: AI-powered alerts and personalized recommendations

### For Healthcare Providers (Web App)
- **Patient Management**: Comprehensive patient database and profiles
- **Analytics Dashboard**: Real-time statistics and health insights
- **Communication Hub**: Chat system for patient interaction
- **Appointment Calendar**: Schedule and manage patient appointments
- **AI-Powered Analysis**: Automated health assessments and treatment recommendations
- **Medical Records**: Complete patient history and examination results

## Technology Stack

### Frontend
- **Mobile**: Flutter (Cross-platform)
- **Web**: Next.js, React, TypeScript
- **Styling**: Tailwind CSS, ShadCN UI Components

### Backend
- **API**: Laravel (PHP)
- **Architecture**: Repository Pattern (Interface → Repository → Service → Controller)
- **Authentication**: JWT tokens + Firebase Auth

### Database & Storage
- **Primary Database**: MongoDB Atlas
- **Real-time Database**: Firebase Realtime Database

### AI & Machine Learning
- **OCR**: Hugging Face OCR-Donut-CORD model
- **AI Integration**: OpenAI API for health recommendations

### Development Tools
- **IDE**: Visual Studio Code
- **API Testing**: Postman
- **Version Control**: Git & GitHub
- **Project Management**: Notion
- **UML Modeling**: Astah UML

## System Architecture

The application follows a layered architecture approach:

```
┌─────────────────┐    ┌─────────────────┐
│   Flutter App   │    │   Next.js App   │
│   (Mobile)      │    │   (Web)         │
└─────────┬───────┘    └─────────┬───────┘
          │                      │
          └──────────┬───────────┘
                     │
            ┌────────▼────────┐
            │   Laravel API   │
            │   (Backend)     │
            └────────┬────────┘
                     │
          ┌──────────┼──────────┐
          │          │          │
    ┌─────▼─────┐ ┌──▼──┐ ┌─────▼─────┐
    │ MongoDB   │ │Firebase│ │ Hugging  │
    │ Atlas     │ │       │ │ Face OCR │
    └───────────┘ └───────┘ └───────────┘
```

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- Flutter SDK
- PHP (v8.0 or higher)
- Composer
- MongoDB Atlas account
- Firebase project

### Backend Setup (Laravel)
```bash
# Clone the repository
git clone https://github.com/username/blood-pressure-app.git
cd blood-pressure-app/backend

# Install dependencies
composer install

# Environment configuration
cp .env.example .env
php artisan key:generate

# Configure database and Firebase credentials in .env
php artisan migrate

# Start the server
php artisan serve
```

### Frontend Setup (Next.js Web App)
```bash
cd frontend-web
npm install
npm run dev
```

### Mobile App Setup (Flutter)
```bash
cd mobile-app
flutter pub get
flutter run
```

## Key Features Implementation

### OCR Integration
The application uses Hugging Face's OCR-Donut-CORD model to automatically extract blood pressure readings from device photos:
- Camera integration for capturing blood pressure monitor displays
- Automatic data extraction and form filling
- Manual verification and correction capabilities

### AI-Powered Recommendations
- Personalized health insights based on blood pressure trends
- Medication timing optimization
- Lifestyle recommendations using OpenAI integration

### Real-time Communication
Firebase-powered chat system enabling:
- Instant messaging between patients and doctors
- Message synchronization across devices
- Online status indicators

## API Documentation

### Authentication Endpoints
- `POST /api/login` - User authentication
- `POST /api/register` - User registration
- `POST /api/forgot-password` - Password recovery
- `POST /api/reset-password` - Password reset

### Patient Endpoints
- `GET /api/patients` - Retrieve patient list
- `POST /api/patients` - Create new patient
- `GET /api/patients/{id}` - Get patient details
- `PUT /api/patients/{id}` - Update patient information

### Blood Pressure Endpoints
- `GET /api/blood-pressure` - Get blood pressure records
- `POST /api/blood-pressure` - Create new BP record
- `POST /api/blood-pressure/ocr` - Process BP image via OCR

### Appointments Endpoints
- `GET /api/appointments` - Retrieve appointments
- `POST /api/appointments` - Schedule new appointment
- `PUT /api/appointments/{id}` - Update appointment status

## Methodology

The project follows **Agile SCRUM** methodology with:
- Daily standups with supervisors
- Sprint-based development cycles
- Kanban board for task management
- Continuous integration and testing

## Database Schema

### Users Collection
```json
{
  "_id": "ObjectId",
  "username": "string",
  "email": "string",
  "password": "hashed_string",
  "role": "patient|doctor",
  "profile_completed": "boolean",
  "created_at": "datetime"
}
```

### Blood Pressure Exams Collection
```json
{
  "_id": "ObjectId",
  "patient_id": "ObjectId",
  "systolic": "number",
  "diastolic": "number",
  "date": "datetime",
  "notes": "string"
}
```

### Appointments Collection
```json
{
  "_id": "ObjectId",
  "patient_id": "ObjectId",
  "doctor_id": "ObjectId",
  "date": "datetime",
  "status": "pending|accepted|rejected",
  "notes": "string"
}
```

## Security Features

- JWT token authentication
- Firebase authentication as secondary layer
- Data encryption for sensitive medical information
- Role-based access control
- Secure API endpoints with validation

## Testing

### Running Tests
```bash
# Backend tests
php artisan test

# Frontend tests
npm run test

# Mobile app tests
flutter test
```

## Deployment

### Mobile App
- **Android**: Build APK for Google Play Store
- **iOS**: Build IPA for App Store

### Web Application
- **Platform**: Vercel (recommended)
- **Build Command**: `npm run build`
- **Environment Variables**: Configure Firebase and API keys

### Backend API
- **Platform**: Any PHP hosting service
- **Requirements**: PHP 8.0+, MongoDB, SSL certificate

## Contributing

This project was developed as an academic exercise. For questions or collaboration opportunities, please reach out through appropriate academic channels.

## Academic Context

This project was developed as a final year internship project at:
- **Institution**: École Supérieure De Technologie-Safi
- **University**: Université Cadi Ayyad, Morocco
- **Program**: Information Systems and Networks Engineering
- **Academic Year**: 2023/2024

**Student**: Rekhla Zakaria  
**Supervisors**: 
- M. EL Abdellaoui Said
- Mme. Kachbal Ilham

**Host Organization**: Norsys Afrique

## Future Enhancements

- Advanced ML models for health prediction
- Integration with wearable devices
- Multi-language support
- Telemedicine video consultation
- Advanced analytics and reporting
- Integration with hospital systems

## License

This project is developed for academic purposes under the supervision of École Supérieure De Technologie-Safi.

## References

- [Next.js Documentation](https://nextjs.org/docs)
- [Flutter Documentation](https://docs.flutter.dev)
- [Laravel Documentation](https://laravel.com/docs)
- [Firebase Documentation](https://firebase.google.com/docs)
- [Hugging Face OCR Models](https://huggingface.co/models?pipeline_tag=image-to-text)
