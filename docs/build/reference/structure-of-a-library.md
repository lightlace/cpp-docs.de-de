---
title: "Struktur einer Bibliothek | Microsoft Docs"
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
  - "Bibliotheken, Struktur"
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Struktur einer Bibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Bibliothek enthält COFF\-Objekte.  Diese Bibliotheksobjekte umfassen Funktionen und Daten, auf die extern durch andere Objekte in einem Programm verwiesen werden kann.  Ein Bibliotheksobjekt wird auch als Bibliothekmember bezeichnet.  
  
 Zusätzliche Informationen über den Inhalt einer Bibliothek erhalten Sie, indem Sie das Tool DUMPBIN mit der **\/LINKERMEMBER**\-Option ausführen.  Weitere Informationen über diese Option erhalten Sie in der [DUMPBIN\-Referenz](../../build/reference/dumpbin-reference.md).  
  
## Siehe auch  
 [Übersicht über LIB](../../build/reference/overview-of-lib.md)