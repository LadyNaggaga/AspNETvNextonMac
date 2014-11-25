AspNETvNextonMac
================
To get started you will need the following software ,frameworks and package managers 
* Download [SublimeText3](http://www.sublimetext.com/3)
* Install [Yeoman](http://yeoman.io)
* Install  [Mono](http://www.mono-project.com)
* Install [HomeBrew](http://brew.sh) 

Before you get started installing the frameworks and PKGs you need to get ASP.NET vNext running, make sure that you have the latest version for Node and npm. Copy and paste the code below into terminal.

` node --version && npm --version`

Check to see if you have git installed as well 

`git --version`

## Install Yeoman 
`sudo npm install —global yo`

### Install the Asp.Net generator 
`npm install -g generator-aspnet`

VOILÀ! Asp.Net vNext is ready for use. For this examples I selected the  MVC Application. Once you have entered an appropriate name, the generator will take care of the rest.

![](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Entername.png)

Navigate to the folder  notice the  model, view and control are all there.  Similar to what you find if you used the MVC model template in Visual Studio.
![](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/MVCModeliscreated.png)

**Before you can run your ASP.NET vNext** in sublime there are still a couple of dependencies  that need to be installed.  A lot of tutorials I have read miss the  dependencies below but I encountered a lot of errors  when trying to configure the K commands.

### Install Mono
In order to run  an ASP.NET vNext on a Mac and Linux environment you need Mono. Copy and paste the code below into your terminal.

`git clone https://github.com/mono/mono.git`

### Install Homebrew
Homebrew enables you install all the stuff you can’t directly install in terminal out of the box.  Copy + Paste the code below

` ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingHomebrew.png"><img width="567" height="298" class="alignnone size-full wp-image-12191" alt="InstallingHomebrew" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingHomebrew.png"></a>`

**Install all the extra mono & Asp.Net vNext dependencies**

`brew install autoconf`

`brew install automake`

`brew install libtool`

`brew tap aspnet/k`

`brew install kvm`

![Homebrew  kvm install](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingKVM.png)

It is important to note that in the current version of **Asp.Net vNext Kestrel doesn’t come with it out of the box**. So  in this case since I am  using the “Kestrel”: “1.0.0-alpha4. To find out which version of  Kestrel you are running, open your project.json file in your Asp.Net project.  To install Kestrel copy + paste code below.

`kvm install 1.0.0-alpha4`

## Running your project in Sublime

Since this is possibly the first ASP.NET project you will need to install the Kulture  as instructed in here using the package control plugin. If you have some issues with these steps, you can install it manually using the following steps:

* Open your project in sublime
* Click view
* Click show console and copy and paste the python code below 

`import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)`

To check to make sure that everything is working, try adding a new namespace into your HomeControllers.cs file.  If everything is in place you will notice the intellisense is in working.
![Kulture successfully installed](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/intellsense.png)

**Steps to running your project**

* In sublime enter Cmd + Shift + p
* Type K and  select run K Command
* Select kpm build
* Select k kestrel – If everything has installed correctly the server  should start

![](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Running-the-localhost-server.png)

* Navigate  http://localhost:5004/

![](http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/ASPNET.png)


