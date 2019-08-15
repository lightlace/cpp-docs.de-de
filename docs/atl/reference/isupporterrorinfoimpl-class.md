---
title: Isupporterrorinfoimpl-Klasse
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
ms.openlocfilehash: d5e7f087f6646940777ae8b2d2a4ea888fdd3593
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495366"
---
# <a name="isupporterrorinfoimpl-class"></a>Isupporterrorinfoimpl-Klasse

Diese Klasse stellt eine Standard Implementierung der [ISupportErrorInfo-Schnittstelle](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) bereit und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert.

> [!IMPORTANT]
> Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Parameter

*piid*<br/>
Ein Zeiger auf die IID einer Schnittstelle, die [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)unterstützt.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Gibt an, ob die von `riid` identifizierte Schnittstelle die [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) -Schnittstelle unterstützt.|

## <a name="remarks"></a>Hinweise

Die [ISupportErrorInfo-Schnittstelle](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) stellt sicher, dass Fehlerinformationen an den Client zurückgegeben werden können. Objekte, die `IErrorInfo` verwenden, `ISupportErrorInfo`müssen implementieren.

Die `ISupportErrorInfoImpl` -Klasse stellt eine Standard `ISupportErrorInfo` Implementierung von dar und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert. Beispiel:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="interfacesupportserrorinfo"></a>Isupporterrorinfoimpl:: interfakesupportserrorinfo

Gibt an, ob die von `riid` identifizierte Schnittstelle die [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) -Schnittstelle unterstützt.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ISupportErrorInfo:: interfakesupportserrorinfo](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
