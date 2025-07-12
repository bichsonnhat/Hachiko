# Hachiko 🥤

A cross-platform e-commerce mobile application for beverage ordering and delivery, built with React Native Expo and Java Spring Boot. This project consists of separate frontend and backend repositories managed as git submodules.

## ✨ Features

### 🛍️ E-commerce Functionality
- **Product Catalog**: Browse and search through various beverage categories
- **Shopping Cart**: Add, remove, and manage items in your cart
- **Order Management**: Place orders, track delivery status, and view order history
- **Payment Integration**: Secure payment processing for transactions
- **User Authentication**: Account creation, login, and profile management

### 🚚 Delivery System
- **Real-time Tracking**: Track your order from preparation to delivery
- **Delivery Scheduling**: Choose preferred delivery times
- **Location Services**: GPS-based delivery address management
- **Push Notifications**: Order updates and delivery notifications

### 📱 Cross-Platform Mobile Experience
- **iOS & Android**: Native performance on both platforms
- **Responsive Design**: Optimized for various screen sizes
- **Offline Capability**: Basic functionality available without internet
- **Modern UI/UX**: Intuitive and user-friendly interface

## 🏗️ Project Structure

This repository serves as the main project container that brings together the frontend and backend components:

```
Hachiko/
├── frontend/          # React Native Expo mobile app for beverage ordering
├── backend/           # Java Spring Boot API server for e-commerce backend
├── .gitmodules        # Git submodules configuration
└── README.md          # This file
```

## 🛠️ Technologies Used

### Frontend (React Native Expo)
- **React Native**: Cross-platform mobile app development
- **Expo**: Development platform for React Native apps
- **TypeScript**: Type-safe JavaScript development
- **Expo Go**: Easy testing on physical devices
- **React Navigation**: Navigation and routing for mobile screens
- **Redux/Context API**: State management for cart and user data
- **Expo Location**: GPS and location services for delivery
- **Expo Notifications**: Push notifications for order updates

### Backend (Java Spring Boot)
- **Spring Boot**: Java framework for building REST APIs
- **Spring Data JPA**: Data persistence and database operations
- **Spring Security**: Authentication and authorization (JWT)
- **Spring Web**: RESTful API development
- **Maven**: Dependency management and build tool
- **MySQL/PostgreSQL**: Database for products, orders, and user data
- **Payment Gateway Integration**: Secure payment processing
- **WebSocket**: Real-time order tracking and notifications

## 📦 Submodules

This project uses git submodules to manage the frontend and backend repositories separately:

