# WindowsPowerShell

## Hyper-V Notes

### Create New Virtual Switch

``` posh
$net = get-netadapter -Name Wi-Fi ; New-VMSwitch -Name "Bridging Switch" -AllowManagementOS $True -NetAdapterName $net.Name

### Create New VM

``` posh
New-VM -Name Server_Ubuntu_18-04 -MemoryStartupBytes 3221225472 -NewVHDPath D:\Hyper-V\Server_Ubuntu_18-04.vhdx" -NewVHDSizeBytes 16106127360 -SwitchName "Bridging Switch"

### Mount ISO to DVD Drive
``` posh
Set-VMDvdDrive -VMName $vm.name -Path C:\Users\brian\Downloads\ubuntu-18.04-desktop-amd64.iso