---
title: ATL-Auflistungen und -Enumeratorklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0ff5fec4749e08826bab5572149c6cd24a204f9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765072"
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
|["_Copy"](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Kopieren Sie die Policy-Klasse|
|[CAdapt](../atl/reference/cadapt-class.md)|Klasse des Adapters (blendet **Operator &** ermöglicht `CComPtr`, `CComQIPtr`, und `CComBSTR` in C++-standardbibliothekscontainer gespeichert werden)|

## <a name="see-also"></a>Siehe auch

[Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)

