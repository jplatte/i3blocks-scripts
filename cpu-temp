#!/bin/bash
temp=$(
    sensors 'coretemp-*' \
        | grep '^Package id' \
        | awk '{ print $4 }' \
        | grep -o '[0-9]\+' \
        | head -n1
)

if [[ "$temp" -lt 30 ]]; then
    printf '\uf2cb'
elif [[ "$temp" -lt 40 ]]; then
    printf '\uf2ca'
elif [[ "$temp" -lt 50 ]]; then
    printf '\uf2c9'
elif [[ "$temp" -lt 60 ]]; then
    printf '\uf2c8'
else
    printf '\uf2c9'
fi

printf '  %s\u2009°C\n' $temp

if [[ "$temp" -lt 40 ]]; then
    printf '\n#3383AE'
elif [[ "$temp" -ge 60 ]]; then
    printf '\n#EEBF13'
elif [[ "$temp" -ge 75 ]]; then
    printf '\n#E41C28'
fi
