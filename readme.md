![img](readme-img/logo.png)
============================

A `flask` app for quickly labeling featuers in images and recording their pixel positions.

For now, this app is specific to a datakind/give-directly project, but it might be useful for other applications in the future.

## Clone
```
git clone https://github.com/abelsonlive/dymo.git
``` 

## Requirements
Install `flask` and `redis`:
```
pip install -r requirements.txt
```

## Setup
* Startup redis:
  * `$ redis-server`
* Now, simply place the images you want to label in the `static/images` directory.  The filenames should be unique to each image and will be used as the primary key in the datastore.

## Run
`dymo` is configured to run as a simple heroku app. You can follow instructions for set up [here](https://devcenter.heroku.com/articles/redistogo#install-redis-in-python).
<br></br>
To test the applocally, run
```
python dymo.py
```
And navigate to [`http://localhost:3030/`](http://localhost:3030/) for further instructions.

## Data:

Each item looks like this:
```
{
    'roofs': [
        {
            'y': 347,
            'x': 314,
            'type': 'iron'
        },
        {
            'y': 362,
            'x': 10,
            'type': 'thatched'
        },
        {
            'y': 270,
            'x': 119,
            'type': 'thatched'
        },
        {
            'y': 178,
            'x': 186,
            'type': 'thatched'
        },
        {
            'y': 157,
            'x': 175,
            'type': 'thatched'
        }
    ],
    'image': 'KE2013071948-grass.png',
    'total': 5,
    'number_thatched': 4,
    'number_iron': 1
}
```

## Preview:

![screenshot](readme-img/screenshot.png)
