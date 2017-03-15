---
title: "Vorteile der Zeichensatzportabilit&#228;t | Microsoft Docs"
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
  - "Zeichensätze [C++], Vorteile"
  - "Portabilität [C++], Zeichensätze"
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Vorteile der Zeichensatzportabilit&#228;t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie profitieren selbst dann von der Verwendung der MFC\-Features und der C\-Laufzeitportabilität, wenn Sie die Anwendung derzeit nicht internationalisieren möchten:  
  
-   Portables Codieren verleiht der CodeBase mehr Flexibilität.  Sie können sie zu einem späteren Zeitpunkt problemlos in Unicode oder MBCS übertragen.  
  
-   Durch die Verwendung von Unicode wird die Effizienz einer Anwendungen für Windows 2000 gesteigert.  Da in Windows 2000 Unicode verwendet wird, müssen alle an das Betriebssystem bzw. vom Betriebssystem übergebenen Zeichenfolgen, die nicht in Unicode codiert sind, übersetzt werden, was Mehraufwand bedeutet.  
  
-   Mit MBCS ist die Unterstützung internationaler Märkte auf anderen Win32\-Plattformen als Windows 2000 möglich, z. B. Windows 95 oder Windows 98.  
  
## Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Unterstützung für Unicode](../text/support-for-unicode.md)