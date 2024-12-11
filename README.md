# Pet Shop Backend

## Description

This is the backend part of a pet products online store project. It implements a REST API for managing categories, products, and orders.

## Project structure

- `/database`
  - `/models`
    - `category.js`: Category model
    - `product.js`: Product model
  - `database.js`: SQLite database connection setup
- `/public`
  - `/category_img`: Category images
  - `/product_img`: Product images
- `/routes`
  - `categories.js`: Routes for working with categories
  - `order.js`: Routes for working with orders
  - `products.js`: Routes for working with products
  - `sale.js`: Routes for working with sales
- `index.js`: Main server file
- `database.sqlite`: SQLite database file
- `package.json` и `package-lock.json`: Project dependency files
- `README.md`: Project description

## Installation and setup

1. Clone the repository:

```bash
git clone <Repository URL>
```

2. Navigate to the project folder:

```bash
cd <Project folder name>
```

3. Install the dependencies:

```bash
npm install
```

4. Run the server:

```bash
npm run dev
```

The server will be started and will listen for requests on port 3333.

## API functionality test

You can test the API functionality using Postman or a browser.

### Examples of API routes:

- Get all categories: `GET /categories/all`
- Get products by category: `GET /categories/:id`
- Get all products: `GET /products/all`
- Get product by ID: `GET /products/:id`
- Place an order: `POST /order/send`
- Submit a coupon request: `POST /sale/send`

### Example request

#### Getting all categories

```bash
axios.get('http://localhost:3333/categories/all')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```

#### Placing an order

```bash
const orderData = {
  name: "John Doe",
  phone: "1234567890",
  email: "johndoe@example.com",
  products: [
    {
      id: 1,
      quantity: 2
    },
    {
      id: 2,
      quantity: 1
    }
  ]
};

axios.post('http://localhost:3333/order/send', orderData, {
  headers: {
    'Content-Type': 'application/json'
  }
})
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```

## Technologies used

- Node.js
- Express
- Sequelize
- SQLite
- Cors
- Axios