# listmonk on Dokku

Originally licensed under the MIT license, forked from https://github.com/knadh/listmonk-heroku-deploy

Create app and database. Link them and configure the app.

```
sudo dokku plugin:install https://github.com/dokku/dokku-postgres.git postgres
dokku apps:create listmonk
dokku postgres:create listmonk-db
dokku postgres:link listmonk-db listmonk
dokku config:set listmonk \
	ROOT_URL=https://listmonk.dokku.me \
	LISTMONK_APP__ADMIN_USERNAME=admin \
	LISTMONK_APP__ADMIN_PASSWORD=password
```

Then push from this repo.
