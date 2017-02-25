---
title: "Systemaufrufe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.system"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systemaufrufe"
  - "Windows [C++], Systemaufrufe"
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Systemaufrufe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Funktionen sind Windows\-Betriebssystemaufrufe.  
  
### System\-Aufrufs\-Funktionen  
  
|Funktion|Verwendung|.NET Framework\-Entsprechung|  
|--------------|----------------|----------------------------------|  
|[\_findclose](../c-runtime-library/reference/findclose.md)|Freigeben der verwendeten Ressourcen aus vorangegangenen Suchvorgängen|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_findfirst, \_findfirst32, \_findfirst64, \_findfirsti64, \_findfirst32I64, \_findfirst64I32, \_wfindfirst, \_wfindfirst32, \_wfindfirst64, \_wfindfirsti64, \_wfindfirst32I64, \_wfindfirst64I32](../c-runtime-library/reference/findfirst-functions.md)|Suchendatei mit angegebenen Attribute|[\<caps:sentence id\="tgt12" sentenceid\="e22cfa910fbeac637b6aba4ed3f9dc48" class\="tgtSentence"\>System::IO::DirectoryInfo::GetFiles\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.getfiles.aspx)|  
|[\_findnext, \_findnext32, \_findnext64, \_findnexti64, \_findnext32I64, \_findnext64I32, \_wfindnext, \_wfindnext32, \_wfindnexti64, \_wfindnext64, \_wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|Nachfolgende Datei der Suche mit angegebenen Attribute|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Dateibehandlung](../c-runtime-library/file-handling.md)   
 [Verzeichnissteuerung](../c-runtime-library/directory-control.md)   
 [E\/A auf niedriger Ebene](../c-runtime-library/low-level-i-o.md)