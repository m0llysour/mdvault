`back`          Move back from the current context
`banner`        Display an awesome metasploit banner
`cd`            Change the current working directory
`color`         Toggle color

`connect`       Communicate with a host
*miniature Netcat clone built into the msfconsole that supports SSL, proxies, pivoting, and file transfers. connect to a remote host from within msfconsole the same as you would with Netcat or Telnet. additional options by issuing the **-h** parameter.*

`edit`          Edit the current module with $VISUAL or $EDITOR
`exit`          Exit the console
`get`           Gets the value of a context-specific variable
`getg`          Gets the value of a global variable
`go_pro`        Launch Metasploit web GUI

`grep`          Grep the output of another command
`help`          Help menu
`info`          Displays information about one or more module

`irb`           Drop into irb scripting mode
*drop you into a live Ruby interpreter shell where you can issue commands and create Metasploit scripts on the fly. This feature is also very useful for understanding the internals of the Framework.*

`jobs`          Displays and manages jobs
*Jobs are modules that are running in the background. The **jobs** command provides the ability to list and terminate these jobs.*

`kill`          Kill a job
`load`          Load a framework plugin
`loadpath`      Searches for and loads modules from a path
`makerc`        Save commands entered since start to a file
`popm`          Pops the latest module off the stack and makes it active

`previous`      Sets the previously loaded module as the current module
`pushm`         Pushes the active or list of modules onto the module stack
`quit`          Exit the console
`reload_all`    Reloads all modules from all defined module paths
`rename_job`    Rename a job

`resource`      Run the commands stored in a file
*Some attacks, such as Karmetasploit, use resource files to run a set of commands in a **karma.rc** file to create an attack.
Batch files can greatly speed up testing and development times as well as allow the user to automate many tasks. Besides loading a batch file from within msfconsole, they can also be passed at startup using the **-r** flag.*

`route`         Route traffic through a session
*allows you to route sockets through a session or ‘comm’, providing basic pivoting capabilities. To add a route, you pass the target subnet and network mask followed by the session (comm) number.*

`save`          Saves the active datastores
*After setting your different variables, you can run the **save** command to save your current environment and settings. With your settings saved, they will be automatically loaded on startup, which saves you from having to set everything again.*

`search`        Searches module names and descriptions
Keywords:
  *app*       :  Modules that are client or server attacks
  *author*    :  Modules written by this author
  *bid*       :  Modules with a matching Bugtraq ID
  *cve*       :  Modules with a matching CVE ID
  *edb*       :  Modules with a matching Exploit-DB ID
  *name*      :  Modules with a matching descriptive name
  *platform*  :  Modules affecting this platform
  *ref*       :  Modules with a matching ref
  *type*      :  Modules of a specific type (exploit, auxiliary, or post)
Examples:
  search cve:2009 type:exploit app:client

`sessions`      Dump session listings and display information about sessions

`set`           Sets a context-specific variable to a value
*allows you to set an encoder to use at run-time. This is particularly useful in exploit development when you aren’t quite certain as to which payload encoding methods will work with a given exploit.
show encoders*

`setg`          Sets a global variable to a value

`show`          Displays modules of a given type, or all modules
*the ones you will use most frequently are **show auxiliary**, **show exploits**, **show payloads**, **show encoders**, and **show nops**.*
*see more advanced options by running **show advanced**.*

`sleep`         Do nothing for the specified number of seconds
`spool`         Write console output into a file as well the screen
`threads`       View and manipulate background threads
`unload`        Unload a framework plugin
`unset`         Unsets one or more context-specific variables
`unsetg`        Unsets one or more global variables
`use`           Selects a module by name
`version`       Show the framework and console library version numbers

`use multi/handler`
`use exploit/multi/handler`
create a listener for reverse shells