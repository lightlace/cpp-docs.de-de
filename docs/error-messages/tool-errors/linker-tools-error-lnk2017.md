---
title: "Linkertoolfehler LNK2017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2017"
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK2017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol'\-Umsetzung zu 'Segment' ist ohne \/LARGEADDRESSAWARE:NO unzulässig  
  
 Sie versuchen, ein 64\-Bit\-Anwendung mit 32\-Bit\-Adressen zu erstellen.  Zu diesem Zweck verfahren Sie wie folgt:  
  
-   Verwenden Sie eine feste Adresse zum Laden.  
  
-   Beschränken Sie die Anwendung auf 3 GB.  
  
-   Geben Sie [\/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md) an.