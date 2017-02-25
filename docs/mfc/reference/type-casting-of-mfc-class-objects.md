---
title: "Typumwandlung von MFC-Klassenobjekten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umwandlungstypen"
  - "Makros, Umwandlungszeiger"
  - "Makros, Typumwandlung"
  - "Zeiger, Typumwandlung"
  - "Typumwandlungen"
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Typumwandlung von MFC-Klassenobjekten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typumwandlungsmakros bieten eine Möglichkeit, einen angegebenen Zeiger auf einen Zeiger umwandeln, der auf ein Objekt der speziellen Klasse, mit oder ohne Überprüfung, die die Umwandlung gültig ist.  
  
 Die folgende Tabelle zeigt die MFC\-Typumwandlungsmakros auf.  
  
### Makros, die Zeiger der MFC\-Klasse umwandeln, \- Objekten  
  
|||  
|-|-|  
|[DYNAMIC\_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|Wandelt einen Zeiger auf einen Zeiger auf ein Klassenobjekt beim Überprüfen, um festzustellen um, wenn die Umwandlung gültig ist.|  
|[STATIC\_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|Wandelt einen Zeiger auf ein Objekt aus einer Klasse in einen Zeiger eines zugehörigen Typ um.  In einem Debugbuild Ursachen **ASSERT**, wenn das Objekt keine "Art" Zieltyp ist.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)