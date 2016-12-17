---
title: "In der regul&#228;ren DLL tritt ein Speicherverlust auf, der Code scheint jedoch einwandfrei zu sein. Wie kann der Arbeitsspeicherverlust ermittelt werden?"
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
  - "DLLs [C++], Speicherverluste"
  - "Speicherverluste [C++], DLLs"
ms.assetid: a5d76573-b567-4b6a-8303-dafeeed9204d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# In der regul&#228;ren DLL tritt ein Speicherverlust auf, der Code scheint jedoch einwandfrei zu sein. Wie kann der Arbeitsspeicherverlust ermittelt werden?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Grund für den Speicherverlust liegt möglicherweise darin, dass MFC temporäre Objekte erstellt, die innerhalb von Meldungshandlerfunktionen verwendet werden.  In regulären DLLs gibt MFC den für diese Objekte belegten Speicher nicht automatisch wieder frei.  Weitere Informationen finden Sie unter [Speicherverwaltung und Debugheap](assetId:///34dc6ef6-31c9-460e-a2a7-15e7f8e3334b) oder im Knowledge Base\-Artikel "Cleaning Up Temporary MFC Objects in \_USRDLL DLLs" \(Q105286, nur auf Englisch verfügbar\).  
  
 Beachten Sie, dass der Begriff "USRDLL" in der Visual C\+\+\-Dokumentation nicht mehr verwendet wird.  Eine reguläre DLL, die statisch mit MFC verknüpft ist, hat dieselben Merkmale wie die frühere USRDLL.  Die Empfehlung im Knowledge Base\-Artikel bezieht sich auch auf reguläre DLLs, die dynamisch mit MFC verknüpft sind.  Die Informationen im oben genannten Knowledge Base\-Artikel beziehen sich sowohl auf reguläre DLLs, die statisch mit MFC verknüpft sind, als auch auf reguläre DLLs, die dynamisch mit MFC verknüpft sind.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zu DLLs](../build/dll-frequently-asked-questions.md)