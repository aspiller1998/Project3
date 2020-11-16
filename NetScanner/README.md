## Powershell IPv4 LAN Scanner

## This script allows you to scan your LAN to see what devices are connected. It also resolves MAC Addresses and matches them to their respective vendor to see the manufacturer.

## Resource: https://github.com/BornToBeRoot/PowerShell_IPv4NetworkScanner




## Instructions

1. Enter your network IP Addresses
2. Enter your CIDR
3. Press enter
4. View results

## Syntax
```powershell
.\IPv4NetworkScan.ps1 [-StartIPv4Address] <IPAddress> [-EndIPv4Address] <IPAddress> [[-Tries] <Int32>] [[-Threads] <Int32>] [[-DisableDNSResolving]] [[-EnableMACResolving]] [[-ExtendedInformations]] [[-IncludeInactive]] [<CommonParameters>]

.\IPv4NetworkScan.ps1 [-IPv4Address] <IPAddress> [-Mask] <String> [[-Tries] <Int32>] [[-Threads] <Int32>] [[-DisableDNSResolving]] [[-EnableMACResolving]] [[-ExtendedInformations]] [[-IncludeInactive]] [<CommonParameters>]

.\IPv4NetworkScan.ps1 [-IPv4Address] <IPAddress> [-CIDR] <Int32> [[-Tries] <Int32>] [[-Threads] <Int32>] [[-DisableDNSResolving]] [[-EnableMACResolving]] [[-ExtendedInformations]] [[-IncludeInactive]] [<CommonParameters>]
```

## Example 1

```powershell
PS> .\IPv4NetworkScan.ps1 -StartIPv4Address 192.168.178.0 -EndIPv4Address 192.168.178.20

IPv4Address   Status Hostname
-----------   ------ --------
192.168.178.1 Up     fritz.box
```

## Example 2

```powershell
PS> .\IPv4NetworkScan.ps1 -IPv4Address 192.168.178.0 -Mask 255.255.255.0 -DisableDNSResolving

IPv4Address    Status
-----------    ------
192.168.178.1  Up
192.168.178.22 Up
```

## Example 3

```powershell
PS> .\IPv4NetworkScan.ps1 -IPv4Address 192.168.178.0 -CIDR 25 -EnableMACResolving

IPv4Address    Status Hostname           MAC               Vendor
-----------    ------ --------           ---               ------
192.168.178.1  Up     fritz.box          XX-XX-XX-XX-XX-XX AVM Audiovisuelles Marketing und Computersysteme GmbH
192.168.178.22 Up     XXXXX-PC.fritz.box XX-XX-XX-XX-XX-XX ASRock Incorporation
```
