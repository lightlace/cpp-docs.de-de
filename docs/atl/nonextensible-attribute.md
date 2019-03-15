---
title: nonextensible-Attribut
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: cc57acb8bd7bc3e32c764606da651f57316ceabf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811848"
---
# <a name="nonextensible-attribute"></a>nonextensible-Attribut

Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird (d. h. Sie wird nicht angeben, Methoden oder Eigenschaften über `IDispatch::Invoke` , die nicht über die Vtable verfügbar sind), gelten die **nonextensible** Attribut zu Ihrer Schnittstelle die Definition. Dieses Attribut stellt die Informationen zur Clientsprachen (z. B. Visual Basic), die zum Aktivieren der Überprüfung der vollständigen Code zum Zeitpunkt der Kompilierung verwendet werden kann. Wenn dieses Attribut nicht angegeben wird, möglicherweise Fehler im Clientcode bleiben bis zur Laufzeit ausgeblendet.

Weitere Informationen zu den **nonextensible** -Attribut und ein Beispiel finden Sie unter [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)
