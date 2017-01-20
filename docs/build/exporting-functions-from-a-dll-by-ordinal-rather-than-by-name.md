---
title: "Exportieren von Funktionen aus einer DLL &#252;ber die Ordnungszahl statt &#252;ber den Namen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "NONAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exportieren von DLLs [C++], Ordinalwerte"
  - "Exportieren von Funktionen [C++], Ordinalwerte"
  - "NONAME-Attribut"
  - "Ordnungszahlenexporte [C++]"
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Exportieren von Funktionen aus einer DLL &#252;ber die Ordnungszahl statt &#252;ber den Namen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Am einfachsten können Funktionen anhand des Namens aus einer DLL exportiert werden.  Dies ist beispielsweise bei Verwendung von **\_\_declspec\(dllexport\)** der Fall.  Funktionen können jedoch auch über die Ordinalzahl exportiert werden.  Bei diesem Verfahren verwenden Sie anstelle von **\_\_declspec\(dllexport\)** eine DEF\-Datei.  Um den Ordinalwert einer Funktion anzugeben, fügen Sie die betreffende Ordinalzahl in der DEF\-Datei an den Funktionsnamen an.  Informationen über das Festlegen von Ordinalzahlen finden Sie unter [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md).  
  
> [!TIP]
>  Um die Größe der DLL\-Datei zu optimieren, verwenden Sie für jede exportierte Funktion das **NONAME**\-Attribut.  Bei Verwendung des **NONAME**\-Attributs werden lediglich die Ordinalzahlen in der Exporttabelle der DLL gespeichert und nicht die Funktionsnamen.  Diese Vorgehensweise ist insbesondere beim Exportieren zahlreicher Funktionen äußerst platzsparend.  
  
## Was möchten Sie tun?  
  
-   [Mithilfe von DEF\-Dateien aus einer DLL exportieren](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Mithilfe von "\_\_declspec\(dllexport\)" aus einer DLL exportieren](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)