# api

The dwyl REST &amp; WebSocket API.

![perfection-intro-image](https://cloud.githubusercontent.com/assets/194400/8255483/2fc78e6c-1698-11e5-8c27-d1b9db99f020.png)

## Run the API Locally

You will need a running instance of ElasticSearch for this API to work on your localhost.

Steps:
+ Learn Vagrant: https://github.com/docdis/learn-vagrant
+ Start Vagrant VM with ElasticSearch `vagrant up`
+ Start API server: `npm install && npm start`


## Send Welcome Email

```sh
curl --data "email=dwyl.smith+1234@gmail.com" http://localhost:1337/email
```

### *Expected* Environment Variables˜

The API server will *not* work unless these
environment variables are set.

Run the following command to set up your local machine:
```sh
export ES_INDEX=dwyl
export MANDRILL_APIKEY='AskUsForTheKey!'

```


### Troubleshooting

Get list of records in ES:

```sh
curl -XGET 'localhost:9200/dwyl/_search?search_type=scan&scroll=10m&size=50' -d '
{
    "query" : {
        "match_all" : {}
    }
}'
```
