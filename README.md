# WMIC
Windows Management Instrumentation Command (WMIC)
WMIC.exe

Retrieve a huge range of information about local or remote computers. Make configuration changes to multiple remote machines.

The ALIAS defines the component of your system that you want WMIC to interact with.
The WHERE clause can be added to filter down to a specific item, e.g. a specific printer instead of all printers.

Syntax
    WMIC [global_switch(s)] Alias [options] [format]

    WMIC [global_switch(s)] Command

    WMIC [global_switch:value] [global_switch:value] Command

    WMIC CONTEXT

Interactive mode:
    WMIC

Global_Switches:
     /NODE         Servers to operate against:
                      @filename
                      machine_id <,machine id list>
     /APPEND       Mode for output redirection:  STDOUT, CLIPBOARD, <filename>
     /AUTHLEVEL    Client authentication level:  Default,None,Connect,Call,Pkt,Pktintegrity,Pktprivacy
     /AGGREGATE    Aggregate mode: (column titles)    ON, OFF
     /AUTHORITY    The <authority type> for the connection.
     /FAILFAST     FailFast mode:(timeout for connection to remote machine)   ON, OFF
     /IMPLEVEL     Client impersonation level:    Anonymous,Identify,Impersonate,Delegate
     /INTERACTIVE  Interactive mode:(prompt before WMI schema changes)    ON, OFF
     /LOCALE       Language id.    (ms_409=US)
     /NAMESPACE    Path for the namespace the alias operates against.
     /OUTPUT       Mode for output redirection:    STDOUT, CLIPBOARD, <filename>
     /PASSWORD     Password for session login.   <password>
     /PRIVILEGES   Enable or disable all privileges:  ENABLE, DISABLE
     /RECORD       Log all input commands and output: <FilePath>
     /ROLE         Path for the role containing the alias definitions.
     /TRACE        Output debugging information to stderr.  ON, OFF
     /USER         User for this session:      <domain>\<userid>

     CONTEXT       Display the current state of all global switches.
     CLASS         Escape to full WMI schema.
     PATH          Escape to full WMI object paths.
     QUIT/EXIT     Exit WMIC


