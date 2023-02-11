# PowerShellContainers
All available tags for base images released by Microsoft can be found here https://hub.docker.com/_/microsoft-powershell

## Building docker containers that use PowerShelll

```dockerfile
FROM mcr.microsoft.com/powershel
SHELL ["pwsh", "-Command"]
RUN Set-PSRepository -Name "PSGallery" -InstalationPolicy Trusted
RUN Install-Module SampleModule
ADD SampleScript.ps1 /scripts/SampleScript.ps1
ENTRYPOINT ["pwsh", "-Command", "/scripts/SampleScript.ps1"]
```

## Running PowersShell interactive console inside container

```shell
docker run -it --rm mcr.microsoft.com/powershell
```
