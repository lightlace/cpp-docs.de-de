---
title: "abort-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort-Funktion"
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# abort-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Funktion **abort**, welche auch in der Standardincludedatei STDLIB.H deklariert wird, beendet ein C\+\+\-Programm.  Der Unterschied zwischen **exit** und **abort** besteht darin, dass **exit** C\+\+ die Laufzeitbeendigung zulässt, \(globale Objektdestruktoren werden aufgerufen\), während **abort** das Programm sofort beendet.  Weitere Informationen finden Sie unter [abort](../c-runtime-library/reference/abort.md) in der *Laufzeitbibliotheksreferenz*.  
  
## Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)