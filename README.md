forked from: https://github.com/taypo/discourse-turkish-i18n-kpn

discourse-hungarian-i18n
======================

You need to modify your app.yml file to get it working. Find the section where after code hooks are listed:

```ruby
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - mkdir -p plugins
          - git clone https://github.com/discourse/docker_manager.git
```

and add the required lines, so the final version will be:

```ruby
hooks:
  after_code:
    - exec:
        cd: $home/plugins
        cmd:
          - mkdir -p plugins
          - git clone https://github.com/discourse/docker_manager.git
    - exec:
        cd: /tmp
        cmd:
          - git clone https://github.com/elekdavid/discourse-hungarian-i18n-kpn.git
          - cp -rT discourse-hungarian-i18n/ /var/www/discourse/
          - rm -rf discourse-hungarian-i18n
```
