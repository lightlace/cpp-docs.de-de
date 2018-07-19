---
title: Entwerfen von Auflistungs- und Enumeratorschnittstellen (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab8b42804ca892c80971928b869e09ccdf479d68
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851326"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Entwurfsprinzipien für Auflistungs- und Enumeratorschnittstellen
Es gibt verschiedene Entwurfsprinzipien für jede Art von Schnittstelle:  
  
-   Stellt eine sammlungsschnittstelle *zufällige* Zugriff auf eine *einzelne* Element in der Auflistung über die `Item` -Methode, sie können Clients zu ermitteln, wie viele Elemente in der Auflistung über sind die `Count` Eigenschaft, und häufig ermöglicht Clients, Elemente hinzufügen und entfernen.  
  
-   Eine Enumeratorschnittstelle bereitstellt, *seriellen* Zugriff auf *mehrere* Elemente in einer Auflistung, es keine ermöglichen dem Client zu ermitteln, wie viele Elemente in der Auflistung sind (bis der Enumerator zurückgeben wird beendet. Elemente), und es bietet keine Möglichkeit zum Hinzufügen oder Entfernen von Elementen.  
  
 Jede Art von Schnittstelle spielt eine andere Rolle bei der Bereitstellung Zugriff auf die Elemente in einer Auflistung.  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)

