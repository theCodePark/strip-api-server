# CodePark Stripe Server

This repository contains the server-side code for handling payments using Stripe in CodePark's application. It allows you to process payments for CodePark Summer Camp.

## Prerequisites

Before running this code, ensure that you have the following set up:

- Node.js installed on your machine.
- A Stripe account and API keys. If you don't have one, you can sign up for free at [Stripe](https://stripe.com/).
- An environment file (`.env`) with your Stripe API secret key (`STRIPE_SECRET_TEST`) and (`STRIPE_SECRET_LIVE`).

## Installation

1. Clone this repository to your local machine.
2. Install the dependencies by running the following command in the project directory:

   ```shell
   npm install
   ```

## Configuration

1. Create a `.env` file in the project directory.
2. Add your Stripe API secret key to the `.env` file:

   ```
   STRIPE_SECRET_TEST=your_stripe_api_secret_key
   ```

## Usage

To start the server, run the following command:

```shell
npm run start
```

The server will listen on the specified port (default is 4000) or the port specified in the environment variable `PORT`.

To deploy the server to Heroku, follow the instructions in the [Heroku documentation](https://devcenter.heroku.com/articles/git).

```shell
heroku login
git add --a
git commit -m "commit message"
git push heroku master
```

## Endpoints

### POST /payment

This endpoint is used to process a payment for CodePark Summer Camp. It expects the following parameters in the request body:

- `amount` (number): The payment amount in USD.
- `id` (string): The Stripe payment method ID.

The server will create a payment intent using the Stripe API with the provided amount, payment method, and description. If the payment is successful, it will return a JSON response with the following structure:

```json
{
  "message": "Payment successful",
  "success": true
}
```

If an error occurs during the payment process, the server will return a JSON response with the following structure:

```json
{
	"message": "Payment failed: <error message>",
  "success": false
}
```

## Contributing

If you'd like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push the branch to your fork.
4. Submit a pull request explaining your changes.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any inquiries, please contact CodePark at [info@codepark.com](mailto:info@codepark.com).