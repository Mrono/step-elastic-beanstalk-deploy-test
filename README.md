#Amazon EB deployment for Wercker.com


[![wercker status](https://app.wercker.com/status/ff5cec33194ea3c318288128f970c134/m "wercker status")](https://app.wercker.com/project/bykey/ff5cec33194ea3c318288128f970c134)

> Please note: This requires you to have an already existing Elastic Beanstalk application and environment in place, it will not run a startup procedure.

You can set the path to a config and or credential file OR have EB Deploy generate one or the other for you

* `credential_file` (required) Path to EB credential file generated by EB Cli, relative to the root of your repo
-----OR-----
* `key` (required) Credentials key provided by amazon.
* `secret` (required) Credentials key secret provided by amazon

* `config_file` (required) Path to EB config file generated by EB Cli, relative to the root of your repo
-----OR-----
* `app_name` (required) Name of the application.
* `env_name` (required) Name of the application environment you wish to deploy to.
* `region` (optional) Region that your elastic beanstalk instance lives in, defaults to us-west-2.


```yml
deploy:
    steps:
        - mrono/elastic-beanstalk-deploy:
            key: $AMAZON_KEY
            secret: $AMAZON_SECRET_KEY
            app_name: My Application
            env_name: production
            region: us-west-2
```

```yml
deploy:
    steps:
        - mrono/elastic-beanstalk-deploy:
            config_file: 'EBConfigFile.txt'
            credential_file: 'EBKeySecret.txt'
```

