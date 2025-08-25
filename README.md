# BracU Lost and Found

The BRACU Lost and Found platform serves as an efficient system for managing lost and found items within the BRAC University community. This web application allows students, faculty, and staff to post details about items they've found on campus, including location, date, and description, making it easier for owners to reclaim their belongings.

## Project Overview

This platform is designed to create a community-driven lost and found system specifically for BRAC University. It helps reconnect lost items with their rightful owners through a structured process of posting, claiming, and verification.

### Key Features

- **User Authentication System**: Secure signup/login functionality with password reset capabilities
- **Lost Item Posting**: Users can create detailed posts about found items with images
- **Location-based Filtering**: Search for items by specific campus locations
- **Claim Verification**: Secure process for item owners to claim their belongings with proof
- **Admin Moderation**: Admin panel to verify claims and manage the system
- **Point System**: Reward mechanism for users who find and report items
- **Profile Management**: Comprehensive user profiles with contact information
- **Communication Tools**: Contact forms and feedback mechanisms
- **Notification System**: Email notifications for important updates and claim status
- **PDF Generation**: Capability to generate ownership certificates

## Architecture

### Technology Stack

- **Frontend**: HTML, CSS, JavaScript, Bootstrap
- **Backend**: Django (Python web framework)
- **Database**: MySQL
- **Email Services**: Django's email backend using SMTP
- **PDF Generation**: xhtml2pdf

### System Components

#### Models
1. **UserModel**: Manages user accounts and profiles
2. **PostModel**: Stores information about lost/found items
3. **ClaimOwner**: Handles claim requests from potential item owners
4. **ResetPwdTokens**: Manages password reset functionality
5. **UserContact**: Stores user contact messages
6. **UserFeedback**: Collects user feedback
7. **BkashPayment**: Handles payment transactions for the point system

#### Core Functionality
1. **Authentication System**: Handles user registration, login, and profile management
2. **Post Management**: Creates, displays, and filters lost/found item posts
3. **Claim Processing**: Manages the claiming process with verification steps
4. **Admin Operations**: Admin-specific functions for system management
5. **Communication System**: Contact forms, feedback mechanisms, and email notifications
6. **Point Management**: System for tracking and rewarding user contributions

#### File Structure
- **home/**: Main Django application containing models, views, and business logic
- **lost_and_found/**: Project configuration and settings
- **templates/**: HTML templates for the frontend
- **static/**: CSS, JavaScript, and image files
- **uploads/**: Storage for user-uploaded images
- **manage.py**: Django command-line utility

### Database Schema

The application uses MySQL with the following core tables:
- **app_users**: User account information
- **user_posts**: Lost/found item post details
- **claim_owner**: Information about item claims
- **reset_pwd_tokens**: Password reset tokens
- **users_contacts**: User contact messages
- **users_feedbacks**: User feedback data
- **bkash_payment**: Payment transaction records

### Authentication Flow

1. Users register with name, email, and password
2. Email verification ensures valid accounts
3. Password reset via email token mechanism
4. Session-based authentication maintains user state

### Post and Claim Process

1. User creates a post with item details, location, and images
2. Potential owners can claim items through a verification process
3. Admin reviews and approves/rejects claims based on evidence
4. On approval, contact details are shared between parties
5. Points are deducted from claimers as a service fee

### Point System

- Users receive points upon registration
- Posting found items rewards additional points
- Claiming items requires spending points
- Points can be purchased through Bkash payment

## Implementation Details

### Security Features

- Password hashing using Django's authentication system
- CSRF protection for form submissions
- Session management for authenticated users
- Restricted access to sensitive functionality

### Responsive Design

The frontend uses Bootstrap to ensure the application works well on various devices and screen sizes.

### Email Integration

The system uses SMTP for sending emails for:
- Password reset links
- Claim acceptance/rejection notifications
- Point purchase confirmations

### File Handling

- Secure image upload for found items and verification
- Unique filename generation using timestamps
- Support for multiple image types

### Admin Interface

- Dashboard for managing users, posts, and claims
- Point addition approval system
- User management capabilities

## Getting Started

### Prerequisites

- Python 3.x
- Django 3.2+
- MySQL
- Required Python packages (see below)

### Installation

1. Clone the repository
   ```
   git clone [repository-url]
   ```

2. Install required packages
   ```
   pip install -r requirements.txt
   ```

3. Configure database settings in lost_and_found/settings.py

4. Run migrations
   ```
   python manage.py migrate
   ```

5. Start the development server
   ```
   python manage.py runserver
   ```

### Required Packages

- Django
- mysqlclient
- Pillow
- reportlab
- xhtml2pdf

## Usage

1. Register a new account
2. Complete your profile with contact information
3. Browse posted items filtered by location
4. Create posts for found items
5. Claim items by providing verification
6. Contact post creators through the system
7. Manage your account and points

## Acknowledgements

Developed as a project for CSE-471 at BRAC University.