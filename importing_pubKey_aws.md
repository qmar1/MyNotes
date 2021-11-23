**Converting public key to base64 encoded**

```
cat .ssh/id_rsa.pub | base64

```

**Importing your private key to aws to a paricular region**

```
$ aws ec2 import-key-pair --key-name "qmar-personal-mbp-key" --public-key-material "c3NoLXJzYSBBQUFBQjNOemFDMXljMkVBQUFBREFRQUJBQUFCZ1FDaDhrckJicm5Halg0NG9LNlJsVDFQTDREZUJSN0pQM01xdFVVaFdPN25SY0FPWDc2M2xlT2Z0TkxjTWlsRU9ZenZiVmhIRmQwVkNCWW1Nakprb1AyNThidHZjWmZQU2VpelJiZ0NMY3dpMUdQbUxKM2p5U3MxUElXVExXdHpEOUdKZ2t1ejkvWXkwWndXV3QvSlhZeGVVcFQ1VmJFVkQvenMwVU9sR1dETW5LQ3JvZFhHbVpiWE5DVDNVN2hzRlhmNmZveWY0UkdZcEtBSHluZU1iOFV2VTVWQ0FkYk13SmlJL05CeDRxZXI1dVVSYmk4emszUm1QN3RiZElXcDB5QS9ZdS82aGx5UEJMRUxnT3BkSGdIbnlta0xpVStkSWlGc3RESWVZNlZYc1FxNUdKb1h1NjhGUWhXcEtRbXA5RXIwQXRIQlNUU1RjNDd4QlRadzF2dzJQV2VZa0U1ZlNtYmVnT0JEWDh4cVJoenJ0RnAyMUVHNzFUZU5LdjNiYnBYV0crVTlQZjZqSWxSRU1vSWZCeWhmSTB6SlJ0bzJUY3IzYWVpb0hpRlB2WnRKbHlqQ0ZaNlo4VkptNTh4c0wyeTBFMkNram9wQ1p3VzJCVFhUSzh6QVRhRzVERVl1cW5OSmgyQmxjTHdmdm1FV2ZYN2J0U2FNczJKelV6UWdGSk09IGt1bWFyQEt1bWFycy1NYWNCb29rLVByby5sb2NhbAo=" --region ap-south-1
{
    "KeyFingerprint": "58:0a:5d:10:85:ef:43:b2:2e:cc:74:66:8d:3e:2e:c0",
    "KeyName": "qmar-personal-mbp-key",
    "KeyPairId": "key-0b0c978f4a9980183"
}

```

**Viewing your keys** 

```
$ aws ec2 describe-key-pairs --region ap-south-1 | jq -c '.KeyPairs[] | select(.KeyName | contains("qmar")) ' | jq .
{
  "KeyPairId": "key-0b0c978f4a9980183",
  "KeyFingerprint": "58:0a:5d:10:85:ef:43:b2:2e:cc:74:66:8d:3e:2e:c0",
  "KeyName": "qmar-personal-mbp-key",
  "KeyType": "rsa",
  "Tags": []
}
```
