---
external help file: Posh-SSH.psm1-Help.xml
Module Name: Posh-SSH
online version: https://github.com/darkoperator/Posh-SSH/tree/master/docs
schema: 2.0.0
---

# Invoke-SSHCommand

## SYNOPSIS
Executes a given command on a remote SSH host.

## SYNTAX

### Index (Default)
```
Invoke-SSHCommand [-Command] <String> [-SessionId] <Int32[]> [-EnsureConnection] [[-TimeOut] <Int32>]
 [[-ThrottleLimit] <Int32>] [-ShowStandardOutputStream] [-ShowErrorOutputStream]
 [-StandardOutputStreamColor <String>] [-ErrorOutputStreamColor <String>] [-ProgressAction <ActionPreference>]
 [<CommonParameters>]
```

### Session
```
Invoke-SSHCommand [-Command] <String> [-SSHSession] <SshSession[]> [-EnsureConnection] [[-TimeOut] <Int32>]
 [[-ThrottleLimit] <Int32>] [-ShowStandardOutputStream] [-ShowErrorOutputStream]
 [-StandardOutputStreamColor <String>] [-ErrorOutputStreamColor <String>] [-ProgressAction <ActionPreference>]
 [<CommonParameters>]
```

## DESCRIPTION
Executes a given command on a remote SSH host given credentials to the host or using an existing SSH Session.

## EXAMPLES

### EXAMPLE 1
```
Invoke-SSHCommand -Command "uname -a" -SessionId 0,2,3


Host       : 192.168.1.163
Output     : Linux debian6 2.6.32-5-amd64 #1 SMP Sun Sep 23 10:07:46 UTC 2012 x86_64 GNU/Linux

ExitStatus : 0

Host       : 192.168.1.155
Output     : Linux ole6 2.6.39-300.17.1.el6uek.x86_64 #1 SMP Fri Oct 19 11:29:17 PDT 2012 x86_64 x86_64 x86_64 GNU/Linux

ExitStatus : 0

Host       : 192.168.1.234
Output     : Linux ubuntusrv 3.2.0-29-generic #46-Ubuntu SMP Fri Jul 27 17:03:23 UTC 2012 x86_64 x86_64 x86_64 GNU/Linux

ExitStatus : 0
```

## PARAMETERS

### -Command
Command to execute in remote host.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionId
SSH Session Id of an exiting session.

```yaml
Type: Int32[]
Parameter Sets: Index
Aliases: Index

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnsureConnection
Ensures a connection is made by reconnecting before command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeOut
Time out in seconds to wait for the command to return a value.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent connections that can be established to run this command.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHSession
SSH Session object.

```yaml
Type: SshSession[]
Parameter Sets: Session
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ShowStandardOutputStream
Displays the result of the standard output of the command in live

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowErrorOutputStream
Displays the result of the error output of the command in live

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandardOutputStreamColor
Display color of the standard output.
Works only with -ShowStandardOutputStream

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: White
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorOutputStreamColor
Display color of the error output.
Works only with -ShowErrorOutputStream

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Red
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProgressAction
{{ Fill ProgressAction Description }}

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: proga

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### SSH.SshSession[]
## OUTPUTS

## NOTES
AUTHOR: Carlos Perez carlos_perez@darkoprator.com

## RELATED LINKS
