AspNETvNextonMac
================
<strong>This page  has been updated to reflect the changes made from vNext Alpha to Beta</strong>

<!--more-->

To get started you will need the following software ,frameworks and package managers :
<ul>
	<li>Download <a href="http://www.sublimetext.com/3">Sublime Text 3 </a></li>
	<li>Install <a href="http://yeoman.io">Yeoman </a></li>
	<li>Install  <a href="http://www.mono-project.com">Mono</a></li>
	<li>Install <a href="http://brew.sh">Homebrew </a></li>
</ul>
Before you get started installing the frameworks and PKGs you need to get ASP.NET vNext running, make sure that you have the latest version for <a href="http://nodejs.org/download/">Node </a>and<a href="https://www.npmjs.org"> npm.</a> Copy and paste the code below into terminal.
<pre class="brush:shell"> node --version &amp;&amp; npm --version</pre>
Check to see if you have git installed as well .
<pre class="brush:shell">git --version</pre>
<h3> Install Yeoman</h3>
Yeoman is an open source sleek scaffolding tool that consists frameworks  that make it quick and easy to build web applications.  The neat thing about Yeoman is it combines several functions into one place, such as template generators which we are going to use to get the ASP.NET vNext up and running .
<pre class="brush:shell">sudo npm install —global yo</pre>
Now that  Yeoman is installed the next step is to get our ASP.NET framework installed using the yeoman generator.
<pre class="brush:shell">npm install -g generator-aspnet</pre>
For this examples I selected the MVC Application. Once you have entered an appropriate name, the generator will take care of the rest.

<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Entername.png"><img class="alignnone size-full wp-image-12311" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Entername.png" alt="Entername" width="486" height="339" /></a>

Now that  MVC application all ready , navigate to the folder  notice the  model, view and control are all there.  Similar to what you find if you used the MVC model template in Visual Studio.

<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/MVCModeliscreated.png"><img class="alignnone  wp-image-12221" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/MVCModeliscreated.png" alt="MVCModeliscreated" width="608" height="356" /></a>
Before you can run your ASP.NET vNext in sublime there are still a couple of dependencies  that need to be installed.  A lot of tutorials I have read miss the  dependencies below but I encountered a lot of errors  when trying to configure the K commands.
<h3>Install Mono</h3>
In order to run  an ASP.NET vNext on a Mac and Linux environment you need <a href="http://www.mono-project.com/docs/">Mono</a>. Copy and paste the code below into your terminal.
<pre class="brush:shell">git clone https://github.com/mono/mono.git</pre>
<h3>Install Homebrew</h3>
<a href="http://brew.sh">Homebrew</a> is an open source software package management tool ; it enables you install all the stuff you can't directly install in terminal out of the box. To install Homebrew you will need to copy and paste the Ruby code below.
<pre class="brush:shell" style="width: 692px; height: 20px;">ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
</pre>
<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingHomebrew.png"><img class="alignnone size-full wp-image-12191" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingHomebrew.png" alt="InstallingHomebrew" width="567" height="298" /></a>

Now, that Homebrew installed make sure to install all the extra mono dependencies.
<pre class="brush:shell">brew install autoconf
brew install automake
brew install libtool</pre>
Install the ASP.NET vNext  Tools

If you had already tapped the repo for previous releases(Alpha) you will be  to run the untap command  to delete the old commands and tap again to get the updated brew scripts.

Untap Command
<pre class="brush:shell" style="width: 692px; height: 3px;">brew untap aspnet/k

</pre>
Tap Command &amp; Install kvm
<pre class="brush:shell" style="width: 692px; height: 3px;">brew tap aspnet/k
brew install kvm
</pre>
<h3><a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingKVM.png"><img class="alignnone size-full wp-image-12201" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/InstallingKVM.png" alt="InstallingKVM" width="556" height="161" /></a></h3>
It is important to note that in the current version of Asp.Net vNext Kestrel doesn’t come with it out of the box. So  in this case since I am  using the <strong>"Kestrel": "1.0.0-beta1"  (from "Kestrel": "1.0.0-beta1" ).</strong> To find out which version of  Kestrel you are running, open your project.json file in your Asp.Net project.  To install Kestrel copy and paste the code below.
<pre class="brush:shell">kvm install 1.0.0-beta1
</pre>
<h3>Setting up your project in Sublime</h3>
Since this is possibly the first ASP.NET project you will need to install the<a href="https://sublime.wbond.net/packages/Kulture"> Kulture </a> as instructed in here using the <a href="https://sublime.wbond.net/packages/Kulture">package control plugin</a>. If you have some issues with these steps, you can install it manually using the following steps:
<ul>
	<li>Open your project in sublime</li>
	<li>Click view</li>
	<li>Click show console and copy and paste the python code below
<pre class="brush:py" style="width: 663px; height: 23px;">import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)</pre>
</li>
</ul>
With Kulture installed you will be able to run you ASP.NET project successfully.  To check to make sure that everything is working, try adding a new namespace into your HomeControllers.cs file.  If everything is in place you will notice the intellisense is in working.

<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/intellsense.png"><img class="alignnone wp-image-12421 size-large" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/intellsense-1024x640.png" alt="intellsense" width="676" height="422" /></a>

<strong>Steps to running your project</strong>
<ul>
	<li>In sublime enter Cmd + Shift + p</li>
	<li>Type K and  select run K Command</li>
	<li>Select kpm build</li>
	<li>Select k kestrel - If everything has installed correctly the server  should start
<a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Running-the-localhost-server.png"><img class="alignnone size-full wp-image-12271" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/Running-the-localhost-server.png" alt="Running the localhost server" width="591" height="380" /></a></li>
	<li>Navigate  <a href="http://localhost:5004/">http://localhost:5004/
</a><a href="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/ASPNET.png"><img class="alignnone wp-image-12473 size-large" src="http://marianaggaga.azurewebsites.net/wp-content/uploads/2014/11/ASPNET-1024x449.png" alt="ASPNET" width="676" height="296" /></a></li>
</ul>
And there you have it !  Asp.Net vNext on a Mac :) .
