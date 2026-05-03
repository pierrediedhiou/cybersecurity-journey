# Linux Commands Cheatsheet

## Navigation
- pwd — Print Working Directory, shows current location
- cd foldername — Change Directory, move into a folder
- ls — List files in current directory

## File Operations
- cat filename — Display contents of a file
- cat > filename — Create/overwrite a file
- cat >> filename — Append to a file
- echo "text" > filename — Overwrite file with text
- echo "text" >> filename — Append text to file

## Searching
- find / -name "filename" 2>/dev/null — Search entire system for a file
- find folder1 folder2 -type f — Find files in specific folders
- grep "keyword" filename — Search inside a file for a keyword

## Networking
- ss -tuln — Show all listening ports
- ss -tulnp — Show listening ports with process names
