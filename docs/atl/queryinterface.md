---
title: QueryInterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14ebef3649cea78e8cf4315a62392cfa142152
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="queryinterface"></a>QueryInterface
Es gibt, zwar Mechanismen, die mit dem express ein Objekt kann die Funktionalität bietet statisch (vor er instanziiert wird) der grundlegende Mechanismus von COM ist die Verwendung der **IUnknown** Methode mit dem Namen [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Jede Schnittstelle abgeleitet **IUnknown**, sodass jede Schnittstelle eine Implementierung von `QueryInterface`. Unabhängig von der Implementierung fragt diese Methode ein Objekt, das über die IID der Schnittstelle, die vom Aufrufer eines Zeigers. Wenn das Objekt über diese Schnittstelle unterstützt `QueryInterface` Ruft einen Zeiger auf die Schnittstelle, während des Aufrufs auch `AddRef`. Andernfalls gibt es die **E_NOINTERFACE** Fehlercode.  
  
 Beachten Sie, die Sie befolgen müssen [Verweiszählung](../atl/reference-counting.md) Regeln jederzeit. Beim Aufrufen **Version** auf einen Schnittstellenzeiger dekrementiert den Verweiszähler auf 0 (null), sollten Sie keine verwenden diesen Zeiger erneut aus. Gelegentlich müssen Sie möglicherweise einen schwachen Verweis auf ein Objekt zu erhalten (d. h., möglicherweise möchten Sie einen Zeiger auf eine der Schnittstellen zu erhalten, ohne den Verweiszähler zu inkrementieren), aber es ist nicht zulässig hierfür durch Aufrufen von `QueryInterface` gefolgt von  **Version**. Der Zeiger auf solche Weise abgerufen ist ungültig und sollte nicht verwendet werden. Dadurch wird schneller deutlich Wenn [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) definiert ist, damit diese Makros definieren eine hilfreiche Möglichkeit suchen, verweiszählung Fehler ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigieren in einem Objekt](http://msdn.microsoft.com/library/windows/desktop/ms687230)

