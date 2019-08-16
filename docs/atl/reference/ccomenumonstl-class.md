---
title: CComEnumOnSTL-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
ms.openlocfilehash: ab11ea5e5347c9c8684e8710e9742fdbcad8a46b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497165"
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL-Klasse

Diese Klasse definiert ein com-Enumeratorobjekt, das C++ auf einer Standard Bibliothekssammlung basiert.

## <a name="syntax"></a>Syntax

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
T,
    Copy,
CollType>,
    public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parameter

*Sock*<br/>
Ein com-Enumerator. Ein Beispiel finden Sie unter " [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) ".

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, das von der Enumeratorschnittstelle verfügbar gemacht wird.

*Kopieren*<br/>
Eine [Kopier Richtlinien](../../atl/atl-copy-policy-classes.md) Klasse.

*Colltype*<br/>
Eine C++ Container Klasse der Standard Bibliothek.

## <a name="remarks"></a>Hinweise

`CComEnumOnSTL`definiert ein com-Enumeratorobjekt, das C++ auf einer Standard Bibliotheks Auflistung basiert. Diese Klasse kann eigenständig oder in Verbindung mit [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)verwendet werden. Im folgenden werden typische Schritte zum Verwenden dieser Klasse beschrieben. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumeratoren](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class-with-icollectiononstlimpl"></a>So verwenden Sie diese Klasse mit ICollectionOnSTLImpl:

- **typedef** eine Spezialisierung dieser Klasse.

- Verwenden Sie die **typedef** als endgültiges Vorlagen Argument in einer Spezialisierung von `ICollectionOnSTLImpl`.

Ein Beispiel finden Sie unter [ATL-Auflistungen und-Enumeratoren](../../atl/atl-collections-and-enumerators.md) .

## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Um diese Klasse unabhängig von ICollectionOnSTLImpl zu verwenden, verwenden Sie Folgendes:

- **typedef** eine Spezialisierung dieser Klasse.

- Verwenden Sie die **typedef** als Vorlagen Argument in einer Spezialisierung von `CComObject`.

- Erstellen Sie eine Instanz der `CComObject` Spezialisierung.

- Initialisieren Sie das Enumeratorobjekt durch Aufrufen von [IEnumOnSTLImpl:: init](../../atl/reference/ienumonstlimpl-class.md#init).

- Gibt die Enumeratorschnittstelle an den Client zurück.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)

`CComEnumOnSTL`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

## <a name="example"></a>Beispiel

Der folgende Code stellt eine generische Funktion bereit, mit der die Erstellung und Initialisierung eines Enumeratorobjekts behandelt werden können:

[!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]

Diese Vorlagen Funktion kann verwendet werden, um die `_NewEnum` -Eigenschaft einer Auflistungs Schnittstelle wie unten dargestellt zu implementieren:

[!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]

Dieser Code erstellt eine **typedef** für `CComEnumOnSTL` , die mithilfe der `IEnumVariant` - `CComVariant`Schnittstelle einen Vektor von s verfügbar macht. Die `CVariantCollection` -Klasse ist `CreateSTLEnumerator` einfach darauf spezialisiert, mit enumeratorobjekten dieses Typs zu arbeiten.

## <a name="see-also"></a>Siehe auch

[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[Beispiel für ATLCollections: Veranschaulicht die Klassen "ICollectionOnSTLImpl", "CComEnumOnSTL" und "Custom Copy Policy"](../../overview/visual-cpp-samples.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[IEnumOnSTLImpl-Klasse](../../atl/reference/ienumonstlimpl-class.md)
