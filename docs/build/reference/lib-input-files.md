---
title: "LIB-Eingabedateien"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eingabedateien, LIB"
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# LIB-Eingabedateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die von LIB erwarteten Eingabedateien hängen von dem Modus ab, in dem das Programm verwendet wird \(siehe nachfolgende Tabelle\).  
  
|Modus|Eingabe|  
|-----------|-------------|  
|Standard \(Erstellen oder Ändern einer Bibliothek\)|COFF\-Objektdateien \(**.obj**\), COFF\-Bibliotheken \(**.lib**\), Objektdateien \(**.obj**\) im 32\-Bit\-OMF\-Format \(Object Model Format\)|  
|Extrahieren eines Members mit **\/EXTRACT**|COFF\-Bibliothek \(**.lib**\)|  
|Erstellen einer Exportdatei und Importbibliothek mit **\/DEF**|Moduldefinitionsdatei \(**.def**\), COFF\-Objektdateien \(**.obj**\), COFF\-Bibliotheken \(**.lib**\), Objektdateien \(**.obj**\) im 32\-Bit\-OMF\-Format \(Object Model Format\)|  
  
> [!NOTE]
>  OMF\-Bibliotheken, die mit der 16\-Bit\-Version von LIB erstellt wurden, können nicht als Eingabe für die 32\-Bit\-Version von LIB verwendet werden.  
  
## Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)