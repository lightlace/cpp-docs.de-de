---
title: ISupportErrorInfoImpl-Klasse
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 650d90c9ec98754e11586f63e0871b70ebbe34f3
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141701"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl-Klasse

Diese Klasse stellt eine Standardimplementierung von der [ISupportErrorInfo Schnittstelle](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler bei einem Objekt generiert.

> [!IMPORTANT]
> Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Parameter

*piid*<br/>
Ein Zeiger auf eine Schnittstelle, unterstützt die IID [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Gibt an, ob die Schnittstelle durch identifiziert `riid` unterstützt die [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) Schnittstelle.|

## <a name="remarks"></a>Hinweise

Die [ISupportErrorInfo Schnittstelle](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) wird sichergestellt, dass die Fehlerinformationen an den Client zurückgegeben werden kann. Objekten, `IErrorInfo` müssen implementieren `ISupportErrorInfo`.

Klasse `ISupportErrorInfoImpl` stellt eine Standardimplementierung von `ISupportErrorInfo` und kann verwendet werden, wenn nur eine einzelne Schnittstelle Fehler bei einem Objekt generiert. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Gibt an, ob die Schnittstelle durch identifiziert `riid` unterstützt die [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) Schnittstelle.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Hinweise

Finden Sie unter [ISupportErrorInfo:: InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
