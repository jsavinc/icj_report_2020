# icj_report_2020
ICJ report 2020 script, to be used as a server that will automatically update from github!

This is hosted on a shiny server as a .Rmd file for a static webpage that summarises ICJ data.

# Instructions for installing on shiny server

Stop shiny server

```
sudo service shiny-service stop
```

Backup old first

```
cd /srv/shiny-server/
sudo mv icj_report_2020 mv icj_report_2020_backup
```

Git clone, enter username & password when prompted

```
cd /srv/shiny-server/
sudo git clone https://github.com/jsavn/icj_report_2020
```

Change ownership to shiny

```
sudo chown -R shiny:shiny icj_report_2020
```

Start shiny server again

```
sudo service shiny-server start
```

Check if it works, and delete backup if it does!

```
sudo rm -R icj_report_2020_backup
```

Don't forget to upload the data files also!

## Instructions in single block, copy-paste to terminal!

```
sudo service shiny-service stop
cd /srv/shiny-server/
sudo mv icj_report_2020 mv icj_report_2020_backup
sudo git clone https://github.com/jsavn/icj_report_2020
sudo chown -R shiny:shiny icj_report_2020
sudo service shiny-server start
```

If it works, delete backup:

```
sudo rm -R icj_report_2020_backup
```

# Instructions for updating on shiny server

```
sudo service shiny-service stop
cd /srv/shiny-server/icj_report_2020
sudo git pull
sudo chown -R shiny:shiny /srv/shiny-server/icj_report_2020
sudo service shiny-server start
```