#MARA Framework wiki

##Introduction
**MARA** is a **M**obile **A**pplication **R**everse engineering and **A**nalysis Framework. It is a toolkit that puts together commonly used mobile application reverse engineering tools, in order to make the task or reverse engineering and analysis easier and friendly to mobile application developers and security professionals. 


##Features supported
* Reverse engineer apk files to smali, java jar files, java source code and dalvik bytecode  (jadx format)
* Reverse engineer dex, jar and class files into java source code and dalvik bytecode (jadx format)
* Statically Analyze java source code and dalvik bytecode
* Scan for apk vulnerabilities via [androbugs](https://github.com/AndroBugs/AndroBugs_Framework)
* Scan ssl domains found in the app via the standalone SSL scanner that makes use of [pyssltest](https://github.com/moheshmohan/pyssltest) and [testssl](https://github.com/drwetter/testssl.sh) 


##Installing MARA on Linux/Nethunter
The following are the requirements for running MARA. The domain SSL scanning component requires an active internet connection. MARA works with Open JDK or Oracle JDK. We recommend version 7 and above when using either of them. 

#### Java JDK
    sudo apt-get -y install openjdk-7-jdk 

#### Tree
    sudo apt-get -y install tree

#### Install 32bit libs
    sudo dpkg --add-architecture i386
    sudo apt-get update
    sudo apt-get -y install libgtk2.0-0:i386 libxxf86vm1:i386 libsm6:i386 lib32stdc++6

#### Figlet
    sudo apt-get -y install figlet
    sudo cp tools/figlet/doom.flf /usr/share/figlet

#### Unirest
    sudo pip install unirest

#### AHA - Ansi HTML Adapter
    sudo apt-get -y install aha

#### Python3
    apt-get install -y python3
    
#### Androwarn dependencies
    sudo apt-get -y install python python-jinja2 git

#### Smali graph generation dependency
    pip install pydot

#### Smalisca
    sudo pip install smalisca

MARA ships with a script that assists in downloading and installing the dependencies above. Simply run the **requirements.sh** script with sudo privilege and it will install them. 

After meeting all the requirements. If you run **./mara.sh** --help you should see the MARA help menu as shown below.

![](https://cloud.githubusercontent.com/assets/7021125/16488085/5a5c17e8-3ed7-11e6-85c5-d56035b91f94.png)

All the analysis data and file conversions are stored in the data folder i.e. **/MARA_Framework/data/file_name**. MARA also keeps a compressed copy of the analysis in the data folder i.e **/MARA_Framework/data/file_name.zip**.

###SSL Scanner
MARA ships with a SSL scanner script that makes use of pyssltest and testssl. The stand alone SSL scanner can be run using the command **./ssl_scanner.sh** and follow the instructions displayed. The findings from the scan are dumped in the domain scans folder i.e. **/MARA_Framework/data/domain_scans/<domain_name>** 


While analyzing APK files, MARA provides the option of scanning domains found in the apk using the above mentioned tools. This scan runs in the background and can be skipped. In the event the scan is performed, the user is required to tail the two log files i.e **pyssltest.log** and **testssl.log** in **/MARA_Framework/data/apk_name/analysis/static/ssl_scan/log/**

##To do list
MARA is still in the very early stages of development. We intend to work on the following features: 
* Integrate dynamic mobile app analysis
* Rewrite the tool in python
* Integrate iOS, Blackberry and Windows phone application analysis
* Develop web panel to display data
* Include additional disassembly and analysis tools 

##Credits
These are the people who have assisted in ensuring the success of this tool's capabilities. 
* Chrispus - [@iamckn](https://twitter.com/iamckn) -[https://www.ckn.io](https://www.ckn.io) (co-developer)
* Ajin - [@ajinabraham](https://twitter.com/ajinabraham) - [Mobile Security Framework - MobSF](https://github.com/ajinabraham/Mobile-Security-Framework-MobSF)
* Munir - [@muntopia](https://twitter.com/muntopia) - http://munir.skilledsoft.com/
* Gabby - [@_V1VI](https://twitter.com/_V1VI)- https://thevivi.net
* AfricaHackOn Team - @AfricaHackon - http://africahackon.com

##Licensing
MARA framework is intended to be free to use by anyone. It shall be available on github for contribution and collaboration. The tool is currently licensed under GNU GPL v3 license to allow interested users to copy, distribute and adapt it, provided that the work is attributed.




