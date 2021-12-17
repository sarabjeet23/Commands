# Commands
This file records the commands to make python 3 working for MacBook Air and getting lxml library working on local python
##1.How to Open cmd shell on MacBook Air
##Answer : Go to Applications ---> Utilities--> Double Click Terminal

##2.How to change default python version on macbook?
##  a. Download HomeBrew. https://brew.sh/. (/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
##  b.Change default python version to puthon 3 in command window using-  alias python=python3
##3. How to upgrade pip? (Getting error while running pip command - pip is not recognized)
##python -m pip install --upgrade pip
##4.Install lxml

###Getting xpaths from xml

>>>root = ET.fromstring(s)
>>> import xml.etree.ElementTree as ET
>>> def parseXML(root,sm):
    sm = sm + "/" + root.tag[root.tag.rfind('}')+1:]
    for child in root:
      parseXML(child,sm)
    if len(list(root)) == 0:
      print(sm)

f = "/Users/sarabjeetkaur/Downloads/quoteXml44.xml"
>>> tree = ET.parse(f)
>>> root = tree.getroot()
>>> parseXML(root,"")
