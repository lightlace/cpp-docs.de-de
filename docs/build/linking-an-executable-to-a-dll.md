---
title: "Verkn&#252;pfen einer ausf&#252;hrbaren Datei mit einer DLL | Microsoft Docs"
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
  - "DLLs [C++], Verknüpfen"
  - "Dynamisches Laden bzw. Verknüpfen [C++]"
  - "Ausführbare Dateien [C++], Verknüpfen mit DLLs"
  - "Explizite Verknüpfung [C++]"
  - "Implizite Verknüpfung [C++]"
  - "Verknüpfen [C++], DLLs"
  - "Laden von DLLs [C++]"
  - "Laufzeit [C++], Verknüpfen"
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Verkn&#252;pfen einer ausf&#252;hrbaren Datei mit einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine ausführbare Datei kann mit einer DLL durch eine der folgenden Methoden verknüpft werden \(bzw. diese laden\):  
  
-   [Implizites Verknüpfen](../build/linking-implicitly.md)  
  
-   [Explizites Verknüpfen](../build/linking-explicitly.md)  
  
 Das implizite Verknüpfen wird gelegentlich auch als statisches Laden oder dynamisches Verknüpfen zur Ladezeit bezeichnet.  Die explizite Verknüpfung wird gelegentlich auch als dynamisches Laden oder dynamisches Verknüpfen zur Laufzeit bezeichnet.  
  
 Bei der impliziten Verknüpfung wird die ausführbare Datei, die die DLL verwendet, mit einer Importbibliothek \(LIB\-Datei\) verknüpft, die vom Ersteller der DLL bereitgestellt wird.  Das Betriebssystem lädt die DLL zusammen mit der ausführbaren Datei.  Der ausführbare Client ruft die exportierten DLL\-Funktionen so auf, als ob sie innerhalb der ausführbaren Datei enthalten wären.  
  
 Bei der expliziten Verknüpfung muss die ausführbare Datei, die die DLL verwendet, Funktionsaufrufe durchführen, um die DLL explizit zu laden und zu entladen und um auf die exportierten Funktionen der DLL zuzugreifen.  Der ausführbare Client muss die exportierten Funktionen über einen Funktionszeiger aufrufen.  
  
 Eine ausführbare Datei kann für dieselbe DLL beide Verknüpfungsmethoden verwenden.  Darüber hinaus schließen diese Mechanismen sich nicht gegenseitig aus, sodass eine ausführbare Datei implizit mit einer DLL verknüpft und die andere explizit an die DLL angefügt werden kann.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Arbeiten mit Importbibliotheken und Exportdateien](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Bestimmen der geeigneten Verknüpfungsmethode](../build/determining-which-linking-method-to-use.md)  
  
-   [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)