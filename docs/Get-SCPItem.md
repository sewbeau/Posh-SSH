---
external help file: PoshSSH.dll-help.xml
Module Name: Posh-SSH
online version: https://github.com/darkoperator/Posh-SSH/tree/master/docs
schema: 2.0.0
---

# Get-SCPItem

## SYNOPSIS
Download from a remote server via SCP a file or directory.

## SYNTAX

### NoKey (Default)
```
Get-SCPItem -Destination <String> -Path <String> -PathType <String> [-NewName <String>]
 [-PathTransformation <String>] [-ComputerName] <String[]> [-Credential] <PSCredential> [-Port <Int32>]
 [-ProxyServer <String>] [-ProxyPort <Int32>] [-ProxyCredential <PSCredential>] [-ProxyType <String>]
 [-ConnectionTimeout <Int32>] [-OperationTimeout <Int32>] [-KeepAliveInterval <Int32>] [-AcceptKey] [-Force]
 [-ErrorOnUntrusted] [-KnownHost <IStore>] [-ProgressAction <ActionPreference>] [<CommonParameters>]
```

### Key
```
Get-SCPItem -Destination <String> -Path <String> -PathType <String> [-NewName <String>]
 [-PathTransformation <String>] [-ComputerName] <String[]> [-Credential] <PSCredential> [-Port <Int32>]
 [-ProxyServer <String>] [-ProxyPort <Int32>] [-ProxyCredential <PSCredential>] [-ProxyType <String>]
 [-KeyFile <String>] [-ConnectionTimeout <Int32>] [-OperationTimeout <Int32>] [-KeepAliveInterval <Int32>]
 [-AcceptKey] [-Force] [-ErrorOnUntrusted] [-KnownHost <IStore>] [-ProgressAction <ActionPreference>]
 [<CommonParameters>]
```

### KeyString
```
Get-SCPItem -Destination <String> -Path <String> -PathType <String> [-NewName <String>]
 [-PathTransformation <String>] [-ComputerName] <String[]> [-Credential] <PSCredential> [-Port <Int32>]
 [-ProxyServer <String>] [-ProxyPort <Int32>] [-ProxyCredential <PSCredential>] [-ProxyType <String>]
 [-KeyString <String[]>] [-ConnectionTimeout <Int32>] [-OperationTimeout <Int32>] [-KeepAliveInterval <Int32>]
 [-AcceptKey] [-Force] [-ErrorOnUntrusted] [-KnownHost <IStore>] [-ProgressAction <ActionPreference>]
 [<CommonParameters>]
```

## DESCRIPTION
Download from a remote server via SCP a file or directory.

## EXAMPLES

### Example 1
```
PS C:\> Get-SCPItem -ComputerName 192.168.1.169 -Credential carlos -Path "/var/log/dmesg" -PathType File -Destination ./
```

Download in to the local path the dmesg file.

### Example 2
```
PS C:\> Get-SCPItem -ComputerName 192.168.1.169 -Credential carlos -Path "/var/log/dmesg" -PathType File -Destination ./ -NewName dmesg_server_169
```

Download in to the local path the dmesg file and give it a different name.

## PARAMETERS

### -AcceptKey
Auto add host key fingerprint to the list of trusted host/gingerprint pairs.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
FQDN or IP Address of host to establish a SSH connection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: HostName, Computer, IPAddress, Host

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionTimeout
Connection timeout interval in seconds.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
SSH Credentials to use for connecting to a server.
If a key file is used the password field is used for the Key pass phrase.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Destination
Path to the location where to download the item to.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorOnUntrusted
Raise an exception if the fingerprint is not trusted for the host.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Do not check the remote host fingerprint.
When downloading if a file already exists it will overwrite the file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyFile
OpenSSH format SSH private key file.

```yaml
Type: String
Parameter Sets: Key
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyString
String array of the content of a OpenSSH key file.

```yaml
Type: String[]
Parameter Sets: KeyString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName
New name for the item on the destination path.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OperationTimeout
Timeout for execution of an operation.
Zero or below disables timeout

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Path to item on the remote host to download.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PathType
What type of Item you are getting from the remote host via SCP.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: File, Directory

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
SSH TCP Port number to use for the SSH connection.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 22
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential
PowerShell Credential Object with the credentials for use to connect to proxy server if required.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyPort
Port to connect to on proxy server to route connection.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 8080
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyServer
Proxy server name or IP Address to use for connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyType
Type of Proxy being used (HTTP, Socks4 or Socks5).

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: HTTP, Socks4, Socks5

Required: False
Position: Named
Default value: HTTP
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeepAliveInterval
Sets a timeout interval in seconds after which if no data has been received from the server, session will send a message through the encrypted channel to request a response from the server

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KnownHost
Known Host IStore either from New-SSHMemoryKnownHost, Get-SSHJsonKnownHost or Get-SSHOpenSSHKnownHost.

```yaml
Type: IStore
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PathTransformation
Remote Path transormation to use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

### System.String[]
System.Management.Automation.PSCredential System.Int32 System.String System.Boolean System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
