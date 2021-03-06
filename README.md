Introduction
=====

The [Bedeveil](https://github.com/Bedevil) group contains Themes and Features for BE::Shell, developed to costumize the user experience as much as we can.
If you want to learn more about BE::Shell you should also check the [project source page](https://sourceforge.net/projects/be-shell/) and is relative wiki.

Structure and Contributions
=====

- Master branch contains all the stable features and completed themes.
- Alpha-features branch is used to start developing new features; the contents of this branch are highly unstable and maybe even dangerous for your system. If you want to propose a new feature please make a [Pull request](http://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project#The-GitHub-Flow) under this branch.
- Beta-features branch is used to test features introduced and developed under Alpha-features branch before merge it into the master one. The contents may still be not completely stable. If you want test some of this features we will be very glad if you report every issue using the [Github dedicated tool](https://github.com/Bedevil/be.shell/issues).
- Other branches contain themes under-development and not ready for a release. They could result not tested for some resolution and might change drastically during time. 

If you want to contribute to this project, in any of the described branch, please use the standard git contribution method - that you can find [here](http://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project) - by creating an appropriate pull request.

Requirements
=====

Install [BE::Shell](http://sourceforge.net/p/be-shell/code/ci/master/tree/) or upgrade to the latest commit.
Themes are made with [QSS](http://qt-project.org/doc/qt-4.8/stylesheet-reference.html) - Qt Style Sheets, while the menu files for the globalmenu applet follow a simple [xml syntax](http://sourceforge.net/p/be-shell/wiki/Menu%20reference/).
Some of the menus, *Recent* and *Places*, are generated by the relative scripts located under the Scripts folder.

**Notes** 

- Due to the absolute positioning in BE::Shell themes may need adjustments within the css or the config file.
- The places script requires xmlstarlet

Installation
======

Clone this repository:

    git clone https://github.com/Bedevil/be.shell.git
    cd be.shell
    
You can either install presets using the provided script or copying the files manually.
To see the themes available in this repo, check our [gallery](https://github.com/Bedevil/be.shell/wiki/Gallery).
   
**By script**

From the cloned source directory, just issue:

    ./be.installer
    
Or, alternatively, you can skip the list of available presets and specify directly the one you want, passing its name after the -p argument - e.g. for be.shell.Vertex :

    ./be.installer -p Vertex
    
*Note* By default the script will ask if you want to backup your current config and theme, this functionality can also be invoked with:

    ./be.installer -b
    
 **Manually**
 
If this is the first time you install BE::Shell, you need to create its configuration and themes folders:

    mkdir -p `kde4-config --localprefix`/share/apps/be.shell/Themes
 
Copy the Theme directory: 

    cp -r Themes `kde4-config --localprefix`/share/apps/be.shell/

Copy the included config file (for example be.shell.Vertex) as be.shell:

    cp be.shell.Vertex `kde4-config --localprefix`/share/config/be.shell
    
Install the provided scripts:

    mkdir -p ~/.local/share/be.shell
    cp -r Scripts ~/.local/share/be.shell && chmod -R 777 ~/.local/share/be.shell/Scripts/*
    
Install the menus:

     cp -r Menu ~/.local/share/be.shell
    
Copy the MainMenu.xml under your be.shell config dir:

    cp MainMenu.xml `kde4-config --localprefix/share/apps/be.shell
   
Finally, (re)load be.shell. If you're using Plasma on KDE SC4, kill its process and start BE::Shell:

    kquitapp plasma-desktop; sleep 2; be.shell
    
While if you're on Plasma5, the command is:

    kquitapp plasmashell; sleep2; be.shell
    
If you're already on BE::Shell, restart it in order to apply the new theme & config:

    be.shell --restart
    
**Notes** 

If you need more help or if you want to check detailed info of how to use our features or modify our work you should check our [wiki](https://github.com/Bedevil/be.shell/wiki).

License
=====

All our works are distributed under the GNU GPLv3 license.  
You can read the terms and condition to the license [here](https://github.com/Bedevil/be.shell/blob/master/LICENSE.md)
