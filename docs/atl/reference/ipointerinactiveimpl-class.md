---
title: Ipointerinactiveimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 6fb5d9f2bcbdeda61f32947bf339d134c4924b72
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495654"
---
# <a name="ipointerinactiveimpl-class"></a>Ipointerinactiveimpl-Klasse

Diese Klasse implementiert `IUnknown` und die [ipointerininaktiven](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) Schnittstellen Methoden.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPointerInactiveImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Ruft die aktuelle Aktivierungs Richtlinie für das-Objekt ab. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Benachrichtigt das-Objekt, dass der Mauszeiger darüber bewegt wurde, und gibt an, dass das Objekt Mausereignisse auslösen kann. Die ATL-Implementierung gibt E_NOTIMPL zurück.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Legt den Mauszeiger für das inaktive Objekt fest. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Ein inaktives Objekt ist ein Objekt, das einfach geladen oder ausgeführt wird. Im Gegensatz zu einem aktiven Objekt kann ein inaktives Objekt keine Windows-Maus-und Tastatur Meldungen empfangen. Daher verbrauchen inaktive Objekte weniger Ressourcen und sind in der Regel effizienter.

Die [ipointerinaktive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) Schnittstelle ermöglicht es einem Objekt, eine minimale Ebene der Maus Interaktion zu unterstützen, während es inaktiv bleibt. Diese Funktion ist besonders nützlich für-Steuerelemente.

Die `IPointerInactiveImpl` -Klasse `IPointerInactive` implementiert die-Methoden durch einfaches zurückgeben von E_NOTIMPL. Sie wird jedoch implementiert `IUnknown` , indem in Debugbuilds Informationen an das dumpgerät gesendet werden.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getactivationpolicy"></a>Ipointerinactiveimpl:: GetActivationPolicy

Ruft die aktuelle Aktivierungs Richtlinie für das-Objekt ab.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ipointerininaktiv:: GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) in der Windows SDK.

##  <a name="oninactivemousemove"></a>Ipointerinactiveimpl:: oninactivemoulmove

Benachrichtigt das-Objekt, dass der Mauszeiger darüber bewegt wurde, und gibt an, dass das Objekt Mausereignisse auslösen kann.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Windows SDK unter [ipointerinaktiv:: oninactivemousermove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) .

##  <a name="oninactivesetcursor"></a>Ipointerinactiveimpl:: oninactivesetcursor

Legt den Mauszeiger für das inaktive Objekt fest.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [ipointerininaktiv:: oninactivesetcursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
