---
title: nonextensible-Attribut
ms.date: 11/04/2016
f1_keywords:
- nonextensible
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: 5aa5b8514435e9876500daa4d92504d75eb6dc23
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257630"
---
# <a name="nonextensible-attribute"></a>nonextensible-Attribut

Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird (d. h. Sie wird nicht angeben, Methoden oder Eigenschaften über `IDispatch::Invoke` , die nicht über die Vtable verfügbar sind), gelten die **nonextensible** Attribut zu Ihrer Schnittstelle die Definition. Dieses Attribut stellt die Informationen zur Clientsprachen (z. B. Visual Basic), die zum Aktivieren der Überprüfung der vollständigen Code zum Zeitpunkt der Kompilierung verwendet werden kann. Wenn dieses Attribut nicht angegeben wird, möglicherweise Fehler im Clientcode bleiben bis zur Laufzeit ausgeblendet.

Weitere Informationen zu den **nonextensible** -Attribut und ein Beispiel finden Sie unter [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)
