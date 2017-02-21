---
title: "/ DEBUGTYPE (Debuginformationsoptionen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/debugtype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE (Linkeroption)"
  - "DEBUGTYPE (Linkeroption)"
  - "-DEBUGTYPE (Linkeroption)"
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# / DEBUGTYPE (Debuginformationsoptionen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Option „\/DEBUGTYPE“ gibt die Typen der durch die Option „\/DEBUG“ generierten Debuginformationen an.  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## Argumente  
 CV  
 Weist den Linker an, Debuginformationen für Symbole, Zeilennummern und andere Objektkompilierungsinformationen in der PDB\-Datei auszugeben.  Diese Option ist standardmäßig aktiviert, wenn **\/DEBUG** angegeben und **\/DEBUGTYPE** nicht angegeben ist.  
  
 PDATA  
 Weist den Linker an, den Debugstreaminformationen in der PDB\-Datei PDATA\- und XDATA\-Einträge hinzuzufügen.  Diese Option ist standardmäßig aktiviert, wenn die Optionen **\/DEBUG** und **\/DRIVER** angegeben sind.  Wenn **\/DEBUGTYPE:PDATA** durch sich selbst angegeben wird, bezieht der Linker die Debugsymbole automatisch in der PDB\-Datei mit ein.  Wenn **\/DEBUGTYPE:PDATA,FIXUP** angegeben ist, enthält der Linker keine Debugsymbole in der PDB\-Datei.  
  
 FIXUP  
 Weist den Linker an, den Debugstreaminformationen in der PDB\-Datei Umsetzungstabelleneinträge hinzuzufügen.  Diese Option ist standardmäßig aktiviert, wenn die Optionen **\/DEBUG** und **\/PROFILE** angegeben sind.  Wenn **\/DEBUGTYPE:FIXUP** oder **\/DEBUGTYPE:FIXUP,PDATA** angegeben ist, enthält der Linker keine Debugsymbole in der PDB\-Datei.  
  
 Argumente für **\/DEBUGTYPE** können in einer anderen Reihenfolge kombiniert werden, indem sie durch ein Komma getrennt werden.  Bei der **\/DEBUGTYPE**\-Option und ihrer Argumente wird die Groß\-\/Kleinschreibung nicht beachtet.  
  
## Hinweise  
 Verwenden Sie die **\/DEBUGTYPE**\-Option, um den Einschluss der Umsetzungstabellendaten oder der PDATA\- und XDATA\-Headerinformationen im Debugstream anzugeben.  Dadurch schließt der Linker Informationen über Benutzermoduscode mit ein, der in einem Kerneldebugger sichtbar ist, wenn die Aufschlüsselung in einen Kernelmoduscode erfolgt.  Um Debugsymbole zur Verfügung zu stellen, wenn **FIXUP** angegeben wird, müssen Sie das Argument **CV** einbeziehen.  
  
 Für das Debuggen von Code im Benutzermodus, der für Anwendungen typisch ist, wird die Option **\/DEBUGTYPE** nicht benötigt.  Standardmäßig geben die Compilerswitches, die die Debugausgabe \([\/Z7, \/Zi, \/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\) angeben, alle durch den Visual Studio\-Debugger benötigten Informationen aus.  Verwenden Sie **\/DEBUGTYPE:PDATA** oder **\/DEBUGTYPE:CV,PDATA,FIXUP** zum Debuggen von Code, der Benutzermodus\- und Kernelmoduskomponenten kombiniert, beispielsweise eine Konfigurations\-App für einen Gerätetreiber.  Weitere Informationen über Kernelmodusdebugger finden Sie unter [Debugtools für Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## Siehe auch  
 [\/DEBUG \(Debuginfo generieren\)](../../build/reference/debug-generate-debug-info.md)   
 [\/DRIVER \(Treiber für den Kernelmodus von Windows NT\)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [\/PROFILE \(Leistungstools\-Profiler\)](../../build/reference/profile-performance-tools-profiler.md)   
 [Debugtools für Windows \(WinDbg, KD, CDB, NTSD\)](http://go.microsoft.com/fwlink/p?LinkID=285651)