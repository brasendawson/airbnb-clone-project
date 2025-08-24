# airbnb-clone-project
## Technology Stack
- **Django:** A high-level Python web framework used for building the RESTful API.
- **Django REST Framework:** Provides tools for creating and managing RESTful APIs.
- **PostgreSQL:** A powerful relational database used for data storage.
- **GraphQL:** Allows for flexible and efficient querying of data.
- **Celery:** For handling asynchronous tasks such as sending notifications or processing payments.
- **Redis:** Used for caching and session management.
- **Docker:** Containerization tool for consistent development and deployment environments.
- **CI/CD Pipelines:** Automated pipelines for testing and deploying code changes.

## Team Roles
- **Backend Developer:** Responsible for implementing API endpoints, database schemas, and business logic.
- **Database Administrator:** Manages database design, indexing, and optimizations.
- **DevOps Engineer:** Handles deployment, monitoring, and scaling of the backend services.
- **QA Engineer:** Ensures the backend functionalities are thoroughly tested and meet quality standards.

## Database Design
The database design for the Airbnb clone project includes the following key entities:

### Users
- **User ID:** Unique identifier for each user
- **Email:** User's email address for authentication and communication
- **Name:** User's full name
- **Password:** Securely hashed password
- **Profile Picture:** Image representation of the user

### Properties
- **Property ID:** Unique identifier for each property
- **Owner ID:** Foreign key referencing the User who owns the property
- **Title:** Name/title of the property
- **Description:** Detailed description of the property
- **Price per Night:** Cost to rent the property

### Bookings
- **Booking ID:** Unique identifier for each booking
- **Property ID:** Foreign key referencing the booked Property
- **Guest ID:** Foreign key referencing the User making the booking
- **Check-in Date:** Date when the booking starts
- **Check-out Date:** Date when the booking ends

### Reviews
- **Review ID:** Unique identifier for each review
- **Booking ID:** Foreign key referencing the Booking
- **Rating:** Numerical rating (e.g., 1-5 stars)
- **Comment:** Textual review of the property
- **Date Created:** When the review was submitted

### Payments
- **Payment ID:** Unique identifier for each payment
- **Booking ID:** Foreign key referencing the Booking
- **Amount:** Total amount paid
- **Payment Status:** Current status of the payment (pending, completed, refunded)
- **Payment Method:** Method used for the payment

### Entity Relationships
- A User can have multiple Properties (one-to-many)
- A User can make multiple Bookings as a guest (one-to-many)
- A Property can have multiple Bookings (one-to-many)
- A Booking belongs to one Property and one User (many-to-one)
- A Booking can have one Review (one-to-one)
- A Booking can have one Payment (one-to-one)

## Feature Breakdown

### User Management
The user management system handles user registration, authentication, and profile management. It enables users to create accounts, log in securely, and manage their personal information, providing a foundation for personalized experiences within the platform.

### Property Management
Property management allows property owners to list their spaces, upload photos, set pricing, and specify availability. This feature empowers hosts to showcase their properties effectively and manage their listings, driving the supply side of the marketplace.

### Booking System
The booking system facilitates the reservation process, allowing guests to search for properties, view availability, and make reservations. It handles the core transaction logic of the platform, connecting guests with available properties based on their criteria and managing the booking lifecycle.

### Review and Rating System
This feature enables guests to leave feedback about their stays and hosts to review guests. By creating a transparent feedback mechanism, it builds trust in the community and helps future users make informed decisions about properties and guests.

### Payment Processing
The payment system securely handles financial transactions between guests and hosts. It manages payment collection, holding funds in escrow until check-in, and distributing payments to hosts after successful stays, ensuring a secure and reliable financial experience for all parties.

### Search and Filtering
This feature allows users to find properties based on various criteria such as location, price range, amenities, and availability dates. By providing advanced search capabilities, it enhances user experience and helps guests find exactly what they're looking for.

### Messaging System
The messaging system facilitates communication between hosts and guests before, during, and after bookings. It enables users to ask questions, coordinate check-ins, and address any issues that arise, fostering clear communication throughout the rental process.

## API Security

### Authentication and Authorization
The API implements robust authentication using JWT (JSON Web Tokens) and role-based authorization controls. This security measure is crucial for protecting user accounts, preventing unauthorized access to personal information, and ensuring users can only perform actions they're permitted to do.

### Data Encryption
All sensitive data, including personal information and payment details, is encrypted both in transit and at rest. Encryption is essential for protecting user privacy, meeting regulatory requirements like GDPR, and preventing data breaches that could compromise user trust.

### Rate Limiting
API rate limiting prevents abuse by limiting the number of requests a client can make within a specific timeframe. This security feature is important for preventing denial-of-service attacks, reducing the impact of automated scraping, and ensuring fair system usage for all clients.

### Input Validation and Sanitization
All user inputs are thoroughly validated and sanitized before processing. This practice is critical for preventing injection attacks (SQL, NoSQL, XSS), ensuring data integrity, and maintaining the reliability of the application's functionality.

### Secure Headers and CORS
The API implements secure HTTP headers and Cross-Origin Resource Sharing (CORS) policies. These measures are vital for preventing cross-site scripting attacks, clickjacking, and unauthorized API access from malicious websites, creating a secure boundary around the application.

## CI/CD Pipeline

Continuous Integration and Continuous Deployment (CI/CD) pipelines automate the testing, building, and deployment processes of our application. These automated workflows ensure that code changes are thoroughly tested before being deployed to production, reducing the risk of introducing bugs and improving the overall quality of the application.

### Key Components

- **Automated Testing:** Each code commit triggers automated unit, integration, and end-to-end tests to verify functionality.
- **Code Quality Checks:** Static code analysis tools automatically review code for potential issues and enforce coding standards.
- **Containerization:** Docker is used to package the application and its dependencies into containers, ensuring consistency across different environments.
- **Deployment Automation:** Successful builds are automatically deployed to staging environments for further testing before being promoted to production.

### Tools Used

- **GitHub Actions:** For automating workflows directly from the GitHub repository
- **Docker:** For containerizing the application
- **Pytest:** For Python unit and integration testing
- **Black and Flake8:** For code formatting and linting
- **PostgreSQL Test Containers:** For testing database interactions
