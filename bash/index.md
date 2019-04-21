# bash

Bash Reference Manual: https://devdocs.io/bash/

## How To ...

### Set default values for variables

```sh
#!/usr/bin/env bash
# script.sh

# following line sets MYVAR to empty string if unset
: ${MYVAR=}

if [ "$MYVAR" = "y" ]; then
	echo "YAY!";
fi

echo "MYVAR: $MYVAR"
```

