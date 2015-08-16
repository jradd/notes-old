# CLi-Fu

grep
---------------------------------------
```bash
grep "^[^#;]" $FILENAME
```


group
---------------------------------------
```bash
dscl . -read /Groups/staff | awk '($1 == "PrimaryGroupID:") { print $2 }'
```

### Zsh

