# # README

## Vehicle Sizing API

### Getting the API up and running:

- Download the file to you computer.
- Make sure to have ruby and rails installed. This API was built with the following versions:
  - ruby 2.5.3
  - Rails 6.0.4
- run `bundle install` to install the necessary gems
- run `rails s` to start the your local server

### Using Postman

I used postman to ensure that the data requested was returning the correct data in addition to my request_specs
- To start:
  - open postman and create a new collection to work on
  - select the `post` verb, because we are going to be inputing data for the request
  - enter `http://localhost:3000//api/v1/size_vehicle` as the request url
  - next select "Body" underneath the requested url
  - Select raw and then on make sure `JSON` is selected in the dropdown options
  - the body should be written in this format:
      `{"items": [
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
      ]}`
  - Once the desired dimensions are entered, hit `send` and viola! The correct vehicle should be displayed as:
      `{
        "data": {
          "vehicle_type": "truck"
        }
      }`


This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
