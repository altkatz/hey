- Compile

```
make
```

- Prepare auth token file,each line is a auth token string of one user:

```
auth_token_of_user1
auth_token_of_user2
auth_token_of_user3
.....
```

- Prepare user_reqs.json,each item in the json array is a request made by a single user:

```
[
    {
    "URL": "url1",
    "Method": "GET",
    "Body": "body1",
    "Headers": {"Content-Type":"application/json"}

    },
    {
    "URL": "url2",
    "Method": "POST",
    "Body": "body2",
    "Headers": {"Content-Type":"application/json"}
    }
]
```

- Run:
  run 18000 requests with 9000 concurrent users(each user 2 requests):

```

./hey -n 18000 -c 9000 -auth-tokens-file ./alltokens -user-req-file ./user_reqs.json


```
