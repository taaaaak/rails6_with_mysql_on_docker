# rails6_with_mysql_on_docker 
 
## 同じ階層にRailsという名前でアプリケーションを作成する 
 
### config/database.yml 
 
```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password: root_pass
  host: db

development:
  <<: *default
  database: device_management_development

test:
  <<: *default
  database: device_management_test

production:
  <<: *default
  database: device_management_production
  username: deviceManagementApp
  password: <%= ENV['DEVICE_MANAGEMENT_APP_DATABASE_PASSWORD'] %>
```
