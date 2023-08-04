# YaPracticum - Sprint 11 - «API for YaTube»

## Description:
YaTube is a prototype for a social media network. The functionality allows registered users to publish and comment on posts, as well as to subscribe to other authors.


## Installation:
Clone the repository:
```
git clone git@github.com:tekut/api_final_yatube.git
```

Create and activate the virtual environment:
```
python -m venv env
```
```
source env/bin/activate
```

Install the dependencies from the requirements.txt file:
```
python -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```

Perform migrations:
```
python3 manage.py migrate
```

Run the project:
```
python manage.py runserver
```


## Endpoint examples for the unauthorized users:
Use GET method
```r
    To get a list of all publications: "http://.../api/v1/posts/",
    To see the individual post: "http://.../api/v1/posts/{id}/",
    To obtain the list of available groups: "http://.../api/v1/groups/",
    To see the individual group details: "http://.../api/v1/groups/{id}/",
    To obtain the list of all comments for the individual post: "http://.../api/v1/posts/{post_id}/comments/",
    To see the individual comment for the post: "http://.../api/v1/posts/{post_id}/comments/{comment_id}"
```

## User registration:
In order to create the new user you need to make the following request using the POST method:
```r
{
"username":"YourUsername",
"password":"YourPassword"
}
```

```
POST  "http://.../api/v1/users/"
```

Access for authorized users is implemented via the JWT token, which can be obtained by making a POST request:
```r
{
"username":"YourUsername",
"password":"YourPassword"
}
```

```
POST /api/v1/jwt/create/
```


### Authorised users can make GET, POST, PUT, PATCH and DELETE requests. However, YaTube only allows the authors of the posts/comments to modify or delete the original publications.
