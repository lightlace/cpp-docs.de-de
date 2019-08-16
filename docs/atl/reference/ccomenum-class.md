---
title: Ccomenumerationsklasse
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 7252eb2fa5d34618a1c38484a2506bae27a1106a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497211"
---
# <a name="ccomenum-class"></a>Ccomenumerationsklasse

Diese Klasse definiert ein com-Enumeratorobjekt, das auf einem Array basiert.

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

*Sock*<br/>
Eine com-Enumeratorschnittstelle. Ein Beispiel finden Sie unter " [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) ".

*piid*<br/>
Ein Zeiger auf die Schnittstellen-ID der Enumeratorschnittstelle.

*T*<br/>
Der Typ des Elements, das von der Enumeratorschnittstelle verfügbar gemacht wird.

*Kopieren*<br/>
Eine homogene [Kopier Richtlinien Klasse](../../atl/atl-copy-policy-classes.md).

*ThreadModel*<br/>
Das Threading Modell der-Klasse. Dieser Parameter ist standardmäßig das globale Objekt Thread Modell, das im Projekt verwendet wird.

## <a name="remarks"></a>Hinweise

`CComEnum`definiert ein com-Enumeratorobjekt, das auf einem Array basiert. Diese Klasse ist analog zu [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) , das einen Enumerator auf Grundlage eines C++ Standard Bibliothek Containers implementiert. Im folgenden werden typische Schritte zum Verwenden dieser Klasse beschrieben. Weitere Informationen finden Sie unter [ATL-Auflistungen und-Enumeratoren](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>So verwenden Sie diese Klasse:

- **typedef** eine Spezialisierung dieser Klasse.

- Verwenden Sie die **typedef** als Vorlagen Argument in einer Spezialisierung von `CComObject`.

- Erstellen Sie eine Instanz der `CComObject` Spezialisierung.

- Initialisieren Sie das Enumeratorobjekt durch Aufrufen von [CComEnumImpl:: init](../../atl/reference/ccomenumimpl-class.md#init).

- Gibt die Enumeratorschnittstelle an den Client zurück.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

## <a name="example"></a>Beispiel

Der unten gezeigte Code bietet eine wiederverwendbare Funktion zum Erstellen und Initialisieren eines Enumeratorobjekts.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Diese Vorlagen Funktion kann verwendet werden, um die `_NewEnum` -Eigenschaft einer Auflistungs Schnittstelle wie unten dargestellt zu implementieren:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Dieser Code erstellt eine **typedef** für `CComEnum` , die einen Vektor von Varianten über die `IEnumVariant` -Schnittstelle verfügbar macht. Die `CVariantArrayCollection` -Klasse ist `CreateEnumerator` einfach darauf spezialisiert, mit enumeratorobjekten dieses Typs zu arbeiten und übergibt die erforderlichen Argumente.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[CComEnumImpl-Klasse](../../atl/reference/ccomenumimpl-class.md)<br/>
[CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md)
