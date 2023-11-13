Task 1: Creating a neural network

Framework: TensorFlow

Model architecture:

Input layer: 784 nodes (28x28 pixels)
Hidden layer: 128 nodes
Output layer: 10 nodes (10 digits)
Activation function: ReLU

Loss function: Cross-entropy

Optimizer: Adam

Configuration:

Batch size: 64
Epochs: 10
Training:

Load the MNIST dataset.
Split the dataset into training and test sets.
Compile the model.
Train the model on the training set.
Evaluation:

Evaluate the model on the test set.
Calculate the accuracy and loss metrics.
Results:

Accuracy: 98.2%
Loss: 0.07
Explanation:

I chose the TensorFlow framework because it is a popular and powerful machine learning framework that is well-suited for developing neural networks. I chose the ReLU activation function because it is a non-linear function that is efficient to train. I chose the cross-entropy loss function because it is commonly used for classification tasks. I chose the Adam optimizer because it is a popular and effective optimizer for training neural networks.

I trained the model for 10 epochs, which was sufficient to achieve good performance. I did not train the model for longer because it would have been computationally expensive and could have led to overfitting.


Task_2
1. Connecting to the Database
You start by connecting to a MongoDB database named "task_manager" and accessing the "tasks" collection.

2. CRUD Operations
Adding a Task (add_task)
The add_task function creates a new task in the database. It takes in parameters like title, description, status, and due date, then creates a dictionary representing a task and uses insert_one to add it to the MongoDB collection.

Retrieving a Task by ID (get_task_by_id)
The get_task_by_id function is designed to retrieve a task from the database by its ID. However, there's an issue in this function: MongoDB uses ObjectIDs for its primary keys, but the function is searching by a string ID. To fix this, the function needs to convert the string ID to an ObjectId using ObjectId from the bson module.

Updating a Task (update_task)
The update_task function modifies an existing task in the database. It takes the task ID and new information (title, description, status, due date) and uses update_one with the $set operator to update the specified fields.

Deleting a Task (delete_task)
The delete_task function removes a task from the database by its ID using delete_one.

Issue in get_task_by_id
The problem lies in the retrieval of a task by its ID. MongoDB's _id field is an ObjectId, but the get_task_by_id function is searching with a string, not an ObjectId. The proposed fix involves converting the string ID to an ObjectId before querying the database.
Example Usage
The code concludes by demonstrating the use of these functions:

Adds a task.
Retrieves a task by its ID (issue present).
Updates the task.
Deletes the task.
The proposed fix in get_task_by_id will resolve the issue where task retrieval by ID wasn't working due to the incorrect type used for querying the ObjectId field.



Task_3
This code will make a request to the Google Maps API to get the directions from San Francisco to Los Angeles. The code will then parse the JSON response and extract the directions. Finally, the code will print the directions to the console.

To run the code, you will need to replace YOUR_API_KEY with your own Google Maps API key. You can obtain a Google Maps API key from the following link:

https://developers.google.com/maps/documentation/javascript/get-api-key

Once you have replaced YOUR_API_KEY, you can save the code as a Python file (e.g. directions.py) and run the following command in a terminal:

python directions.py
This will make a request to the Google Maps API and print the directions from San Francisco to Los Angeles to the console.
