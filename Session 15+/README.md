# Business Intelligence and Data Warehouse Course

This repository contains additional information. 

## FAQ

### Is it possible to use homebrew to install the software?

Yes! [Homebrew](https://brew.sh) (for Mac) can help to install the majority of tools (except Tableau) that we need using the terminal. If you are interested open the terminal and follow these steps:

  - Install brew (for Mac)
  
``` 
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

  - Update and upgrade brew (for mac). 

``` 
brew update && brew upgrade
``` 

  - Install cask using brew (for mac). More information about [cask](http://caskroom.io).

``` 
brew tap caskroom/cask
``` 

  - Install JDK 8 using cask (for mac). Use uninstall to delete.

``` 
brew cask install java8
``` 

  - Install MySQL using brew (for mac). Use uninstall to delete.

``` 
brew install mysql
``` 

  - Install MySQL Workbench using brew and cask (for mac). Use uninstall to delete.

``` 
brew cask search mysql
brew cask install mysqlworkbench
``` 

  - Install kettle (pdi) using brew (for mac). Use uninstall to delete.

``` 
brew install kettle
``` 

or 

``` 
brew cask install data-integration
``` 

  - Uninstall brew (for Mac)

``` 
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
``` 

### Is it possible to use chocolatey to install the software?

Yes! [Chocolatey](https://chocolatey.org) (for Windows) can help to install the majority of tools (except Tableau and PDI) that we need using the terminal. If you are interested open the terminal and follow these steps:

  - Install JDK 8.

``` 
choco install jdk8
``` 

  - Install MySQL (only version 5.x)

``` 
choco install mysql
``` 

  - Install MySQL Workbench.

``` 
choco install mysql.workbench
``` 