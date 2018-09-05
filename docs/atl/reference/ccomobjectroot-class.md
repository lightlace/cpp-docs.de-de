---
title: CComObjectRoot-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93d30c1af67159c04546076a07c78fbaec9cbb91
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762318"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot-Klasse

Diese Typdefinition der [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist auf dem standardmäßigen threading-Modell des Servers vorlagenbasiert.

## <a name="syntax"></a>Syntax

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>Hinweise

`CComObjectRoot` ist eine `typedef` von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) vorlagenbasiert, auf dem standardmäßigen threading-Modell des Servers. Daher [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) verweist entweder auf [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).

`CComObjectRootEx` verarbeitet die objektverwaltung Verweis Anzahl für aggregierte und zusammengesetzten Objekte. Sie enthält den Verweiszählerwert des Objekts, wenn das Objekt nicht aggregiert werden wird, und den Zeiger auf die äußere unbekannte enthält, wenn das Objekt aggregiert wird. Für aggregierte Objekte `CComObjectRootEx` Methoden können verwendet werden, um das innere Objekt zum Erstellen der Ausfall behandelt, und schützen das äußere Objekt vor dem Löschen, wenn interne Schnittstellen freigegeben werden oder das innere Objekt gelöscht wird.

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

## <a name="see-also"></a>Siehe auch

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)   
[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)   
[CComObject-Klasse](../../atl/reference/ccomobject-class.md)   
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
