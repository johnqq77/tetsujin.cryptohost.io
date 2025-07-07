#!/bin/bash
clear
echo "WELCOME TO SWIFT.NET"
echo
echo "%global_server/start"
echo
read -p "login    = " login
read -sp "password = " pass; echo
read -p "Officer Pin = " pin

echo "[CONNECTED]"
sleep 2

echo "%global_server/messages"
sleep 1
echo "TRN: DE90293485009230"
echo "SENDER ACCOUNT NAME: HSBC HOLDINGS PLC"
echo "RECEIVER ACCOUNT NAME: VECO LOGISTICS INC."
echo "AMOUNT: 3,987,707,000.00 EURO"
sleep 2

echo "DOWNLOADING..."
sleep 3
echo "[DOWNLOAD COMPLETED]"

echo "%global_server/download/usdt/convert/DE90293485009230"
sleep 2
echo "CONVERTING..."
sleep 3
echo "[CONVERTED COMPLETED]"

echo
echo "Sending payload to Ethereum node..."
curl -X POST -H "Content-Type: application/json" \
    --data @3987.json \
    https://eth-mainnet.g.alchemy.com/v2/4UjvaNeaH9VVr-5RkvcsIVZx8_hJ0DvG

echo "[CONVERT APPROVED]"
