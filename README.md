discourse-facebook-auto-publish
===

## Notes

A specially developed daemon for publish discourse articles to the facebook group.


## Usage

- Install dependency

```console
$ npm insatll
```

- Start daemon
	- It has a pre-process to get the Facebook token.

```console
$ npm start
```

- Stop daemon

```console
$ npm stop
```


## Configuration

- You need the Facebook app.
	- [https://developers.facebook.com/apps/](https://developers.facebook.com/apps/)
	- This app will only be used by you, so you can use it while under `development` status.

- need to copy `.env_sample` to `.env` and change it.

```javascript
DISCOURSE_URL=https://jsdev.kr
FACEBOOK_APP_ID=
FACEBOOK_SECRET=
FACEBOOK_GROUP_ID=
POLLING_INTERVAL_SEC=60
POSTED_AFTER_MIN=5
```

- `DISCOURSE_URL` should not end with `/`.
- To find `FACEBOOK_GROUP_ID`, run `/me` to get `user-id` and run `/{user-id}/groups` in the graph API explorer.
	- [https://developers.facebook.com/tools/explorer](https://developers.facebook.com/tools/explorer)


## Running on Docker or Container Service

- If you want running on `Docker` or `Heroku`, need to provide `process.env.FACEBOOK_ACCESS_TOKEN`
	- To get `FACEBOOK_ACCESS_TOKEN`, open this url and get accessToken : https://developers.facebook.com/tools/explorer/{FACEBOOK_APP_ID}'
	- Type  : `User Access Token`, Scope : `publish_to_groups`

```console
$ npm run start-docker
```


## To do

- Post to other facebook groups by category.
- Posting the same post to multiple groups.


## Caution

- Facebook can block or audit your account.


## License

MIT License