Aliases:

       ALIAS               - Access local system aliases [CALL]
       BASEBOARD           - Base board management (motherboard or system board) 
       BIOS                - BIOS management (Basic input/output services) 
       BOOTCONFIG          - Boot configuration
       CDROM               - CD-ROM
       COMPUTERSYSTEM      - Computer system [CALL/SET]
       CPU                 - CPU
       CSPRODUCT           - Computer system product information from SMBIOS. 
       DATAFILE            - DataFiles [CALL]
       DCOMAPP             - DCOM Applications.
       DESKTOP             - User's Desktop
       DESKTOPMONITOR      - Desktop Monitor
       DEVICEMEMORYADDRESS - Device memory addresses
       DISKDRIVE           - Physical disk drive
       DISKQUOTA           - Disk space usage for NTFS volumes.[SET]
       DMACHANNEL          - Direct memory access (DMA) channel
       ENVIRONMENT         - System environment settings [SET]
       FSDIR               - Filesystem directory entry [CALL]
       GROUP               - Group account [CALL]
       IDECONTROLLER       - IDE Controller
       IRQ                 - Interrupt request line
       JOB                 - Jobs scheduled using the schedule service.[CALL]
       LOADORDER           - System services that define execution dependencies. 
       LOGICALDISK         - Local storage devices [CALL/SET]
       LOGON               - LOGON Sessions.
       MEMCACHE            - Cache memory
       MEMORYCHIP          - Memory chip information.
       MEMLOGICAL          - System memory, layout and availability
       MEMPHYSICAL         - Physical memory management
       NETCLIENT           - Network Client management.
       NETLOGIN            - Network login information for a particular user. 
       NETPROTOCOL         - Protocols (and their network characteristics).
       NETUSE              - Active network connection.
       NIC                 - Network Interface Controller (NIC)
       NICCONFIG           - Network adapter. [CALL] 
       NTDOMAIN            - NT Domain. [SET]  
       NTEVENT             - NT Event Log.  
       NTEVENTLOG          - NT eventlog file [CALL/SET]
       ONBOARDDEVICE       - Common adapter devices built into the motherboard.
       OS                  - Operating System/s [CALL/SET]
       PAGEFILE            - Virtual memory file swapping
       PAGEFILESET         - Page file settings [SET]
       PARTITION           - Partitioned areas of a physical disk.
       PORT                - I/O ports
       PORTCONNECTOR       - Physical connection ports
       PRINTER             - Printer device [CALL/SET]
       PRINTERCONFIG       - Printer device configuration  
       PRINTJOB            - Print job [CALL]
       PROCESS             - Processes [CALL]*
       PRODUCT             - Windows Installer [CALL]
       QFE                 - Quick Fix Engineering (patches)
       QUOTASETTING        - Setting information for disk quotas on a volume. [SET]
       RDACCOUNT           - Remote Desktop connection permission [CALL]
       RDNIC               - Remote Desktop connection on a specific network adapter [CALL/SET]
       RDPERMISSIONS       - Permissions to a specific Remote Desktop connection [CALL]
       RDTOGGLE            - Turn Remote Desktop listener on or off remotely[CALL]
       RECOVEROS           - Blue Screen Information [SET]
       REGISTRY            - Computer system registry [SET]
       SCSICONTROLLER      - SCSI Controller [CALL]
       SERVER              - Server information 
       SERVICE             - Service application [CALL]
       SHADOWCOPY          - Shadow copy management [CALL]
       SHADOWSTORAGE       - Shadow copy storage areas [CALL/SET]
       SHARE               - Shared resourcees [CALL]
       SOFTWAREELEMENT     - Elements of a software product*
       SOFTWAREFEATURE     - Subsets of SoftwareElement. [CALL]*
       SOUNDDEV            - Sound Devices 
       STARTUP             - Commands that run automatically when users logon
       SYSACCOUNT          - System account  
       SYSDRIVER           - System driver for a base service. [CALL]
       SYSTEMENCLOSURE     - Physical system enclosure
       SYSTEMSLOT          - Physical connection points including ports,
                             slots and peripherals, and proprietary connections points.
       TAPEDRIVE           - Tape drives  
       TEMPERATURE         - Temperature sensor (electronic thermometer).
       TIMEZONE            - Time zone data 
       UPS                 - Uninterruptible power supply (UPS) 
       USERACCOUNT         - User accounts [CALL/SET]
       VOLTAGE             - Voltage sensor (electronic voltmeter) data
       VOLUME              - Local storage volume [CALL/SET]
       VOLUMEQUOTASETTING  - Associates the disk quota setting with a specific disk volume. [SET]
       VOLUMEUSERQUOTA     - Per user storage volume quotas  [SET]
       WMISET              - WMI service operational parameters [SET]

for more inofrmation on a specific alias, type alias /?
Options

By default an alias will return a standard LIST of information, you can also use GET to return one or more specific properties.

      GET * will also return all properties.

Configuration changes can be made, where indicated above with: [CALL or SET ]

The CREATE and DELETE options allow you to change the WMI schema itself.

       alias 
       alias LIST [BRIEF | FULL | INSTANCE | STATUS |SYSTEM | WRITEABLE]
                    [/TRANSLATE:BasicXml|NoComma ]
                       [/EVERY:no_secs] [/FORMAT:format]
       alias GET [property list]
                    [/VALUE ] [/ALL ] [/TRANSLATE:BasicXml|NoComma ]
                       [/EVERY:no_secs] [/FORMAT:format]
       alias CALL method_name [parameters]
       alias SET [assignments]
       alias CREATE 
       alias DELETE
       alias ASSOC [/RESULTCLASS:classname] [/RESULTROLE:rolename][/ASSOCCLASS:assocclass]

       For more help
       WMIC alias /?
       WMIC alias option /?
       e.g.
       WMIC BIOS CALL /?
       WMIC MEMLOGICAL SET /?
The order of the /FORMAT and /TRANSLATE switches is significant: if /TRANSLATE follows /FORMAT, the output is formatted first and then translated.

