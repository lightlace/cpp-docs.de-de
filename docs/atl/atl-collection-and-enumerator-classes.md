---
title: ATL-Klassen zum Erfassen und Enumerator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b172c0d3a6f453ec0d5f7b5bb3584ebf2f5140e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL-Auflistung und Enumerator-Klassen
ATL stellt die folgenden Klassen zum Auflistungen und-Enumerationen implementieren.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Collection-Implementierung|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Enumerator-Implementierung (geht davon aus Daten, die in einem C++-Standard-Bibliothek-kompatiblen Container gespeichert.)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Enumerator-Implementierung (geht davon aus in einem Array gespeicherten Daten)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Enumerator-Objekt-Implementierung (verwendet `IEnumOnSTLImpl`)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Enumerator-Objekt-Implementierung (verwendet `CComEnumImpl`)|  
|["_Copy"](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|  
|[CAdapt](../atl/reference/cadapt-class.md)|Adapterklasse (blendet **Operator &** ermöglicht `CComPtr`, `CComQIPtr`, und `CComBSTR` in C++-Standardbibliothek Containern gespeichert werden)|  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)

