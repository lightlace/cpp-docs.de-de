---
title: "/TSAWARE (Terminalserverf&#228;hige Anwendung erstellen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tsaware"
  - "VC.Project.VCLinkerTool.TerminalServerAware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TSAWARE (Linkeroption)"
  - "Terminalserver"
  - "Terminalserver, Terminalserverfähige Anwendungen"
  - "TSAWARE (Linkeroption)"
  - "-TSAWARE (Linkeroption)"
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TSAWARE (Terminalserverf&#228;hige Anwendung erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TSAWARE[:NO]  
```  
  
## Hinweise  
 Die \/TSAWARE\-Option legt ein Flag im Feld "IMAGE\_OPTIONAL\_HEADER DllCharacteristics" im optionalen Header des Programmimage fest.  Wenn dieses Flag eingerichtet ist, nimmt Terminalserver bestimmte Änderungen an der Anwendung nicht vor.  
  
 Wenn eine Anwendung den Terminalserver nicht erkennt \(Legacyanwendung\), kann der Terminalserver an der Legacyanwendung bestimmte Anpassungen vornehmen, damit diese in einer Mehrbenutzerumgebung fehlerfrei funktioniert.  Der Terminalserver erstellt z. B. einen virtuellen Windows\-Ordner, sodass allen Benutzern anstelle eines Windows\-Systemverzeichnisses ein eigener Windows\-Ordner zur Verfügung steht.  Damit erhalten die Benutzer Zugriff auf ihre eigene INI\-Datei.  Zusätzlich nimmt der Terminalserver Änderungen an der Registrierung der Legacyanwendung vor.  Durch diese Anpassungen verlangsamt sich der Ladevorgang für die Legacyanwendung auf dem Terminalserver.  
  
 Wenn eine Anwendung den Terminalserver jedoch erkennt, sind während der Installation weder INI\-Dateien notwendig noch müssen Einträge in die Registrierung von **HKEY\_CURRENT\_USER** vorgenommen werden.  
  
 Wenn die Anwendung auf INI\-Dateien zugreift, gleichzeitig aber die Option **\/TSAWARE** verwendet wird, werden die Dateien für alle Systembenutzer freigegeben.  Wenn dies in der konkreten Situation akzeptabel ist, können Sie die Anwendung mit **\/TSAWARE** verknüpfen; anderenfalls sollten Sie **\/TSAWARE:NO** verwenden.  
  
 Die Option **\/TSAWARE** ist für Windows 2000 und höher, Windows\- und Konsolenanwendungen standardmäßig aktiviert.  Weitere Informationen finden Sie unter [\/SUBSYSTEM \(Subsystem angeben\)](../../build/reference/subsystem-specify-subsystem.md) und [\/VERSION \(Versionsinformationen\)](../../build/reference/version-version-information.md).  
  
 **\/TSAWARE** ist nicht gültig für Treiber, VxDs oder DLLs.  
  
 Wenn eine Anwendung mit **\/TSAWARE** verknüpft wurde, zeigt **DUMPBIN**[\/HEADERS](../../build/reference/headers.md) diesbezüglich weitere Informationen an.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **System**.  
  
4.  Ändern Sie die Eigenschaft **Terminalserver**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Storing User\-Specific Information](http://msdn.microsoft.com/library/aa383452)   
 [Legacy Applications in a Terminal Services Environment](https://msdn.microsoft.com/en-us/library/aa382957.aspx)