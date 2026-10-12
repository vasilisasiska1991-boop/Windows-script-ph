# Выгрузка процессов Windows с путями к файлам
# Отчет сохраняется на рабочем столе

$OutputFile = Join-Path ([Environment]::GetFolderPath('Desktop')) 'ProcessesWithPaths.txt'

$Processes = Get-CimInstance Win32_Process |
    Sort-Object Name, ProcessId |
    Select-Object ProcessId, Name, ExecutablePath, CommandLine

$Processes |
    Format-List |
    Out-File -FilePath $OutputFile -Encoding utf8 -Width 4096

Write-Host "Отчет сохранен: $OutputFile" -ForegroundColor Green
