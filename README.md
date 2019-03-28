## About

| Item         | Info                   |
| ------------ | ---------------------- |
| Project      | discourse-oauth2-enl-v |
| Version      | 0.1                    |
| Maintainer   | audazel                |

## Installation

Edit `app.yml`:

```
cd /var/discourse
vi containers/app.yml
```

Insert or edit below config snippet in `app.yml`. You will need to add this project URL:

```
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - git clone https://github.com/discourse/docker_manager.git
          - git clone https://github.com/antonraharja/discourse-oauth2-enl-v.git

```

Rebuild and re-run:

```
cd /var/discourse
./launcher rebuild app
```

Visit this page for more information on howto install plugins in Discourse:
- https://meta.discourse.org/t/install-plugins-in-discourse/19157

# Settings

Get client ID and client secret from Project V

The callback URL is `https://<your discourse>/auth/oauth2_enl_v/callback`

Set client ID and client secret from Discourse in `Admin -> Settings -> Login`
