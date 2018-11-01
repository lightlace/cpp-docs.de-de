---
title: CComEnum-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 8e0bf49b48c2c0f1a202231e67364637375f9342
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623534"
---
# <a name="ccomenum-class"></a>CComEnum-Klasse

Diese Klasse definiert ein COM-Enumerator-Objekt basierend auf einem Wertearray.

## <a name="syntax"></a>Syntax

```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
T,
    Copy>,
public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parameter

*Basis*<br/>
Eine COM-Enumerator-Schnittstelle. Finden Sie unter [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) verdeutlicht.

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, die von der Enumeratorschnittstelle verfügbar gemacht werden.

*Kopieren*<br/>
Eine homogene [kopieren Richtlinienklasse](../../atl/atl-copy-policy-classes.md).

*ThreadModel*<br/>
Das Threadingmodell der-Klasse. Dieser Parameter ist standardmäßig auf das globale Objekt Thread-Modell in Ihrem Projekt verwendet.

## <a name="remarks"></a>Hinweise

`CComEnum` definiert ein COM-Enumerator-Objekt basierend auf einem Wertearray. Diese Klasse ist analog zu [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) implementiert einen Enumerator, der basierend auf einem C++-Standardbibliothek-Container. Typische Schritte bei der Verwendung dieser Klasse werden im folgenden beschrieben. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumerationen](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Diese Klasse verwenden zu können:

- **TypeDef** eine Spezialisierung dieser Klasse.

- Verwenden der **Typedef** als Vorlagenargument in einer Spezialisierung von `CComObject`.

- Erstellen Sie eine Instanz von der `CComObject` Spezialisierung.

- Initialisieren Sie das Enumeratorobjekt durch Aufrufen [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).

- Die Enumeratorschnittstelle an den Client zurückgeben.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

## <a name="example"></a>Beispiel

Der folgenden Code enthält eine wiederverwendbare Funktion zum Erstellen und initialisieren ein Enumeratorobjekt.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Diese Vorlagenfunktion kann zum Implementieren der `_NewEnum` Eigenschaft einer Auflistung-Schnittstelle, wie unten dargestellt:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Dieser Code erstellt eine **Typedef** für `CComEnum` , verfügbar macht, einen Vektor von Varianten, die über die `IEnumVariant` Schnittstelle. Die `CVariantArrayCollection` Klasse einfach spezialisiert `CreateEnumerator` zum Arbeiten mit Objekten der Enumerator von diesem Typ und übergibt die erforderlichen Argumente.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[CComEnumImpl-Klasse](../../atl/reference/ccomenumimpl-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)
