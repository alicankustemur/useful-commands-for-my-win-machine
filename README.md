```bash

# Find all .png files and rename them
find . -type f -name '*.png' -printf "mv '%h/%f' '%h/%s_%f'\n" | sh

# Find all .png files and move them to the upper folder
find . -type f -name '*.png' -printf "mv -n '%h/%f' ./\n" | sh

# Remove _8047 string from the png file recursively
Get-ChildItem  -Filter "*png" | Rename-Item -NewName {$_.Name -replace '_8047'}

# List all file types on the directory
find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u

# Check How many .png files found 
find . -type f -name '*.png' -printf "mv -n '%h/%f' ./\n" | wc -l

```