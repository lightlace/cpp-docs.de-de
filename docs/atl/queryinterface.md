---
title: QueryInterface | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3227ebd4767bd7639bb5e5d8d5a1c73e26079dc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953420"
---
# <a name="queryinterface"></a>QueryInterface
Es gibt, aber Mechanismen mit dem express ein Objekt kann die Funktionalität bietet statisch (vor er instanziiert wird) der grundlegende Mechanismus für die COM-ist die Verwendung der `IUnknown` aufgerufene Methode [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Jede Schnittstelle stammt aus `IUnknown`, sodass jede Schnittstelle keine Implementierung von besitzt `QueryInterface`. Unabhängig von der Implementierung fragt diese Methode ein Objekt mit die IID der Schnittstelle, die vom Aufrufer eines Zeigers, auf. Wenn das Objekt über die Schnittstelle unterstützt `QueryInterface` ruft Sie einen Zeiger auf die Schnittstelle, bei gleichzeitigem Aufrufen `AddRef`. Andernfalls wird den Fehlercode E_NOINTERFACE zurückgegeben.  
  
 Beachten Sie, die Sie bei der standardeinhaltung [Verweiszählung](../atl/reference-counting.md) Regeln immer. Wenn Sie aufrufen `Release` auf einen Schnittstellenzeiger, den Verweiszähler auf 0 (null) dekrementiert werden soll, verwenden Sie nicht diesen Zeiger erneut aus. Gelegentlich müssen Sie möglicherweise einen schwachen Verweis auf ein Objekt zu erhalten (d. h. möglicherweise möchten Sie einen Zeiger auf eine der Schnittstellen abzurufen, ohne den Verweiszähler zu inkrementieren), aber es ist nicht zulässig, durch den Aufruf dazu `QueryInterface` gefolgt von `Release`. Der Zeiger auf diese Weise erhalten ist ungültig und sollte nicht verwendet werden. Dadurch wird schneller deutlich Wenn [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) definiert ist, ist dieses Makro definieren eine gute Möglichkeit für das Zählen von Fehlern suchen von verweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [QueryInterface: Navigieren in einem Objekt](http://msdn.microsoft.com/library/windows/desktop/ms687230)

