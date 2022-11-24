# exiahuang/dataloader

## Features

[exiahuang/dataloader](https://github.com/exiahuang/dataloader) Features

-   Need ant and java
-   Support Windows/WSL/Linux/Mac.
-   Dataloader version:
  - 40.0.0~47.0.0
  - 54.0.0
  - 55.0.1
  - 56.0.5
-   Support Export/ExportAll/Insert/Update/Upsert/Delete
-   Not need to install dataloader, auto download.
-   Integrated with [exiahuang/xysfdx](https://github.com/exiahuang/xysfdx) for `vscode`

## cli usage

-   clone repository
-   config `config.properties`
-   run

1. clone

```shell
git clone https://github.com/exiahuang/dataloader.git

```

2. config `config.properties`

for 43.0.0~47.0.0

```shell
ant encrypt -Dpassword=your_password -Dapiversion=47.0.0

```

for 40.0.0~42.0.0

```shell
ant encrypt_before_v42 -Dpassword=your_password -Dapiversion=42.0.0

```

> Copy the generated encrypted password and set sfdc.password in config.properties.

3. start to export

```shell
# usage
ant start_export -Dsobject_name=Sobject_name -Dsoql="Soql"

#example
ant start_export -Dsobject_name=User -Dsoql="select id,name from user limit 100"
```

### export

```sh
#example
ant start_export -Dsobject_name=User -Dsoql="select id,name from user limit 100" -Dapiversion=47.0.0
```

### exportAll

```sh
ant export_all -Dsobject_name=User -Dsoql="select id,name from user limit 100" -Dapiversion=47.0.0
```

### insert

```sh
ant insert -Dsobject_name=you_test_object__c -Dsdl="./insert/insert.sdl" -Dcsv="./insert/insert.csv" -Dapiversion=47.0.0
```

> TIPS: How to create sdl file ? I always use [SalesforceXyTools For Chrome](https://chrome.google.com/webstore/detail/salesforce-xytools/ehklfkbacogbanjgekccnbfdgjechlmf) to create it.

### update

```sh
ant update -Dsobject_name=you_test_object__c -Dsdl="./update/update.sdl" -Dcsv="./update/update.csv" -Dapiversion=47.0.0
```

### upsert

```sh
ant upsert -Dsobject_name=you_test_object__c -Dsdl="./upsert/upsert.sdl" -Dcsv="./upsert/upsert.csv" -Dextid="Id or yourExtId" -Dapiversion=47.0.0

```

### delete

```sh
ant delete -Dsobject_name=you_test_object__c -Dsdl="./delete/delete.sdl" -Dcsv="./delete/delete.csv" -Dapiversion=47.0.0
```

### hard delete

TODO: `hard delete not work`

```sh
ant hard_delete -Dsobject_name=you_test_object__c -Dsdl="./delete/delete.sdl" -Dcsv="./delete/delete.csv" -Dapiversion=47.0.0
```

## About Linux Environment or WSL

You can find `Mac` or `Windows` Installing Guide, But no linux.
This is the environment for `Ubuntu 18.04.2 LTS` / `WSL`.

### install Zulu java

[Azul Zulu Linux Repo!](http://repos.azulsystems.com/)

```shell
apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0xB1998361219BD9C9
sudo apt-add-repository 'deb http://repos.azulsystems.com/ubuntu stable main'
sudo apt install -y zulu-11

```

`Zulu` java version:

```
$ java -version

openjdk version "11.0.6" 2020-01-14 LTS
OpenJDK Runtime Environment Zulu11.37+17-CA (build 11.0.6+10-LTS)
OpenJDK 64-Bit Server VM Zulu11.37+17-CA (build 11.0.6+10-LTS, mixed mode)
```

you can use `openjdk-11-jdk`

```
$ java -version

openjdk version "11.0.5" 2019-10-15
OpenJDK Runtime Environment (build 11.0.5+10-post-Ubuntu-0ubuntu1.118.04)
OpenJDK 64-Bit Server VM (build 11.0.5+10-post-Ubuntu-0ubuntu1.118.04, mixed mode, sharing)
```

### check/change java version

check all java version in your os.

```
update-java-alternatives -l
```

change java version

```
sudo update-alternatives --config java
```

### install ant

```
sudo apt -y install ant
```
