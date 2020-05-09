# Bot Commands

## `-help`
Provides help information sensitive to the context. It will only display
commands to which you have access in the channel that you've issued the
`-help` command.

## `-accept <answer>`
This command is used to accept the server guidelines and be fully
admitted to the server.

## `-ipcalc`
Subnet calculator functions

### `-ipcalc info <cidr|ipaddr subnetmask>`
_Aliases_: `-ipcalc ipc`,`-ipcalc subnetinfo`

Provides network, broadcast, first usable, and last usable addresses
and subnet mask.

The following examples are functionally equivalent:
```
-ipcalc info 1.2.3.4/24
```
```
-ipcalc info 1.2.3.4 255.255.255.0
```

### `-ipcalc collision <ipcidr1> <ipcidr2>`
_Aliases_: `-ipcalc overlap`,`-ipcalc cc`

Provide an answer as to whether the IPs' subnets overlap.

Example:
```
-ipcalc collision 192.16.1.2/24 192.16.0.0/23
```

## `-profile`
Modify your profile information.

### `-profile org`
Used to control your organization role. Organization roles are
email-validated roles on the Discord server in the format `org:<domain>`
to demonstrate affiliation with your employer or school.
For example, a user with an email domain of neteng.xyz may have the role
`org:neteng.xyz`. Currently, only one organization role is permitted per
user at a time.

#### `-profile org clear`
Remove any organization roles currently set.

#### `-profile org confirm <email> <key>`
Confirm an organization role using the key from your email. The key, as
well as the exact command to use, will be emailed to you when you use
the `-profile org set` command.

#### `-profile org set <email>`
Used to set your organization based on your email. Your org role will
be determined based on the domain name in your email address. _Do not use
free email addresses for this; "gmail.com" is probably not your
employer or school, but "google.com" might be. Use your employer or
school email address here.

Once you submit this command, you will be emailed a verification code and
command to confirm your affiliation.

_Note that your email address will be briefly publicly exposed when you
answer this, but it will be deleted immediately by the bot and is not
stored by the bot. The source code to achieve this is publicly viewable._

Example use:
```
-profile org set user@myemployer.com
```
