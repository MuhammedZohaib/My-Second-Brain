Starting metasploit

```bash
msfconsole
```

if it gives error regarding database then u need to enable PostgreSQL service

```bash
service postgresql start 
service metasploit start
msfconsole
```

# Basic Steps:
1. Picking an Exploit
2. Setting Exploit Options
3. Picking a Payload
4. Setting Payload Options
5. Running the Exploit
6. Connecting to the Remote System
7. Performing Post Exploitation Process

## Picking an Exploit

```bash
msf> show exploits
```

This will list all available exploits but we can use `search` command to find the right exploit quicker. 

```bash 
msf> help search 
```

Once we have found the right exploit we need to use this exploit for that purpose we need to run the following command:

```bash
msf> use "name of exploit" #use the expolit
msf> info "name of exploit" #gives infor regarding the exploit
```

Once you have successfully selected the type of exploit which can target a certain vulnerability in the victims machine now it time to Pick a payload.

## Picking a Payload

```bash
msf> show payloads
```

This will list several payloads which can be used against that payload. You can simply select payloads with either `remote_shell` or `meterpreter shell`. The best way is to select the shell type is `reverse tcp shell` as it is not blocked by the firewall.

```bash
msf> set payload "name of payload"
```

Once the right type of payload is selected now we need to `set payload` options.

```bash
msf> show options 
```

The above command will list all the available options which can be set in that payload.

We need to set `LHOST option` to the IP address of attacker machine so that it can make session once the exploit is successful. Once all the option are set we need to check our `set options` for one last time to make sure everything is right. 
After that we are good to go and type

```bash
msf> exploit
```

This will exploit the target machine and once exploit is successful you can have a session with the machine. 

```bash
msf> sessions
```

This command will show you available sessions in the metasploit framework.

Now we can connect to any session by using the session id and running the following command

```bash
msf> sessions -i "Id of the session"
```

once we have a session created the `msf` prompt of the terminal will change to `meterpreter` prompt.

```bash
meterpreter>
```

# Meterpreter Shell

Meterpreter is a shell created after a successful exploit. It provide set of commands which aid in security testing, as it allows to pull password hashes, gather data and system from the target machine.

## Basic Meterpreter Commands
The commands are broken down into 7 Sections:

* `Core Commands`
* `File System Commands`
* `Networking Commands`
* `System Commands`
* `User Interface Commands`
* `Webcam Commands`
* `Three priv Commands`

### Core Commands

```bash
#This will background the meterpreter session
meterpreter> background 

#We can return back to the backgrounded session by using the following command
meterpreter> sessions -i "session id" 

#Allows to use additional modules
meterpreter> load
meterpreter> run

#Exit out of meterpreter
meterpreter> exit
```

### File System Commands

```bash
cat       # Read the content of a file
cd        # Change directory
download  # download a file or directory
edit      # edit a file
getlwd    # print local working directory
getwd     # print working directory
lcd       # change local working directory
lpwd      # print local working directory
ls        # list files
mkdir     # make directory
mv        # move source to destination
pwd       # print working directory
rm        # remove file
rmdir     # remove directory
search    # search for files
upload    # upload a file or directory
```

As we have opened a meterpreter session basically we have access to 2 separate file systems 

