---
title: "Design Principles for Collection and Enumerator Interfaces | Microsoft Docs"
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
  - "collection interfaces"
  - "enumerator interfaces"
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Design Principles for Collection and Enumerator Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt verschiedene Entwurfsprinzipien hinter jedem Typ Schnittstelle:  
  
-   Eine Auflistungsschnittstelle stellt *wahlfreien Zugriff* auf ein *einzelnes*\-Element in der Auflistung über die **Item** Möglichkeit, können sie Client ermitteln, wie viele Elemente in der Auflistung über die **Count**\-Eigenschaft sind, und können häufig Client, um Elemente hinzuzufügen und zu entfernen.  
  
-   Eine Enumeratorschnittstelle bietet *seriellen* Zugriff auf *mehrere* Elemente in einer Auflistung, sie erlaubt dem Client nicht, zu ermitteln, wie viele Elemente in der Auflistung sind \(bis der Enumerator aufhört, Elemente zurückzugeben\), und sie stellt keine Methode zum Hinzufügen oder Entfernen von Elementen bereit.  
  
 Jeder Typ Schnittstelle gibt eine andere Rolle erneut, wenn er den Zugriff auf die Elemente einer Auflistung bietet.  
  
## Siehe auch  
 [Auflistungen und Enumerationen](../atl/atl-collections-and-enumerators.md)