# Oraculum Architecture - Slide Content

## Component Summary (4-5 bullets each):

### Frontend
 Web and mobile client built with React and Flutter
 Provides user interface for profile management, career guidance, and mock interviews
 Handles user authentication and secure API communication
 Supports cross-platform deployment for maximum accessibility
 Implements responsive design for optimal user experience

### Auth/API
 API Gateway manages request routing and authentication
 Firebase Auth provides secure user authentication and authorization
 Implements OAuth 2.0 and JWT token-based security
 Handles rate limiting and request validation
 Provides unified API interface for all client applications

### Profile Service
 Cloud Functions-based service for user data management
 Stores and retrieves user profiles, skills, and preferences
 Integrates with Firestore for real-time data synchronization
 Emits events for profile updates to trigger downstream processes
 Supports user privacy and data compliance requirements

### Recommendation Service (Vertex AI)
 Leverages Google Vertex AI for machine learning capabilities
 Provides personalized career recommendations based on user profiles
 Implements custom ML models for skill gap analysis
 Integrates with search services for content discovery
 Supports continuous learning and model retraining

### Interview Service (Gemini/STT/TTS)
 Mock interview functionality using Google Gemini AI
 Speech-to-text conversion for voice-based interviews
 Text-to-speech for AI interviewer responses
 Real-time feedback and scoring using AI models
 Stores interview recordings and transcripts securely

### Data Storage (Firestore, Cloud Storage)
 Firestore provides NoSQL database for user data and profiles
 Cloud Storage handles file uploads and media content
 Implements data encryption and backup strategies
 Supports real-time data synchronization across services
 Ensures data consistency and ACID compliance

### Pub/Sub
 Event-driven architecture for asynchronous processing
 Handles profile update events and recommendation triggers
 Manages background tasks and data pipeline processing
 Provides reliable message delivery and error handling
 Supports microservices communication and decoupling

### CI/CD
 Cloud Build automates deployment pipelines
 Supports both frontend and backend deployment workflows
 Implements automated testing and quality gates
 Enables blue-green deployments and rollback capabilities
 Integrates with monitoring and alerting systems

### Monitoring
 Cloud Monitoring provides comprehensive observability
 Tracks system performance, errors, and user metrics
 Integrates with BigQuery for data analytics and reporting
 Implements alerting for critical system events
 Supports capacity planning and performance optimization

## How It Works (One Paragraph):

Oraculum operates as a comprehensive student career guidance platform that combines modern web technologies with advanced AI capabilities. Students interact through a responsive React/Flutter frontend that communicates with a secure API Gateway, which routes requests to specialized microservices including profile management, AI-powered career recommendations, and mock interview functionality. The system leverages Google Cloud's Vertex AI for machine learning, Gemini for conversational AI, and Firestore for real-time data storage, while an event-driven architecture using Pub/Sub ensures scalable and reliable processing. The entire platform is deployed and monitored through automated CI/CD pipelines, providing students with personalized career guidance, skill assessments, and interview preparation tools powered by cutting-edge artificial intelligence.

## Windows Local Render Commands:

```cmd
REM Download PlantUML JAR and Graphviz
curl -L -o plantuml.jar https://github.com/plantuml/plantuml/releases/download/v1.2024.8/plantuml-1.2024.8.jar
curl -L -o graphviz-installer.msi https://graphviz.org/download/windows/graphviz-installer-10.0.1-64bit.msi

REM Install Graphviz (run as administrator)
msiexec /i graphviz-installer.msi /quiet

REM Add Graphviz to PATH (add to system environment variables)
REM C:\Program Files\Graphviz\bin

REM Render PlantUML to SVG
java -jar plantuml.jar -tsvg oraculum-architecture.puml

REM Render PlantUML to PNG
java -jar plantuml.jar -tpng oraculum-architecture.puml

REM Alternative with Graphviz path
java -Djava.awt.headless=true -jar plantuml.jar -tsvg -graphvizdot "C:\Program Files\Graphviz\bin\dot.exe" oraculum-architecture.puml
```
