---
title: "Sichern von verz&#246;gert geladenen Importen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verzögert geladene Importe"
  - "Verzögert geladene Importe, Dumperstellung"
  - "Verzögert geladene Importe"
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Sichern von verz&#246;gert geladenen Importen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verzögert geladene Importe können mit [dumpbin \/imports](../../build/reference/imports-dumpbin.md) gesichert werden, wobei sich die Informationen geringfügig von Standardimporten unterscheiden.  Sie bilden einen eigenen Abschnitt der **\/imports**\-Sicherung und werden explizit als verzögert geladene Importe gekennzeichnet.  Wenn das Abbild Entladeinformationen enthält, wird dies vermerkt.  Wenn Bindungsinformationen vorhanden sind, werden die Datums\- und die Zeitangabe der Ziel\-DLL zusammen mit den gebundenen Adressen des Imports vermerkt.  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)