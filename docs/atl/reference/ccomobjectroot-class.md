---
title: CComObjectRoot-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 4761aa9ae9c8ffacfb393311d7e058b1450b4628
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554971"
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

[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject-Klasse](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject-Klasse](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject-Klasse](../../atl/reference/ccompolyobject-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
