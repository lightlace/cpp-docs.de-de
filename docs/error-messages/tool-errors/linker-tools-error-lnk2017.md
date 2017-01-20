---
title: "Linkertoolfehler LNK2017"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2017"
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol'\-Umsetzung zu 'Segment' ist ohne \/LARGEADDRESSAWARE:NO unzulässig  
  
 Sie versuchen, ein 64\-Bit\-Anwendung mit 32\-Bit\-Adressen zu erstellen.  Zu diesem Zweck verfahren Sie wie folgt:  
  
-   Verwenden Sie eine feste Adresse zum Laden.  
  
-   Beschränken Sie die Anwendung auf 3 GB.  
  
-   Geben Sie [\/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md) an.