# PowerShellContainers
How to build docker containers that use PowerShelll


```dockerfile
FROM mcr.microsoft.com/powershel
SHELL ["pwsh", "-Command"]
RUN Set-PSRepository -Name "PSGallery" -InstalationPolicy Trusted
ADD SampleScript.ps1 /scripts/SampleScript.ps1
ENTRYPOINT ["pwsh", "-Command", "/scripts/SampleScript.ps1"]
```

All available tags for based images released by Microsoft can be found here https://hub.docker.com/_/microsoft-powershell
