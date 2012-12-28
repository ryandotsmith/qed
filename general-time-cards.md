# Timecard v2.0

Not so long ago we introduced [timecards](https://github.com/ryandotsmith/qed/blob/master/time-cards.md) --the state of the art for visibility into your HTTP services running on Heroku. Today we are excited to anounce the general availability of timecards. Now you can get timecards on any system on any platform. You can start using timecards today.

1. Signup for a 2020 account.
2. Grab the [log-shuttle]() binary.
3. Pipe timecard-conventional data to log-shuttle.

Signup.

```bash
# Generate a new password to use with our service.
$ dd bs=8 count=1 if=/dev/random of=/dev/stdout | xxd -p > 2020-password.txt
# Signup for 2020 usnig your generated password.
$ curl -X PUT -u "ryan@2020.io:$(cat 2020-password.txt)" https://api.2020.io/signup
```

Download log-shuttle.

```bash
$ curl -o log-shuttle "https://static.2020.io/arch/`uname`/bin/log-shuttle
$ chmox +x ./log-suttle
```

Create timecards.

```bash
$ echo 'reqid=123 measure=my-photo-service at=enqueue'    					 >> logfile
$ echo 'reqid=123 measure=my-photo-service at=dequeue'    					 >> logfile
$ echo 'reqid=123 measure=my-photo-service at=begin-work' 					 >> logfile
$ echo 'reqid=123 measure=my-photo-service at=end-work success=true' >> logfile
```
