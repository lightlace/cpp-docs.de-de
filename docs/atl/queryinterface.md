---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 28f3781706981b06d49829c0277014c09574ef6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250353"
---
# <a name="queryinterface"></a>QueryInterface

Es gibt, aber Mechanismen mit dem express ein Objekt kann die Funktionalität bietet statisch (vor er instanziiert wird) der grundlegende Mechanismus für die COM-ist die Verwendung der `IUnknown` aufgerufene Methode [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Jede Schnittstelle stammt aus `IUnknown`, sodass jede Schnittstelle keine Implementierung von besitzt `QueryInterface`. Unabhängig von der Implementierung fragt diese Methode ein Objekt mit die IID der Schnittstelle, die vom Aufrufer eines Zeigers, auf. Wenn das Objekt über die Schnittstelle unterstützt `QueryInterface` ruft Sie einen Zeiger auf die Schnittstelle, bei gleichzeitigem Aufrufen `AddRef`. Andernfalls wird den Fehlercode E_NOINTERFACE zurückgegeben.

Beachten Sie, die Sie bei der standardeinhaltung [Verweiszählung](../atl/reference-counting.md) Regeln immer. Wenn Sie aufrufen `Release` auf einen Schnittstellenzeiger, den Verweiszähler auf 0 (null) dekrementiert werden soll, verwenden Sie nicht diesen Zeiger erneut aus. Gelegentlich müssen Sie möglicherweise einen schwachen Verweis auf ein Objekt zu erhalten (d. h. möglicherweise möchten Sie einen Zeiger auf eine der Schnittstellen abzurufen, ohne den Verweiszähler zu inkrementieren), aber es ist nicht zulässig, durch den Aufruf dazu `QueryInterface` gefolgt von `Release`. Der Zeiger auf diese Weise erhalten ist ungültig und sollte nicht verwendet werden. Dadurch wird schneller deutlich Wenn [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) definiert ist, ist dieses Makro definieren eine gute Möglichkeit für das Zählen von Fehlern suchen von verweisen.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: Navigieren in einem Objekt](/windows/desktop/com/queryinterface--navigating-in-an-object)
