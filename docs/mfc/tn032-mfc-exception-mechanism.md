---
title: "TN032: MFC-Ausnahmemechanismus"
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
  - "vc.mfc.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CException-Klasse, Verwenden"
  - "MFC, Ausnahmen"
  - "TN032"
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# TN032: MFC-Ausnahmemechanismus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In älteren Versionen von Visual C\+\+ unterstützt nicht den Standardc\+\+\-ausnahme\-Mechanismus und die MFC bereitgestellten Makros **TRY\/CATCH\/THROW** stattdessen, die verwendet wurden.  Diese Version von Visual C\+\+ unterstützt vollständig C\+\+\-Ausnahmen.  Dieser Hinweis wurden einige der erweiterten Implementierungsdetails der vorherigen Makros einschließlich ab, wie automatisch Stapel abfragebasierte Objekte bereinigt.  Da C\+\+\-Ausnahmen Stapelentladung standardmäßig unterstützen, ist dieser technische Hinweis nicht mehr erforderlich.  
  
 Siehe [Ausnahmen: Verwenden MFC\-Makros und C\+\+\-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) weitere Informationen über die Unterschiede zwischen den MFC\-Makros und den neuen C\+\+\-Schlüsselworten.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)