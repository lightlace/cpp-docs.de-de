---
title: "Von Windows verwendeter Suchpfad zum Auffinden einer DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Windows-Suchpfad"
  - "Suchen von DLLs"
  - "Bekannte DLL-Suchen [C++]"
  - "Suchen von DLLs"
  - "Suchpfade [C++]"
  - "Suchen [C++], DLLs"
  - "Windows [C++], DLL-Suchpfad"
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Von Windows verwendeter Suchpfad zum Auffinden einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sowohl bei der impliziten als auch bei der expliziten Verknüpfung, sucht Windows zuerst nach "bekannten DLLs", z. B. Kernel32.dll und User32.dll.  Danach werden die DLLs von Windows in der folgenden Reihenfolge gesucht:  
  
1.  Das Verzeichnis, in dem sich das ausführbare Modul des aktuellen Prozesses befindet.  
  
2.  Das aktuelle Verzeichnis.  
  
3.  Das Systemverzeichnis von Windows.  Der Pfad für dieses Verzeichnis wird durch die **GetSystemDirectory**\-Funktion abgerufen.  
  
4.  Das Windows\-Verzeichnis.  Der Pfad für dieses Verzeichnis wird durch die **GetWindowsDirectory**\-Funktion abgerufen.  
  
5.  Die in der **PATH**\-Umgebungsvariablen aufgeführten Verzeichnisse.  
  
    > [!NOTE]
    >  Die LIBPATH\-Umgebungsvariable wird nicht verwendet.  
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Explizite Verknüpfungen verwenden](../build/linking-explicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)