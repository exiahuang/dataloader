# exiahuang/dataloader

## Features

[exiahuang/dataloader](https://github.com/exiahuang/dataloader) Features

-   Need ant and java
-   Support Windows/WSL/Linux/Mac.
-   Dataloader version: 40.0.0~47.0.0
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
ant encrypt_before_v42 -Dpassword=your_password -Dapiversion=47.0.0

```

> Copy the generated encrypted password and set sfdc.password in config.properties.

3. start to export

```shell
# usage
ant start_export -Dsobject_name=Sobject_name -Dsoql="Soql"

#example
ant start_export -Dsobject_name=User -Dsoql="select id,name from user limit 100"
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

### check java version

```
$ java -version

openjdk version "11.0.6" 2020-01-14 LTS
OpenJDK Runtime Environment Zulu11.37+17-CA (build 11.0.6+10-LTS)
OpenJDK 64-Bit Server VM Zulu11.37+17-CA (build 11.0.6+10-LTS, mixed mode)
```

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
