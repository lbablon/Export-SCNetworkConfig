
# Export-SCNetworkConfig.ps1 - Powershell script to export SCVMM network configuration.

The script lists every logical networks and dependencies such as vm networks and sites from a SCVMM server and exports the results in a ps script named ./Import-SCNetworkConfig.ps1 so it can be replay on a new SCVMM server. 

Objects that are currently exported include :

- Logical Networks
- Logical Network's sites and configuration
- VM Networks and configuration

Not yet implemented but in roadmap : 

- Port profiles configuration
- SCIP addresses
- Clouds

## Usage

The script can be run from the powershell console of the SCVMM console or from a computer with the VirtualMachineManager already loaded and with
an access to the SCVMM server. Just use the Get-SCVMMServer beforehand with a user with sufficient permissions. You can also speficy the filepath for the import script to be build by using the -output switch.

## Parameters

- **[-output]**, path for the import ps script

## Examples

```
"./Export-SCNetworkConfig.ps1"
```

Runs the script and exports the current scvmm server's network configuration as ps commands in the ps script ".\Import-SCNetworkConfig.ps1". 

```
"./Export-SCNetworkConfig.ps1" -Output "C:\temp\import.ps1"
```

Runs the script and exports the current scvmm server's network configuration as ps commands in the ps script "C:\temp\import.ps1".

