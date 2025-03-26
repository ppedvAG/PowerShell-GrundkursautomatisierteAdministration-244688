# Skript Beispiel
```powershell
param(
[Parameter(Mandatory=$true)]
[string]$EventId,

[int]$Newest = 5,

[string]$ComputerName = "localhost"
)
Write-Verbose -Message "Zusätzliche Optionale"
Write-Verbose -Message "$EventId $Newest $ComputerName"
Get-EventLog -LogName Security -ComputerName $ComputerName | Where-Object EventId -eq $EventId | Select-Object -First $Newest
```