- **Frontend**: [`bichsonnhat/Hachiko-frontend`](https://github.com/bichsonnhat/Hachiko-frontend) - React Native Expo mobile app for beverage ordering
- **Backend**: [`bichsonnhat/Hachiko-backend`](https://github.com/bichsonnhat/Hachiko-backend) - Java Spring Boot REST API server for e-commerce and delivery management

## 🚀 Getting Started

### Prerequisites

- Git
- Node.js (for React Native Expo frontend)
- Java 11+ and Maven (for Spring Boot backend)
- Android Studio or Xcode (for mobile development)
- Expo CLI: `npm install -g expo-cli`

### 1. Clone the Repository

When cloning this repository, you need to initialize and update the submodules:

```bash
# Clone the main repository
git clone https://github.com/bichsonnhat/Hachiko.git
cd Hachiko

# Initialize and update submodules
git submodule init
git submodule update
```

**Alternative**: Clone with submodules in one command:
```bash
git clone --recurse-submodules https://github.com/bichsonnhat/Hachiko.git
```

### 2. Setup React Native Expo Frontend

```bash
cd frontend
# Install dependencies
npm install

# Start the Expo development server
npx expo start

# Follow the QR code to run on your mobile device
# Or use the emulator/simulator options
```

### 3. Setup Java Spring Boot Backend

```bash
cd backend
# Build the project
./mvnw clean install

# Run the Spring Boot application
./mvnw spring-boot:run

# The API will be available at http://localhost:8080
```

## 🔌 API Endpoints

The Spring Boot backend provides RESTful APIs for the beverage delivery app:

### Authentication & User Management
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile

### Product Catalog
- `GET /api/products` - Get all beverages
- `GET /api/products/{id}` - Get specific product details
- `GET /api/categories` - Get beverage categories
- `GET /api/products/search` - Search products

### Shopping Cart & Orders
- `POST /api/cart/add` - Add item to cart
- `GET /api/cart` - Get cart contents
- `DELETE /api/cart/{itemId}` - Remove item from cart
- `POST /api/orders` - Place an order
- `GET /api/orders` - Get order history
- `GET /api/orders/{orderId}/track` - Track order status

### Delivery & Payments
- `POST /api/payments/process` - Process payment
- `GET /api/delivery/track/{orderId}` - Real-time delivery tracking
- `POST /api/delivery/address` - Save delivery address

## 📱 Mobile Development

### Testing the React Native App

1. **On Physical Device**:
   - Install Expo Go app from App Store/Google Play
   - Scan the QR code from `npx expo start`

2. **On iOS Simulator** (macOS only):
   - Press `i` in the Expo CLI terminal
   - Requires Xcode to be installed

3. **On Android Emulator**:
   - Press `a` in the Expo CLI terminal
   - Requires Android Studio to be installed

### Building for Production

```bash
# Build for iOS
eas build --platform ios

# Build for Android
eas build --platform android
```

## 🔄 Working with Submodules

### Updating Submodules

To pull the latest changes from both submodules:

```bash
# Update all submodules to their latest commits
git submodule update --remote

# Or update a specific submodule
git submodule update --remote frontend
git submodule update --remote backend
```

### Making Changes to Submodules

1. **Navigate to the submodule directory**:
   ```bash
   cd frontend  # or backend
   ```

2. **Make your changes and commit them**:
   ```bash
   # Make changes to files
   git add .
   git commit -m "Your commit message"
   git push origin main  # or your branch name
   ```

3. **Update the main repository to point to the new commit**:
   ```bash
   cd ..  # Back to main repository
   git add frontend  # or backend
   git commit -m "Update frontend/backend submodule"
   git push origin main
   ```

### Adding New Submodules

If you need to add more submodules in the future:

```bash
git submodule add <repository-url> <directory-name>
```

## 🔧 Development Workflow

1. **Start by updating submodules**:
   ```bash
   git submodule update --remote
   ```

2. **Work on individual components**:
   - React Native Expo changes: Work in the `frontend/` directory
   - Java Spring Boot changes: Work in the `backend/` directory

3. **Commit changes to submodules first**, then update the main repository

4. **Keep submodules in sync** by regularly updating them

## 📝 Important Notes

- Each submodule is a separate git repository with its own history
- Changes to submodules need to be committed in the submodule directory first
- The main repository tracks specific commits of each submodule
- When collaborating, make sure to update submodules after pulling changes
- Always check the individual README files in `frontend/` and `backend/` for specific setup instructions

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make changes to the appropriate submodule(s)
4. Commit changes to the submodule repositories
5. Update the main repository to reference the new submodule commits
6. Submit a pull request

## 📄 License

This project is licensed under the MIT License. See the LICENSE files in the individual submodules for more details.

## 📞 Support

For issues related to:
- **Mobile App (Frontend)**: Open an issue in the [Hachiko-frontend repository](https://github.com/bichsonnhat/Hachiko-frontend/issues)
- **API Server (Backend)**: Open an issue in the [Hachiko-backend repository](https://github.com/bichsonnhat/Hachiko-backend/issues)
- **General project structure or deployment**: Open an issue in this repository

## 🎯 Development Roadmap

### Current Features
- ✅ User authentication and registration
- ✅ Product catalog and search
- ✅ Shopping cart functionality
- ✅ Order placement and tracking
- ✅ Payment processing
- ✅ Delivery management

### Planned Features
- 🔄 Real-time chat with delivery drivers
- 🔄 Loyalty program and rewards
- 🔄 Push notifications for promotions
- 🔄 Advanced analytics and reporting
- 🔄 Multi-language support
- 🔄 Dark mode theme