Where
The options above can be filtered with a WHERE clause:

Where item='string value' # Test if Equal
Where item!='string value' # NOT EQUAL

Use single quotes to delimit spaces or special characters, do not add spaces to either side of the = or != 
See further examples below.

Format:
Format defines the layout of the information, XML output is automatically formatted using a default style sheet, while other formats (HTML, Table, MOF, Raw XML etc) can be specified using /FORMAT: stylesheet_name

Stylesheets supplied with WMIC:

    csv.xsl, hform.xsl, htable-sortby.xsl, htable.xsl
    texttable.xsl, textvaluelist.xsl, xml.xsl
All output files are unicode text (convert to ASCII with TYPE) Tab Separated Values (.tsv) can be opened in excel

The PROCESS alias can be used to start a new installation process, if doing this across the network, place the installer files on a share with permissions EVERYONE : Read Only. This is because network credentials will be dropped when jumping from one remote machine to another (unless you have kerberos configured).

Notes
To run WMIC requires administrator rights and for many operations Elevation.

The last element returned by WMIC is a single <CR> character (an empty line), when running WMIC in a FOR loop you might need to remove this, particularly if delayed expansion is involved.

The number of WMI properties that can be monitored has increased with every new version of Windows.

Running WMIC within a batch file it can sometimes hang, possible workarounds for this:
        START "" /W CMD /C WMIC options...
        WMIC options... <NUL

The WMI information for installed software packages (PACKAGE and SOFTWAREFEATURE) is often incomplete and inconsistent for a variety of historical reasons. A more reliable method is to retrieve a list of installed programs directly from the Add/Remove list in the registry, with a VBScript like this from Torgeir Bakken.

Examples

    :: Display the DELL Serial number (also works for some other brands)
        WMIC BIOS get serialnumber

    :: List the OS build and version
        WMIC OS LIST BRIEF

    :: List the other available OS information
        WMIC OS LIST /?

    :: List the computername, locale and Bootdevice
        WMIC OS GET csname, locale, bootdevice /value

        WMIC OS GET osarchitecture /value

    :: Get a list of installed Windows updates on a remote machine, unlike Get-Hotfix, this includes the installation date.
        WMIC /NODE:"server64" QFE list 

    :: Get the local date and time
        WMIC OS GET localdatetime

    :: List all local Disks
        WMIC LOGICALDISK where drivetype!=4 get deviceid, description, volumename

    :: List ipv4 adapters 
        WMIC NICCONFIG where (IPEnabled=True and TcpipNetbiosOptions!=null and TcpipNetbiosOptions!=2) GET             caption,index,TcpipNetbiosOptions,IPEnabled

    :: Disable Netbios
        WMIC NICCONFIG where (IPEnabled=True and TcpipNetbiosOptions!=null and TcpipNetbiosOptions!=2) CALL SetTcpipNetbios 2

    WMIC NTEVENT List Brief

    :: List all the running services and save to a file
        WMIC SERVICE where (state="running") GET caption, name, state > services.tsv

    :: Stop the TELNET service (also StartService, PauseService,ResumeService)
        WMIC SERVICE where caption='TELNET' CALL StopService

    :: Display Printer Status
        WMIC PRINTER LIST brief
        WMIC PRINTER LIST /?
        WMIC PRINTER where PortName="LPT1:" GET PortName, Name, ShareName

    WMIC /INTERACTIVE:ON PRINTER where PortName="LPT1:" DELETE

    WMIC PROCESS where name='evil.exe' delete

    WMIC /output:"%computername%.txt" MEMORYCHIP where "memorytype=17" get Capacity

    WMIC /node:computer64,computer65 PROCESS call create "netstat.exe -ano > C:\output.txt"

    WMIC /node:@computers.txt /failfast:on PROCESS call create "\\server\share\installer.cmd"

    WMIC /node:computer64 /output:shares.html SHARE get name,path /format:htable

    WMIC /node:computer64 SHARE where name="Share1" 

    Interactive mode:
    C:> WMIC
    wmic:root\cli> OS get csname
    wmic:root\cli> quit
