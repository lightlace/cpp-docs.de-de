---
title: ATL-Auflistungen und -Enumeratorklassen
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: b1ab9a160b01ea278d162a515e5121054bf398f7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265404"
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL-Auflistungen und -Enumeratorklassen

ATL bietet die folgenden Klassen zum Implementieren von Auflistungen und-Enumerationen beitragen.

|Klasse|Beschreibung|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Collection-schnittstellenimplementierung|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Enumerator-schnittstellenimplementierung, die (geht davon aus, in einem C++-Standard-Bibliothek-kompatible Container gespeicherte Daten)|
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Enumerator-schnittstellenimplementierung, die (geht davon aus, in einem Array gespeicherte Daten)|
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Enumerator-Objekt-Implementierung (verwendet `IEnumOnSTLImpl`)|
|[CComEnum](../atl/reference/ccomenum-class.md)|Enumerator-Objekt-Implementierung (verwendet `CComEnumImpl`)|
|[_Copy](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|
|[CAdapt](../atl/reference/cadapt-class.md)|Klasse des Adapters (blendet **Operator &** ermöglicht `CComPtr`, `CComQIPtr`, und `CComBSTR` in C++-standardbibliothekscontainer gespeichert werden)|

## <a name="see-also"></a>Siehe auch

[Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)
