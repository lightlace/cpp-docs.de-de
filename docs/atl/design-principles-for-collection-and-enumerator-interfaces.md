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
ms.openlocfilehash: 40aa94226b93a42b14dfd23a64e12fff00e22729
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Entwurfsprinzipien für Sammlung und den Enumerator-Schnittstellen
Es gibt verschiedene Entwurfsprinzipien für jeden Typ der Schnittstelle:  
  
-   Stellt eine sammlungsschnittstelle *zufällige* Zugriff auf eine *einzelne* Element in der Auflistung über die **Element** -Methode, können Sie ermitteln, wie viele Elemente in der Auflistung werden Clients über die **Anzahl** -Eigenschaft, und oft ermöglicht es Clients, hinzufügen und Entfernen von Elementen.  
  
-   Stellt eine Enumeratorschnittstelle *serielle* Zugriff auf *mehrere* Elemente in einer Auflistung, es kann keine des Clients zu ermitteln, wie viele Elemente in der Sammlung befinden (bis der Enumerator zurückgeben beendet Elemente), und es bietet keine Möglichkeit zum Hinzufügen oder Entfernen von Elementen.  
  
 Jeder Typ der Schnittstelle spielt eine andere Rolle Zugriff auf die Elemente in einer Sammlung bereitstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)

