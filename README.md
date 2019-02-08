# mecab-api

Docker compose file for MeCab API with mecab-ipadic-neologd.

> Note: Only works on Intel/AMD(x86_64) architecture. Can't figure out to make it work on ARM such as RaspberryPi, yet.

<details><summary>How to check your architecture.</summary><div>

```
$ uname -a
Darwin KeinosNoMacBookPro.local 17.7.0 Darwin Kernel Version 17.7.0: Thu Dec 20 21:47:19 PST 2018; root:xnu-4570.71.22~1/RELEASE_X86_64 x86_64
```

</div></details>

## Download

```bash
curl -O https://keinos.github.io/mecab-api/docker-compose.yml
```

## Run

```shellsession
$ ls
docker-compose.yml
$ 
$ docker-compose up -d
Creating network "mecab-api_default" with the default driver
Creating mecab-api_api_1 ... done
Creating mecab-api_front_1 ... done
```

## Browser access

Default port is `5001`.

>` http://localhost:5001/`

## API access

Default port is `5000`.

```
$ curl -X POST http://localhost:5000/mecab/v1/parse-ipadic \
       -H "Content-type: application/json" \
       -d '{"sentence": "すもももももももものうち"}'  | jq .
```
