#!/bin/sh

# シェル変数を展開した時値が設定されていないとエラー
set -u

channel=${1:-"_vg14engineers"}
token=`cat ./token`
jq=`which jq`
size=`cat ./usernames.json|jq ".users|length"`
target=$(($RANDOM % ${size}))
username=`cat ./usernames.json|jq ".users[${target}].user"|sed -e 's/\"//g'`
icon=`cat ./usernames.json|jq ".users[${target}].icon"|sed -e 's/\"//g'`
curl -F token=${token} -F channel=${channel} -F text="わかる" -F username=${username} -F icon_url=${icon} https://slack.com/api/chat.postMessage
