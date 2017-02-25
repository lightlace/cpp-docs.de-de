---
title: "Eingabestream-Manipulatoren | Microsoft Docs"
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
  - "Eingabestreamobjekte"
  - "Eingabestreams, Manipulatoren"
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Eingabestream-Manipulatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele Manipulatoren, wie [setprecision](../Topic/setprecision.md), werden für die `ios`\-Klasse definiert und betreffen daher auf Eingabestreams.  Wenige Manipulatoren jedoch tatsächlich Eingabestreamobjekte beeinflussen.  Von denen, die, der die wichtigsten Schritte, sind die Basismanipulatoren \-, `dec`\-, `oct`\- und `hex`, die die Konvertierungsbasis bestimmen, die mit Zahlen aus dem Eingabestream verwendet wird.  
  
 Auf Extraktion ermöglicht der `hex` Manipulator Verarbeitung von verschiedenen Eingabeformaten.  Beispielsweise werden c, C, 0xc, 0xC, 0Xc und alle 0XC als ganze Dezimalzahl 12 interpretiert.  Jedes Zeichen als 0 bis 9, A bis F, a bis f, X x und beendet die numerische Konvertierung.  Somit wird die Sequenz `"124n5"` die Zahl 124. mit der [basic\_ios::fail](../Topic/basic_ios::fail.md) Bitsatz konvertiert.  
  
## Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)