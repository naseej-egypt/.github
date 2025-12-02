# Naseej - Egyptian Handmade Carpets E-Commerce Platform

<div align="center">

![Naseej Logo](https://via.placeholder.com/200x200/8B4513/FFFFFF?text=Naseej)

**Preserving Egyptian Heritage Through Technology**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Flutter](https://img.shields.io/badge/Flutter-3.0+-02569B?logo=flutter)](https://flutter.dev)
[![PHP](https://img.shields.io/badge/PHP-7.4+-777BB4?logo=php)](https://php.net)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

[Features](#features) • [Architecture](#architecture) • [Getting Started](#getting-started) • [Documentation](#documentation) • [Contributing](#contributing)

</div>

---

## 🎯 About

Naseej is a comprehensive, full-stack e-commerce ecosystem dedicated to authentic Egyptian handmade carpets. Built with modern technologies and a focus on cultural authenticity, this platform connects three generations of Egyptian carpet craftsmanship with customers worldwide.

### Platform Components

Our platform consists of three interconnected applications:

| Component | Technology | Purpose | Repository |
|-----------|-----------|---------|------------|
| **Customer App** | Flutter | Mobile shopping experience | [naseej-app](./naseej-app) |
| **Admin Panel** | Flutter | Business management dashboard | [naseej-admin-app](./naseej-admin-app) |
| **Backend API** | PHP | RESTful API service | [naseej-backend](./naseej-backend) |

---

## ✨ Key Highlights

### 🛍️ Customer Experience
- **Seamless Shopping**: Browse, filter, and purchase authentic Egyptian carpets
- **Multi-Language Support**: Arabic, English, French, German, and Spanish
- **Smart Features**: Favorites, cart persistence, real-time search
- **Order Tracking**: Real-time order status updates
- **Multiple Payment Options**: Cash on delivery and online payments
- **Store Locator**: Find physical stores with distance calculation

### 👨‍💼 Business Management
- **Comprehensive Dashboard**: Real-time analytics and sales insights
- **Product Management**: Complete CRUD operations with image handling
- **Order Processing**: Status tracking and delivery assignment
- **Customer Management**: Profile tracking and analytics
- **Delivery Management**: Personnel tracking and performance monitoring
- **Multi-Store Support**: Physical store network management

### 🔧 Technical Excellence
- **RESTful API**: Clean, standardized endpoints
- **JWT Authentication**: Secure token-based sessions
- **Role-Based Access**: Customer, Admin, and Delivery personnel roles
- **Real-Time Updates**: Live notifications and inventory tracking
- **Email Integration**: OTP verification and notifications
- **Offline Support**: Connectivity detection and handling

---

## 🏗️ Architecture

### System Overview

```
┌─────────────────────────────────────────────────────────────┐
│                     Naseej Platform                          │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌─────────────┐      ┌─────────────┐      ┌─────────────┐ │
│  │   Customer  │      │    Admin    │      │   Delivery  │ │
│  │  Mobile App │      │    Panel    │      │  Personnel  │ │
│  │  (Flutter)  │      │  (Flutter)  │      │   (Future)  │ │
│  └──────┬──────┘      └──────┬──────┘      └──────┬──────┘ │
│         │                    │                     │         │
│         │                    │                     │         │
│         └────────────────────┼─────────────────────┘         │
│                              │                               │
│                     ┌────────▼────────┐                      │
│                     │   Backend API   │                      │
│                     │   (PHP/MySQL)   │                      │
│                     │                 │                      │
│                     │  - JWT Auth     │                      │
│                     │  - RESTful      │                      │
│                     │  - Email        │                      │
│                     │  - File Upload  │                      │
│                     └────────┬────────┘                      │
│                              │                               │
│                     ┌────────▼────────┐                      │
│                     │  MySQL Database │                      │
│                     │                 │                      │
│                     │  - Products     │                      │
│                     │  - Orders       │                      │
│                     │  - Customers    │                      │
│                     │  - Analytics    │                      │
│                     └─────────────────┘                      │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

### Technology Stack

#### Frontend (Mobile Apps)
- **Framework**: Flutter 3.0+
- **State Management**: GetX
- **Architecture**: Service Layer + Repository Pattern
- **Networking**: HTTP package
- **Storage**: Shared Preferences
- **UI Components**: Custom widgets + Material Design

#### Backend API
- **Language**: PHP 7.4+
- **Database**: MySQL 5.7+ / MariaDB 10.2+
- **Architecture**: MVC + Service Layer
- **Authentication**: JWT tokens
- **Email**: PHPMailer
- **File Handling**: Native PHP with validation

---

## 🚀 Getting Started

### Prerequisites

- **For Mobile Apps**:
  - Flutter SDK (>=3.0.0)
  - Dart SDK (>=3.0.0)
  - Android Studio / VS Code
  - iOS Simulator / Android Emulator

- **For Backend**:
  - PHP (>=7.4, 8.0+ recommended)
  - MySQL (>=5.7) or MariaDB (>=10.2)
  - Apache/Nginx with mod_rewrite
  - Composer
  - SSL Certificate (production)

### Quick Start

#### 1. Clone the Repositories

```bash
# Clone the organization
git clone https://github.com/your-org/naseej-platform.git
cd naseej-platform

# Or clone individual repositories
git clone https://github.com/your-org/naseej-backend.git
git clone https://github.com/your-org/naseej-app.git
git clone https://github.com/your-org/naseej-admin-app.git
```

#### 2. Setup Backend API

```bash
cd naseej-backend

# Install dependencies
composer install

# Configure database (config/database.php)
# Import database schema
mysql -u username -p database_name < database/schema.sql

# Configure constants (config/constants.php)
# Set permissions
chmod -R 755 upload/
chmod -R 755 config/

# Test the API
php -S localhost:8000
```

#### 3. Setup Customer App

```bash
cd naseej-app

# Install dependencies
flutter pub get

# Configure API endpoint (lib/core/constant/linkapi.dart)
# Run the app
flutter run
```

#### 4. Setup Admin Panel

```bash
cd naseej-admin-app

# Install dependencies
flutter pub get

# Configure API endpoint (lib/services/api_service.dart)
# Run the app
flutter run
```

---

## 📚 Documentation

### Repository Documentation

Each repository contains detailed documentation:

- **[Backend API Documentation](./naseej-backend/README.md)**: Complete API reference, endpoints, authentication
- **[Customer App Documentation](./naseej-app/README.md)**: Features, screens, user flows
- **[Admin Panel Documentation](./naseej-admin-app/README.md)**: Management features, analytics

### API Documentation

#### Base URL
```
https://your-domain.com/api/
```

#### Authentication
All authenticated endpoints require JWT token:
```
Authorization: Bearer {your_jwt_token}
```

#### Standard Response Format

**Success:**
```json
{
  "status": "success",
  "message": "Operation completed successfully",
  "data": { }
}
```

**Error:**
```json
{
  "status": "error",
  "message": "Error description",
  "errors": { }
}
```

### Quick Links

- [API Endpoints Reference](./naseej-backend/README.md#api-documentation)
- [Customer App Features](./naseej-app/README.md#features)
- [Admin Panel Guide](./naseej-admin-app/README.md#features)
- [Database Schema](./naseej-backend/database/schema.sql)

---

## 🎨 Features Overview

### Customer Mobile App

| Category | Features |
|----------|----------|
| **Shopping** | Product browsing, Advanced filtering, Search, Cart management |
| **Account** | Registration, Email verification, Profile management, Order history |
| **Orders** | Checkout, Order tracking, Reorder, Cancellation |
| **Favorites** | Wishlist, Quick add/remove, Favorite products view |
| **Stores** | Store locator, Distance calculation, Store pickup |
| **Settings** | Theme selection, Language preferences, Notifications |

### Admin Panel

| Category | Features |
|----------|----------|
| **Dashboard** | Sales analytics, Revenue tracking, Charts, PDF export |
| **Products** | CRUD operations, Image management, Stock tracking, Categories |
| **Orders** | Order processing, Status updates, Delivery assignment |
| **Customers** | Customer database, Analytics, Status management |
| **Delivery** | Personnel management, Performance tracking, Assignment |
| **Stores** | Store network management, Operating hours, Locations |
| **Admins** | User management, Role assignment, Password management |

### Backend API

| Feature | Description |
|---------|-------------|
| **Authentication** | JWT tokens, OTP verification, Password reset |
| **Products** | Full CRUD, Image uploads, Search, Filtering |
| **Orders** | Order processing, Status tracking, Payment management |
| **Cart** | Session management, Real-time calculations |
| **Notifications** | Real-time alerts, Email integration |
| **Analytics** | Dashboard stats, Sales reports, Insights |

---

## 🔐 Security

### Implemented Measures

- **Authentication**: JWT token-based authentication with expiry
- **Password Security**: Bcrypt hashing for all passwords
- **Input Validation**: Server-side and client-side validation
- **SQL Injection Prevention**: Prepared statements and parameterized queries
- **XSS Protection**: Output encoding and sanitization
- **CSRF Protection**: Token validation for state-changing operations
- **File Upload Security**: Type validation, size limits, secure storage
- **Role-Based Access**: Granular permissions for different user types

### Best Practices

- Always use HTTPS in production
- Regularly update dependencies
- Store sensitive data in environment variables
- Implement rate limiting on API endpoints
- Regular security audits and penetration testing

---

## 📱 Supported Platforms

### Customer & Admin Apps

| Platform | Minimum Version | Tested Version |
|----------|----------------|----------------|
| Android | API 21 (Android 5.0) | API 33 (Android 13) |
| iOS | iOS 12.0 | iOS 16.0 |

### Backend API

| Component | Version |
|-----------|---------|
| PHP | 7.4+ (8.0+ recommended) |
| MySQL | 5.7+ |
| MariaDB | 10.2+ |

---

## 🤝 Contributing

We welcome contributions from the community! Please read our [Contributing Guidelines](CONTRIBUTING.md) before submitting pull requests.

### How to Contribute

1. **Fork** the repository you want to contribute to
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Development Guidelines

- Follow the coding standards for each technology (Flutter Style Guide, PSR for PHP)
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Run linters before committing (`flutter analyze`, `phpcs`)

---

## 📊 Project Stats

### Lines of Code
- **Backend API**: ~15,000 lines (PHP)
- **Customer App**: ~20,000 lines (Dart/Flutter)
- **Admin Panel**: ~18,000 lines (Dart/Flutter)

### Features Count
- **API Endpoints**: 100+
- **Mobile Screens**: 40+ (Customer + Admin)
- **Database Tables**: 20+
- **Supported Languages**: 5

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📧 Contact & Support

### Project Team

- **Technical Lead**: Yasser Ashraf
- **Email**: yasserashraf3142@gmail.com
- **Organization**: Naseej Platform

### Support Channels

- **Technical Issues**: Open an issue in the relevant repository
- **Feature Requests**: Use the discussions section
- **Security Concerns**: Email yasserashraf3142@gmail.com directly

### Links

- **Website**: [www.naseej.com](https://www.naseej.com) (coming soon)
- **Documentation**: [docs.naseej.com](https://docs.naseej.com) (coming soon)
- **API Status**: [status.naseej.com](https://status.naseej.com) (coming soon)

---

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- GetX community for excellent state management
- Egyptian artisan community for inspiring this project
- Open source contributors worldwide
- All users and testers who provided valuable feedback

---

## 🗺️ Roadmap

### Version 1.1 (Q2 2024)
- [ ] Payment gateway integration (Stripe, PayPal)
- [ ] Push notifications
- [ ] In-app chat support
- [ ] Product reviews and ratings
- [ ] Wishlist sharing

### Version 1.2 (Q3 2024)
- [ ] Delivery personnel mobile app
- [ ] Advanced analytics dashboard
- [ ] Multi-currency support
- [ ] Augmented Reality carpet preview
- [ ] Social media integration

### Version 2.0 (Q4 2024)
- [ ] Web application (Customer & Admin)
- [ ] AI-powered product recommendations
- [ ] Voice search
- [ ] Blockchain-based authenticity certificates
- [ ] Virtual showroom

---

## 📚 Additional Resources

### Learning Resources
- [Flutter Documentation](https://docs.flutter.dev/)
- [GetX Documentation](https://pub.dev/packages/get)
- [PHP Documentation](https://www.php.net/docs.php)
- [RESTful API Design](https://restfulapi.net/)

### Related Projects
- [Egyptian Heritage Apps](https://github.com/topics/egyptian-heritage)
- [E-Commerce Solutions](https://github.com/topics/ecommerce)
- [Flutter E-Commerce](https://github.com/topics/flutter-ecommerce)

---

<div align="center">

**Made with ❤️ for preserving Egyptian heritage through technology**

[⬆ Back to Top](#naseej---egyptian-handmade-carpets-e-commerce-platform)

</div>
