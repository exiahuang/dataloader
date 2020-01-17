# exiahuang/dataloader

## Features

[exiahuang/dataloader](https://github.com/exiahuang/dataloader) Features

-   Need ant and java
-   Support Windows/WSL/Linux/Mac.
-   Dataloader version: 40.0.0, 41.0.0, 42.0.0
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

```shell
ant encrypt -Dpassword=your_password -Dapiversion=43.0.0

```

3. start to export

```shell
# usage
ant start_export -Dsobject_name=Sobject_name -Dsoql="Soql"

#example
ant start_export -Dsobject_name=User -Dsoql="select id,name from user limit 100"
```
