---
title: "Konsistenzregeln f&#252;r vorkompilierte Header | Microsoft Docs"
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
  - "Vorkompilierte Headerdateien, Konsistenzregeln"
ms.assetid: 844b1a14-5b0b-4276-a1f5-cc62f13f6dda
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Konsistenzregeln f&#252;r vorkompilierte Header
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt werden Richtlinien vorgestellt, die Ihnen die effizientere Verwendung von vorkompilierten Headern ermöglichen:  
  
-   [Konsistenzregeln zur Verwendung einer vorkompilierten Headerdatei](../../build/reference/consistency-rules-for-per-file-use-of-precompiled-headers.md)  
  
-   [Konsistenzregeln für "\/Yc" und "\/Yu"](../../build/reference/consistency-rules-for-yc-and-yu.md)  
  
 Da PCH\-Dateien Informationen über die Computerumgebung und Speicheradressinformationen über das Programm enthalten, sollten Sie eine PCH\-Datei nur auf dem Computer verwenden, auf dem sie erstellt wurde.  
  
## Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)