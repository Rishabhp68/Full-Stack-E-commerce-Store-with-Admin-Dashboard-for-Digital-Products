# Full Stack Nextjs E-commerce Store with Admin Dashboard for Digital Products

Welcome to the Full Stack Nextjs E-commerce Store with Admin Dashboard for Digital Products project! This repository contains a comprehensive solution for a digital image e-commerce platform built with Next.js, Prisma, Stripe, and Tailwind CSS. This application includes an admin dashboard for managing Digital Products and processing orders, with automated email notifications for successful purchases and order history. Note that this project does not include a shopping cart, digital gallery, or user authentication.

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Admin Dashboard**: A powerful backend interface to manage Digital Products and monitor orders.
- **Product Management**: Add, update, and remove Digital Products from the store.
- **Order Management**: View and manage orders, including payment status and detailed order information.
- **Stripe Payment Integration**: Secure payment processing with Stripe, including webhook support for payment confirmation.
- **Email Notifications**: Automated emails sent using Resend to confirm successful purchases and provide order history.
- **Responsive Design**: Tailwind CSS ensures a responsive design that works well on all devices.

## Technologies

This project uses the following technologies:

- **Next.js**: React framework for server-side rendering and static site generation.
- **Prisma**: ORM for database management and interactions.
- **Stripe**: Payment gateway for processing transactions with webhook support.
- **Resend**: Service for sending emails, used for purchase confirmations and order history notifications.
- **Tailwind CSS**: Utility-first CSS framework for styling.

## Installation

To set up the project locally, follow these steps:

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/fullstack-ecommerce-digital-images.git
   cd fullstack-ecommerce-digital-images
   ```

2. **Install Dependencies**:

   ```bash
   npm install
   ```

## Configuration

1. **Database Configuration**: Create a `.env` file in the root directory with your database connection string:

   ```plaintext
   DATABASE_URL=your-database-connection-string
   ```

2. **Stripe Configuration**: Add your Stripe keys to the `.env` file:

   ```plaintext
   STRIPE_SECRET_KEY=your-stripe-secret-key
   NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
   ```

3. **Resend Configuration**: Add your Resend API key to the `.env` file:

   ```plaintext
   RESEND_API_KEY=your-resend-api-key
   ```

4. **Prisma Setup**: Run Prisma migrations to set up your database schema:

   ```bash
   npx prisma migrate dev
   ```

5. **Build and Seed Data**: If you have seed data, add it and run:

   ```bash
   npx prisma db seed
   ```

6. **Stripe Webhooks**: Configure Stripe webhooks to handle payment confirmations. To test Stripe webhooks in development, you need to forward events to your local endpoint. Open a separate terminal window and run:

   ```bash
   stripe listen --forward-to localhost:3000/webhooks/stripe
   ```

   Ensure that your Stripe webhook endpoint is set up to handle events such as `checkout.session.completed`.

## Usage

1. **Run Development Server**:

   ```bash
   npm run dev
   ```

   Access the application at `http://localhost:3000`.

2. **Build for Production**:

   ```bash
   npm run build
   npm run start
   ```

## Deployment

For deployment, you can use platforms like Vercel, Heroku, or any other provider that supports Next.js applications.

To deploy on Vercel:

1. Push your code to GitHub.
2. Sign up or log in to [Vercel](https://vercel.com/).
3. Import your GitHub repository into Vercel.
4. Configure environment variables in the Vercel dashboard.
5. Deploy your application.

## Contributing

Contributions are welcome! To contribute to this project:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes and commit (`git commit -am 'Add feature'`).
4. Push your branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

Please ensure that your code adheres to the project's coding standards and passes all tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to reach out with any questions or feedback. Enjoy building and using your e-commerce store!