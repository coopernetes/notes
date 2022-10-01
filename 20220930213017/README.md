# Stuff I never remember in bash

Combine stderr and stdout:

```shell
[some-command] 2>&1

# To fully suppress all output
[some-command] 2>&1 > /dev/null

# Write to file
[some-command] 2>&1 | tee out-and-err.log # -a option to append
```

Using `-exec` with find:

```shell
find some/path -type f -iname "searchforthisfile*" \
	-exec some command with trailing args {} \;   	# <<< I NEVER REMEMBER THE ORDER OF THAT BACKSLASH

find some/path -type f -iname "searchforthisfile*" \
	| xargs -n1 cat   				# using xargs 

find some/path -type f -iname "searchforthisfile*" \
	| xargs -I {} sh -c "some-command {} --with-shell-expansion" # using xargs 
```
