# GraphQL API Schema

This repository defines a comprehensive GraphQL API schema for managing users, products, categories, orders, carts, notifications, and Stripe payments.
---

## Specifications:

GRAPHQL can be checked on this link using: **schema.gql**

[GraphQL Editor](https://academy.graphqleditor.com/?lesson=tutorial)

## Scalars

### Custom Scalars
- **Date**: Represents date and time.
- **Upload**: Represents a file upload.
- **JSON**: Represents JSON-encoded data.

---

## Enums

### OrderStatus
Defines the status of an order:
- `PENDING`
- `COMPLETED`
- `CANCELED`

### Roles
Defines user roles:
- `ADMIN`
- `MANAGER`
- `CLIENT`

### StripePaymentStatus
Defines the status of Stripe payments:
- `REQUIRES_PAYMENT_METHOD`
- `REQUIRES_CONFIRMATION`
- `PROCESSING`
- `SUCCEEDED`
- `FAILED`
- `CANCELED`

### ShipmentStatus
Defines the status of a shipment:
- `PENDING`
- `PROCESSING`
- `SHIPPED`
- `DELIVERED`
- `RETURNED`
- `CANCELED`

### NotificationType
Defines types of notifications:
- `ORDER_STATUS_UPDATE`
- `LOW_STOCK_ALERT`
- `GENERAL`

---

## Inputs

### Auth Inputs
- **RegisterUserInput**: Input for user registration.
- **LoginUserInput**: Input for user login.
- **ForgetPasswordInput**: Input for password recovery.
- **ResetPasswordInput**: Input for resetting passwords.
- **UpdateInfoUserInput**: Input for updating user information.

### Categories
- **CreateCategoryInput**: Input for creating a new category.
- **UpdateCategoryInput**: Input for updating category details.

### Products
- **CreateProductInput**: Input for creating a new product.
- **UpdateProductInput**: Input for updating product details.
- **UploadImagesInput**: Input for uploading product images.

### Likes
- **ModifyLikeInput**: Input to toggle like status on a product.

### Carts
- **AddItemToCartInput**: Input for adding items to the cart.

### Orders
- **CreateOrderInput**: Input for creating an order.
- **UpdateOrderStatusInput**: Input for updating the status of an order.

---

## Types

### Core Entities
- **Users**: Represents a user.
- **Categories**: Represents a category.
- **Products**: Represents a product.
- **Carts**: Represents a shopping cart.
- **Orders**: Represents an order.
- **Notifications**: Represents notifications for users.

### Payment Types
- **PaymentIntent**: Represents a Stripe payment intent.
- **SetupIntent**: Represents Stripe setup intent details.
- **PaymentMethodOptions**: Contains options for payment methods.

### Pagination
- **ItemConnection**: Handles paginated results for products.
- **PageInfo**: Provides metadata for paginated queries.

---

## Queries

### User Queries
- `getUsers`: Retrieve all users.
- `getUser(id: ID!)`: Retrieve a user by ID.

### Product Queries
- `getProducts`: Retrieve all products.
- `getProduct(id: ID!)`: Retrieve a product by ID.
- `searchProducts`: Search products by name with pagination.

### Category Queries
- `getCategories`: Retrieve all categories.
- `getCategory(id: ID!)`: Retrieve a category by ID.

### Cart Queries
- `getCart`: Retrieve the current user's cart.

### Order Queries
- `getOrders`: Retrieve all orders for the user.
- `getOrderStatus(id: ID!)`: Retrieve the status of a specific order.

### Notification Queries
- `getNotifications`: Retrieve notifications for the user.

---

## Mutations

### Auth Mutations
- `registerUser`: Register a new user.
- `loginUser`: Authenticate a user.
- `forgetPassword`: Trigger a password recovery email.
- `resetPassword`: Reset the user's password.
- `updateUserInfo`: Update user details.

### Product Management
- `createProduct`: Create a new product.
- `updateProduct`: Update product details.
- `deleteProduct`: Delete a product.
- `uploadProductImages`: Upload product images.

### Cart Management
- `addItemToCart`: Add an item to the cart.
- `removeItemFromCart`: Remove an item from the cart.
- `clearCart`: Clear the cart.

### Order Management
- `createOrder`: Create a new order.
- `updateOrderStatus`: Update an order's payment status.
- `cancelOrder`: Cancel an order.

### Notifications
- `markNotificationAsRead`: Mark a notification as read.
- `deleteNotification`: Delete a notification.

