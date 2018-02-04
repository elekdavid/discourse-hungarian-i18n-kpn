forked from: https://github.com/taypo/discourse-turkish-i18n-kpn

discourse-hungarian-i18n
======================

Add the required lines, so the final version will be:

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
          - git clone -b hk-forum https://github.com/elekdavid/discourse-hungarian-i18n-kpn.git
          - cp -rT discourse-hungarian-i18n-kpn/ /var/www/discourse/
          - cp -f discourse-hungarian-i18n-kpn/reload_i18n.sh /root/reload_i18n.sh
          - chmod +x /root/reload_i18n.sh
          - rm -rf discourse-hungarian-i18n-kpn
```
