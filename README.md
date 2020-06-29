# Keras REST API with Flask RESTPlus, Swagger, Gunicorn and Docker

This project is a simple boilerplate for deploying Keras models with Flask RESTPlus, Swagger, Gunicorn and Docker.

## Prerequisites

* Docker

## Installing

1. Clone this repository in your local system and navigate to root folder.

```bash
$ git clone repository-url
```

2. Navigate to `docker` folder and run.

```bash
$ cd docker
$ docker-compose up
```

### Run

This will expose on http://127.0.0.1:5000 the Swagger API docs and that's all!

## Usage

When the project is fully deployed, you will get a single endpoint. This endpoint will allow to predict house
prices by using a simple [Keras Boston house pricing](https://keras.io/api/datasets/boston_housing/) regression model loaded from a [HDF5 file](https://en.wikipedia.org/wiki/Hierarchical_Data_Format).

### House pricing

This endpoint will predict a house price by using the following [input data](http://lib.stat.cmu.edu/datasets/boston).

You must provide all these parameters as float numbers:
- crim: Per capita crime rate by town.
- zn: Proportion of residential land zoned for lots over 25,000 sq.ft.
- indus: Proportion of non-retail business acres per town.
- chas: Charles River dummy variable (= 1 if tract bounds river; 0 otherwise).
- nox: Nitric oxides concentration (parts per 10 million).'
- rm: Average number of rooms per dwelling.
- age: Proportion of owner-occupied units built prior to 1940.
- dis: Weighted distances to five Boston employment centres.
- rad: Index of accessibility to radial highways.
- tax: Full-value property-tax rate per $10,000.
- ptratio: Pupil-teacher ratio by town.
- b: 1000(Bk - 0.63)^2 where Bk is the proportion of blacks by town.
- lstat: Percentage of lower status of the population.

The endpoint will return the predicted value as a median value of owner-occupied homes in one thousand dollars.

The response with default input data:

```json
{
    "medv": 453.8800964355469, 
    "description": "Median value of owner-occupied homes in $1000's.", 
}
```

## Built With

* [Flask](http://flask.pocoo.org/) - Web framework
* [Flask-RESTPlus](https://flask-restplus.readthedocs.io/en/stable/) - Flask REST Extensions
* [Swagger](https://swagger.io/) - API Documentation
* [Keras](https://keras.io/) - Deep learning framework
* [Gunicorn](https://gunicorn.org/) - Python WSGI HTTP Server for UNIX
* [Docker](https://www.docker.com/) - Platform as a Service (PaaS) to deliver software in containers

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/vvives/keras-rest-api/tags). 

## Authors

* **Víctor Vives** - *Main developer* - [vvives](https://github.com/vvives)

See also the list of [contributors](CONTRIBUTORS.md) who participated in this project.

## License

### Project License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details