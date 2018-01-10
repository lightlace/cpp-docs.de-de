---
title: Entwerfen von Auflistung und Enumerator-Schnittstellen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8709274e1b95816dee01b4457993521dde5d5213
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Entwurfsprinzipien für Sammlung und den Enumerator-Schnittstellen
Es gibt verschiedene Entwurfsprinzipien für jeden Typ der Schnittstelle:  
  
-   Stellt eine sammlungsschnittstelle *zufällige* Zugriff auf eine *einzelne* Element in der Auflistung über die **Element** -Methode, können Sie ermitteln, wie viele Elemente in der Auflistung werden Clients über die **Anzahl** -Eigenschaft, und oft ermöglicht es Clients, hinzufügen und Entfernen von Elementen.  
  
-   Stellt eine Enumeratorschnittstelle *serielle* Zugriff auf *mehrere* Elemente in einer Auflistung, es kann keine des Clients zu ermitteln, wie viele Elemente in der Sammlung befinden (bis der Enumerator zurückgeben beendet Elemente), und es bietet keine Möglichkeit zum Hinzufügen oder Entfernen von Elementen.  
  
 Jeder Typ der Schnittstelle spielt eine andere Rolle Zugriff auf die Elemente in einer Sammlung bereitstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)

