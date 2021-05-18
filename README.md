# hacktricks
Little utility to quickly open up book.hacktricks.xyz for a certain port or a nmap file. Created for HTB and OSCP.

# Installation

Clone the repo anywhere you want, and add the following to your shell's config file and adapt to your browser and/or other needs.

```
export HACKTRICKS_LIST=/path/to/your/hacktricks.lst

function hacktricks() {
        if [ $# -eq 1 ]; then
                links=$(grep -i "$1" $HACKTRICKS_LIST | awk '{ print $1}')
                for l in $links; do
                        echo $l
                        firefox $l
                done
        else
                echo "Usage: hacktricks <port or service>"
        fi

}

```

# Usage

Running `hacktricks <port no>` or `hacktricks <service>` runs `grep` on the list of all pages, and opens the ones that match.

# TODOs
- Maybe include fulltext search
- Add param to load data from nmap output and open hacktricks for all open ports