# Service Efficiency v2.0

Not so long ago we introduced [service efficiency](https://github.com/ryandotsmith/qed/blob/master/service-efficiency.md) --the state of the art for visibility into your HTTP services running on Heroku. Today we are excited to announce the general availability of service efficiency. Now you can get service efficiency charts on any system on any platform. You can start using service efficiency today.

1. Signup for a 2020 account.
2. Grab the [log-shuttle]() binary.
3. Pipe service efficiency data to 2020.

Signup.

```bash
# Generate a new password to use with our service.
$ dd bs=8 count=1 if=/dev/random of=/dev/stdout | xxd -p > 2020-password.txt
# Signup for 2020 usnig your generated password.
$ curl -X PUT -u "ryan@2020.io:$(cat 2020-password.txt)" https://api.2020.io/signup
```

Download log-shuttle.

```bash
$ curl -o log-shuttle "https://static.2020.io/arch/`uname`/bin/log-shuttle"
$ chmox +x ./log-suttle
```

Log Service Efficiency.

```bash
$ echo 'reqid=123 measure=my-photo-service at=enqueue'               >> logfile
$ echo 'reqid=123 measure=my-photo-service at=dequeue'               >> logfile
$ echo 'reqid=123 measure=my-photo-service at=begin-work'            >> logfile
$ echo 'reqid=123 measure=my-photo-service at=end-work success=true' >> logfile
```

Send logs to 2020.

```bash
$ cat logfile | ./log-shuttle -token="`cat 2020-password.txt`" -procid="demo"
```
