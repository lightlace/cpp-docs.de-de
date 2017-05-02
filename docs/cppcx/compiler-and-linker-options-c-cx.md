---
title: "Optionen f&#252;r Compiler und Linker (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Optionen f&#252;r Compiler und Linker (C++/CX)
Eine Umgebungsvariable, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Compileroptionen und Linkeroptionen unterstützen die Erstellung von Apps für die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
## Bibliothekspfad  
 Die %LIBPATH%\-Umgebungsvariable gibt den Standardpfad für die Suche nach WINMD\-Dateien an.  
  
## Compileroptionen  
  
|Option|Beschreibung|  
|------------|------------------|  
|[\/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> \/ZW:nostdlib|Aktiviert [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Spracherweiterungen.<br /><br /> Der `nostdlib`\-Parameter verhindert, dass der Compiler den standardmäßigen, vordefinierten Suchpfad verwendet, um Assembly\- und WINMD\-Dateien zu finden.<br /><br /> Die Compileroption [\/ZW](../build/reference/zw-windows-runtime-compilation.md) gibt die folgenden Compileroptionen implizit an:<br /><br /> -   [\/Fi](../build/reference/fi-name-forced-include-file.md) vccorlib.h: Erzwingt die Einbindung der Headerdatei „vccorlib.h“, die viele für den Compiler erforderliche Typen definiert.<br />-   [\/FU](~/build/reference/fu-name-forced-hash-using-file.md) Windows.winmd: Erzwingt die Einbindung der Windows.winmd\-Metadatendatei, die vom Betriebssystem bereitgestellt wird und viele Typen in der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] definiert.<br />-   [\/FU](~/build/reference/fu-name-forced-hash-using-file.md) Platform.winmd: Erzwingt die Einbindung der Platform.winmd\-Metadatendatei, die vom Compiler bereitgestellt wird und die meisten Typen in der Plattformfamilie von Namespaces definiert.|  
|[\/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|Fügt ein durch den *dir*\-Parameter angegebenes Verzeichnis zum Suchpfad hinzu, der vom Compiler für die Suche nach Assembly\- und WINMD\-Dateien verwendet wird.|  
|[\/FU](~/build/reference/fu-name-forced-hash-using-file.md) *Datei*|Erzwingt die Einbindung des angegebenen Moduls oder der WINMD\-Datei. Das bedeutet, Sie müssen `#using` *Datei* nicht im Quellcode angeben. Der Compiler erzwingt automatisch die Einbindung der eigenen Windows\-Metadatendatei „Platform.winmd“.|  
|\/D "WINAPI\_FAMILY\=2"|Erstellt eine Definition, die die Verwendung einer Teilmenge des Win32\-SDKs ermöglicht, die mit der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] kompatibel ist.|  
  
## Linkeroptionen  
  
|Option|Beschreibung|  
|------------|------------------|  
|\/APPCONTAINER\[:NO\]|Markiert die ausführbare Datei als \(nur\) „im App\-Container ausführbar“.|  
|\/WINMD\[:{NO&#124;ONLY}\]|Gibt eine WINMD\-Datei und eine zugeordnete Binärdatei aus. Diese Option muss an den Linker übergeben werden, damit eine WINMD\-Datei ausgegeben wird.<br /><br /> **NO** – Gibt keine WINMD\-Datei, aber eine Binärdatei aus<br /><br /> **ONLY** – Gibt eine WINMD\-Datei, aber keine Binärdatei aus|  
|\/WINMDFILE:*Dateiname*|Der Name der auszugebenden WINMD\-Datei, anstelle des Namens der WINMD\-Standarddatei. Wenn mehrere Dateinamen in der Befehlszeile angegeben werden, wird der letzte Name verwendet.|  
|\/WINMDDELAYSIGN\[:NO\]|Signiert die WINMD\-Datei teilweise und platziert den öffentlichen Schlüssel in der Binärdatei.<br /><br /> **NO** – \(Standard\) Die WINMD\-Datei wird nicht signiert.<br /><br /> \/WINMDDELAYSIGN hat keine Auswirkung, sofern nicht \/WINMDKEYFILE oder \/WINMDKEYCONTAINER ebenfalls angegeben sind.|  
|\/WINMDKEYCONTAINER:*Name*|Gibt einen Schlüsselcontainer zum Signieren einer Assembly an. Der *Name*\-Parameter entspricht dem Schlüsselcontainer, der zum Signieren der Metadatendatei verwendet wird.|  
|\/WINMDKEYFILE:*Dateiname*|Gibt einen Schlüssel oder ein Schlüsselpaar zum Signieren der Assembly an. Der *Dateiname*\-Parameter entspricht dem Schlüssel, der zum Signieren der Metadatendatei verwendet wird.|  
  
## Hinweise  
 Wenn Sie **\/ZW** verwenden, stellt der Compiler automatisch eine Verknüpfung zur DLL\-Version der C\-Laufzeit \(CRT\) her. Das Verknüpfen mit der statischen Bibliotheksversion ist nicht zulässig und jegliche Verwendung von CRT\-Funktionen, die in einer [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App nicht gestattet sind, führen zu einem Kompilierungsfehler.  
  
## Siehe auch  
 [Erstellen von Apps und Bibliotheken](../cppcx/building-apps-and-libraries-c-cx.md)