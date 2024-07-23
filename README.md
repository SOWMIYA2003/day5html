# day5html

Node.js Setup

    Install Dependencies:

    Make sure you have Node.js installed. You will also need to install Axios for making HTTP requests.

    bash

npm install axios

Create the Node.js Application:

Create a file, e.g., app.js, and include the following code:

javascript

const axios = require('axios');

// Base URL of the book shop API
const BASE_URL = 'https://api.bookshop.com';

// Task 10: Get all books – Using async callback function
async function getAllBooks() {
    try {
        const response = await axios.get(`${BASE_URL}/books`);
        console.log('All Books:', response.data);
    } catch (error) {
        console.error('Error fetching all books:', error);
    }
}

// Task 11: Search by ISBN – Using Promises
function searchByISBN(isbn) {
    return axios.get(`${BASE_URL}/books/${isbn}`)
        .then(response => {
            console.log('Book by ISBN:', response.data);
        })
        .catch(error => {
            console.error('Error fetching book by ISBN:', error);
        });
}

// Task 12: Search by Author
async function searchByAuthor(author) {
    try {
        const response = await axios.get(`${BASE_URL}/books?author=${author}`);
        console.log('Books by Author:', response.data);
    } catch (error) {
        console.error('Error fetching books by author:', error);
    }
}

// Task 13: Search by Title
async function searchByTitle(title) {
    try {
        const response = await axios.get(`${BASE_URL}/books?title=${title}`);
        console.log('Books by Title:', response.data);
    } catch (error) {
        console.error('Error fetching books by title:', error);
    }
}

// Example Usage
getAllBooks();
searchByISBN('1234567890');
searchByAuthor('J.K. Rowling');
searchByTitle('Harry Potter');

Handling User Registration and Login:

You will need endpoints for user registration and login. Here’s a basic example using async/await:

javascript

// Task 6: Register New User
async function registerUser(userData) {
    try {
        const response = await axios.post(`${BASE_URL}/users/register`, userData);
        console.log('User Registered:', response.data);
    } catch (error) {
        console.error('Error registering user:', error);
    }
}

// Task 7: Login as a Registered User
async function loginUser(credentials) {
    try {
        const response = await axios.post(`${BASE_URL}/users/login`, credentials);
        console.log('User Logged In:', response.data);
    } catch (error) {
        console.error('Error logging in user:', error);
    }
}

Handling Book Reviews:

For adding, modifying, and deleting book reviews, you will need to handle these CRUD operations. Here's an example:

javascript

// Task 8: Add/Modify a Book Review
async function addOrModifyReview(bookId, reviewData) {
    try {
        const response = await axios.post(`${BASE_URL}/books/${bookId}/review`, reviewData);
        console.log('Review Added/Modified:', response.data);
    } catch (error) {
        console.error('Error adding/modifying review:', error);
    }
}

// Task 9: Delete Book Review
async function deleteReview(bookId, reviewId) {
    try {
        const response = await axios.delete(`${BASE_URL}/books/${bookId}/review/${reviewId}`);
        console.log('Review Deleted:', response.data);
    } catch (error) {
        console.error('Error deleting review:', error);
    }
}

Submission of Project GitHub Link:

Ensure your project is hosted on GitHub and include the link in your submission.
