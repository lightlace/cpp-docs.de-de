---
title: "Richtungsflag"
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
  - "c.flags"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Richtungskennzeichen"
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Richtungsflag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Richtungsflag ist ein CPU\-Flagbesondere Prozessoren Intel 80x86.  Es gilt für alle Assemblyanweisungen zu, die dem Präfix REP \(Wiederholung\), wie MOVS, MOVSD, MOVSW und andere verwenden.  Adressen haben zu den entsprechenden Anweisungen werden erhöht wird, wenn das Richtungsflag gelöscht wird.  
  
 Die C\-Laufzeit\-Routinen wird davon ausgegangen, dass das Richtungsflag gelöscht wird.  Wenn Sie andere Funktionen mit den C\-Laufzeitfunktionen verwenden, müssen Sie sicherstellen, dass die anderen Funktionen das Richtungsflag allein links oder es in seinem ursprünglichen Zustand wiederherstellen.  Die Erwartung des Richtungsflags, um nach Eintragung deaktivieren zu sein macht den Laufzeitcode schneller und effizienter.  
  
 Die C\-Laufzeitbibliothek, wie die Zeichenfolgenbearbeitungs\- und Puffermanipulationsroutinen, erwarten das Richtungsflag, um eindeutig sein.  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)