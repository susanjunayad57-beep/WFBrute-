WFBRUTE – WIFI SECURITY TESTING TOOL (WINDOWS)

WfBrute is a standalone Windows executable for authorized WiFi password auditing. It scans for WPA/WPA2‑PSK networks and performs brute‑force attacks using a wordlist.

•	⚠️ LEGAL NOTICE  

Use only on networks you own or have explicit permission to test.  
Unauthorized access is illegal. The author assumes no liability.

•	FEATURES

•		📡 Scan nearby WiFi networks (SSID, BSSID, signal strength, encryption)
•		🔑 Brute‑force WPA2‑PSK networks with a password wordlist
•		🚀 Fast mode – reduces delays for strong signal environments (use with caution)
•		🖥️ Interactive mode – menu‑driven target and wordlist selection
•		🎨 Colored terminal output – colored tables, progress bars, ASCII‑safe (no emoji)
•		🧹 Password filtering – only printable ASCII, minimum 8 characters
•		💾 Memory efficient – streams passwords from disk
•		⏲️ Configurable – scan timeout, connection delay, attempt limit

•	REQUIREMENTS AND DETAILS

REQUIREMENTS	        DETAILS

OS	                  Windows 10/11 (64 Bits)

PRIVILIGES	          Administrator Rights (Run As Administrator)

WIFI ADAPTER	        Uses Your Built-In Wireless Adapter – No External Hardware Needed.



•	INSTALLATION

1.	Download WfBrute.exe To A Folder Of Your Choice (E.G.,       `C:\WfBrute\`).
2.	Add The Folder To Your `PATH` Environment Variable To Run WfBrute From Any Command Prompt.
3.	No Further Installation – It’s Ready To Run.

•	USAGE

Open Command Prompt Or Powershell As Administrator And Run-


WfBrute [OPTIONS] [SSID] [WORDLIST]





•	COMMAND‑LINE OPTIONS

OPTIONS	              DESCRIPTIONS
-s, --scan	          Scan only mode – list networks and exit
--scan-timeout        SEC	Seconds to wait for scan results (default: 3)
-f, --fast	          Fast brute force mode (1s delay + aggressive polling)
-d, --delay           SEC	Connection delay in seconds (default: 2, ignored if --fast)
-m, --max-attempts N	Stop after N password attempts
-h, --help	          Show this help message


⚠️ IMPORTANT – FAST MODE WARNING
 
o	The `--fast` option reduces connection delay to 1 second and uses very short polling intervals.  
o	AVOID USING FAST MODE FOR ACCURATE ATTACKS unless you are certain the target signal is excellent.  
o	On weaker signals, fast mode may cause false negatives (the tool may report failure even when a password is correct).  
o	For reliable results, use the default delay (2 seconds) or increase it with `-d`.

•	EXAMPLES

Scan for networks:

cmd
WfBrute --scan

Interactive mode (no arguments):
cmd
WfBrute

- Scans for networks  
- You select a target  
- You provide wordlist path and other options

Direct brute force (default delay – recommended for accuracy):

cmd
WfBrute "MyHomeWiFi" C:\wordlists\rockyou.txt




Fast mode – only when signal is very strong (use with caution):

cmd
WfBrute --fast "CoffeeShop" D:\passwords.txt

Limit attempts with custom delay:

cmd
WfBrute -d 3 -m 5000 "MyHomeWiFi" C:\wordlists\rockyou.txt

Custom scan timeout:

cmd
WfBrute --scan --scan-timeout 5

•	HOW IT WORKS

1. Privilege check – exits if not run as Administrator.  
2. Scan – uses your built‑in wireless interface to scan for nearby networks.  
3. Target selection – via CLI argument or interactive menu.  
4. Wordlist processing – only printable ASCII passwords with length ≥ 8 are used.  
5. Brute‑force loop – for each password:  
   - Creates a temporary WiFi profile  
   - Attempts connection to the target AP  
   - Polls the connection status until timeout  

•	WORDLIST FORMAT

- Plain text file (UTF‑8 or ANSI), one password per line.  
- Only lines that are printable ASCII and at least 8 characters long are used.  
- Example:
  password123
  MySecret99
  Winter2024






•	TROUBLESHOOTING

“NO WIRELESS INTERFACE FOUND”

- Ensure your WiFi adapter is enabled in Device Manager.  
- Try reinstalling the wireless driver from the manufacturer.

•	SCAN RETURNS FEW OR NO NETWORKS

- Increase scan timeout: `--scan-timeout 5` (or higher).  
- Move closer to access points.  
- Disable other network management tools (e.g., third‑party WiFi managers).

•	CONNECTION ATTEMPTS ALWAYS FAIL

- Target must be WPA/WPA2‑PSK (not Enterprise, WEP, or WPA3).  
- Weak signal can cause timeouts – do not use `--fast`; use default delay or higher.  
- Increase delay with `-d 4` (or higher) for slow‑responding APs.


•	FAST MODE GIVES FALSE NEGATIVES
- As warned above, fast mode trades accuracy for speed.  
- If you suspect a correct password is being missed, rerun without `--fast` (or with `-d 3` or `-d 4`).

“ACCESS IS DENIED” / “PERMISSION DENIED”

- Right‑click `WfBrute.exe` → Run as administrator.
- Or launch Command Prompt as Administrator first, then run  `WfBrute`.

THE EXECUTABLE DOESN’T START / MISSING DLLS

- Install the latest [Microsoft Visual C++ Redistributable] (https://aka.ms/vs/17/release/vc_redist.x64.exe) (x64 version).

DISCLAIMER

This software is provided “as is”, without warranty of any kind.  
By using this tool, you agree that you are solely responsible for complying with all applicable laws.  
The author does not condone unauthorized access to computer systems or networks.


Download From 



LICENSE

MIT – see [LICENSE](LICENSE) file (included in the release package).

AUTHOR

Security Research & Development – For issues or contributions, please open an issue on the project repository.

                                
                                             
                                     CRATED BY
                                     JUNAYAD AHSAN
