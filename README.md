# logj4checker
Log J4 Vulnerability checker


This is a Bash script that searches for files on a Linux system that contain the string "log4j" in their name or their contents. It also checks if any packages containing "solr," "elastic," or "log4j" are installed, and whether Java is installed. Finally, it scans JAR/WAR/EAR files on the system for the presence of log4j files and optionally checks them against a list of known vulnerable hashes.

Here is a brief description of what each part of the script does:

The PACKAGES variable is set to "solr|elastic|log4j", which defines the list of packages to search for.
The SHA256_HASHES_URL variable is set to the first argument provided to the script, which is expected to be a URL pointing to a list of SHA256 hashes of vulnerable log4j versions.
The script defines several Bash functions to output messages in different colors and to perform various checks.
The locate_log4j() function uses the locate command to search for files containing "log4j" in their name. If locate is not installed, it uses the find command instead.
The find_jar_files() function finds all JAR/WAR/EAR files on the system.
The script checks if the user is running as root and warns them if they are not.
The script downloads a list of known vulnerable hashes from the provided URL and checks JAR/WAR/EAR files against them.
The script performs three scans: (1) it searches for files containing "log4j" using the locate command or the find_jar_files() function, (2) it checks for installed packages containing "solr," "elastic," or "log4j," and (3) it checks if Java is installed and warns that log4j could be bundled inside Java applications.
Finally, the script scans JAR/WAR/EAR files for the presence of log4j files and optionally checks them against the list of known vulnerable hashes. If any files containing "log4j" are found, the script outputs a warning message.
