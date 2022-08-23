```dockerfile?+{1,9-12}|-{2,3-6}|n{5-6,15}
FROM microsoft/windowsservercore

# Executed as cmd /S /C echo default
RUN echo default

# Executed as cmd /S /C powershell -command Write-sadsfsdf
RUN powershell -command Write-Host default

# Executed as powershell -command Write-Host hello
SHELL ["powershell", "-command"]
RUN Write-Host hello

# Executed as cmd /S /C echo hello!
SHELL ["cmd", "/S", "/C"]
RUN echo hello
```
