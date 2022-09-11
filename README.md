# Создание
- `vagrant init`           
- `vagrant init <boxpath>` 
# Старт
- `vagrant up`                
- `vagrant resume`              
- `vagrant provision`           -- форсировать пересоздание машины
- `vagrant provision --debug`
- `vagrant up --provision | tee provision.log` 
- `vagrant reload`              -- перегрузить(будет перечитан Vagrantfile с новыми настройками)
- `vagrant reload --provision`  

# Вход в бокс
- `vagrant ssh`           
- `vagrant ssh <boxname>` -- в конкретный бокс

# Остоновка
- `vagrant halt`        -- остановить
- `vagrant suspend`     -- пауза (запомнит состояние)

# Удаление
- `vagrant destroy`     -- остановить и удалить
- `vagrant destroy -f`   -- force

# Общее
- `vagrant -h`                    -- помощь по командам
- `vagrant -v`
- `vagrant status`
- `vagrant global-status`        -- статус всех машин
- `vagrant global-status --prune`  -- если показывает боксы который реально нет
     
- `vagrant box list`              
- `vagrant box add <name> <url>`  -- скачать box на локальный пк
- `vagrant box outdated`          -- проверить обновления для боксов
- `vagrant box remove <name>`   -- удалить бокс с локальной машины
- `vagrant package`               -- запаковать запущенные боксы чтоб можно было переиспользовать

# Сохранение состояния
-`vagrant snapshot save [options] [vm-name] <name>`
