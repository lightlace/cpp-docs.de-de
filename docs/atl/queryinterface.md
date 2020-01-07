---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 37bb7a8c7fef963f340704561e24e33cc36707f3
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298635"
---
# <a name="queryinterface"></a>QueryInterface

Obwohl es Mechanismen gibt, mit denen ein Objekt die Funktionalität Ausdrücken kann, die es statisch bereitstellt (vor der instanziierten), besteht der grundlegende com-Mechanismus darin, die `IUnknown` Methode namens [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))zu verwenden.

Jede Schnittstelle wird von `IUnknown`abgeleitet, sodass jede Schnittstelle über eine Implementierung von `QueryInterface`verfügt. Unabhängig von der Implementierung fragt diese Methode ein Objekt mithilfe der IID der Schnittstelle ab, zu der der Aufrufer einen Zeiger wünscht. Wenn das-Objekt diese Schnittstelle unterstützt, ruft `QueryInterface` einen Zeiger auf die-Schnittstelle ab, während gleichzeitig `AddRef`aufgerufen wird. Andernfalls wird der E_NOINTERFACE Fehlercode zurückgegeben.

Beachten Sie, dass Sie immer die [Verweis zählungs](../atl/reference-counting.md) Regeln befolgen müssen. Wenn Sie `Release` in einem Schnittstellen Zeiger aufzurufen, um den Verweis Zähler auf 0 (null) zu verringern, sollten Sie diesen Zeiger nicht erneut verwenden. Gelegentlich müssen Sie möglicherweise einen schwachen Verweis auf ein Objekt abrufen (d. h., Sie möchten einen Zeiger auf eine der Schnittstellen abrufen, ohne den Verweis Zähler zu erhöhen). Dies ist jedoch nicht akzeptabel, indem Sie `QueryInterface` gefolgt von `Release`aufrufen. Der in einer solchen Weise erhaltene Zeiger ist ungültig und sollte nicht verwendet werden. Dies wird leichter ersichtlich, wenn [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) definiert ist. Daher ist das definieren dieses Makros eine hilfreiche Möglichkeit, um Verweis Zählfehler zu finden.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: Navigieren in einem Objekt](/windows/win32/com/queryinterface--navigating-in-an-object)
