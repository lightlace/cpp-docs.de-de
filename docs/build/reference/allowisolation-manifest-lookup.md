---
title: "/ALLOWISOLATION (Manifestsuche) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ALLOWISOLATION"
  - "VC.Project.VCLinkerTool.AllowIsolation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION (Linkeroption)"
  - "-ALLOWISOLATION (Linkeroption)"
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /ALLOWISOLATION (Manifestsuche)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Verhalten bei der Manifestsuche an.  
  
## Syntax  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## Hinweise  
 Durch **\/ALLOWISOLATION:NO** werden DLLs ohne Manifest geladen, und vom Linker wird im optionalen `DllCharacteristics`\-Feld des Headers das `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION`\-Bit festgelegt.  
  
 **\/ALLOWISOLATION** führt dazu, dass das Betriebssystem nach Manifesten sucht und diese lädt.  
  
 Standardmäßig ist **\/ALLOWISOLATION** festgelegt.  
  
 Wenn für eine ausführbare Datei die Isolation deaktiviert ist, wird vom Windows\-Ladeprogramm für den neu erstellten Prozess nicht nach einem Anwendungsmanifest gesucht.  Der neue Prozess hat keine Standardaktivierungskontext, selbst wenn ein Manifest in der ausführbaren Datei oder in demselben Verzeichnis wie die ausführbare Datei mit Namen *executable\-name***.exe.manifest** platziert wird.  
  
 Weitere Informationen finden Sie in [Manifestdateien\-Verweis](http://msdn.microsoft.com/library/aa375632).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Manifestdatei** aus.  
  
5.  Ändern Sie die Eigenschaft **Isolation zulassen**.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)