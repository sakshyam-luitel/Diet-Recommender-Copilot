# API Contracts

This document outlines the REST API endpoints for the Diet Recommender application, covering authentication, recommendations, recipes, and cart functionalities.

## Authentication Endpoints

### Login
- **Endpoint:** `/api/auth/login`
- **Method:** `POST`
- **Request Body:**  
  ```json
  {
      "username": "string",
      "password": "string"
  }
  ```
- **Response:**  
  - **200 OK**  
    ```json
    {
        "token": "string",
        "user": { ... }
    }
    ```  
  - **401 Unauthorized**  
    ```json
    {
        "error": "Invalid credentials"
    }
    ```

## Recommendations Endpoints

### Get Recommendations
- **Endpoint:** `/api/recommendations`
- **Method:** `GET`
- **Headers:**  
  ```json
  {
      "Authorization": "Bearer <token>"
  }
  ```
- **Response:**  
  - **200 OK**  
    ```json
    {
        "recommendations": [{ ... }]
    }
    ```

## Recipes Endpoints

### Get Recipes
- **Endpoint:** `/api/recipes`
- **Method:** `GET`
- **Response:**  
  - **200 OK**  
    ```json
    {
        "recipes": [{ ... }]
    }
    ```

### Create Recipe
- **Endpoint:** `/api/recipes`
- **Method:** `POST`
- **Request Body:**  
  ```json
  {
      "title": "string",
      "ingredients": ["string"],
      "instructions": "string"
  }
  ```
- **Response:**  
  - **201 Created**  
    ```json
    {
        "message": "Recipe created successfully"
    }
    ```

## Cart Endpoints

### Get Cart
- **Endpoint:** `/api/cart`
- **Method:** `GET`
- **Headers:**  
  ```json
  {
      "Authorization": "Bearer <token>"
  }
  ```
- **Response:**  
  - **200 OK**  
    ```json
    {
        "cartItems": [{ ... }]
    }
    ```

### Add to Cart
- **Endpoint:** `/api/cart`
- **Method:** `POST`
- **Request Body:**  
  ```json
  {
      "recipeId": "string",
      "quantity": "number"
  }
  ```
- **Response:**  
  - **201 Created**  
    ```json
    {
        "message": "Item added to cart"
    }
    ```

---

This documentation serves as a comprehensive reference for developers integrating with the Diet Recommender API.