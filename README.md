# Vehicle Sizing API

## About

- This is a single endpoint RESTful API which when provided with one or more items to transport returns the size of the vehicle required. It was designed and built to take in a list of items in JSON as a request and would respond by sending back the appropriate vehicle in JSON.
- While designing the layout, I wanted to keep the controller small, so I added a facade that would deal with the bulk of the logic in determining the correct vehicle. 
- I had in mind to create am item class, but decided against it for simplicity, and with the assumption that the vehicle sizes would not change much. If vehicle specs needed to be changed, it would be simple to do within the facade. 
- There are two sets of test:
  - Request tests: 
    - Tested to ensure that everything was formatted correctly and responses where coming back successful and with correct body.
    - Tested different scenarios to ensure facade logic was correct. 
  - Unit tests:
    - Tested each instance method of the VehicleFacade class and the method that did the bulk of the logic when determining which vehicle would be needed based on the items dimensions. 
  

## Getting the API up and running:

- Download the file to you computer.
- Make sure to have ruby and rails installed. This API was built with the following versions:
  - ruby 2.5.3
  - Rails 6.0.4
- run `bundle install` to install the necessary gems
- run `rails db:create`
- run `rails s` to start the your local server

## Using Postman

I used postman to ensure that the data requested was returning the correct data in addition to my request_specs
- To start:
  - open postman and create a new collection to work on
  - select the `post` verb, because we are going to be inputing data for the request
  - enter `http://localhost:3000//api/v1/size_vehicle` as the request url
  - next select `Body` underneath the requested url
  - Select raw and then on make sure `JSON` is selected in the dropdown options
  - The body should be written in this format:

      ```{"items": [
        {
          "length": 5.9,
          "width": 1.8,
          "height": 61,
          "weight": 12.2,
          "quantity": 1
        },
        {
          "length": 55.9,
          "width": 20.8,
          "height": 65,
          "weight": 12.2,
          "quantity": 2
        }
      ]}
      ```

  - Once the desired dimensions are entered, hit `send` and viola! The correct vehicle should be displayed as:

      ```{
        "data": {
          "vehicle_type": "truck"
        }
      }
      ```
