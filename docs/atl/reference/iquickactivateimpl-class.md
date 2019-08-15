---
title: Iquickactivateimpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 2169686ebbf756c5caf9232f5031532c62ac8265
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495507"
---
# <a name="iquickactivateimpl-class"></a>Iquickactivateimpl-Klasse

Diese Klasse kombiniert die Initialisierung von Container Steuerelementen zu einem einzelnen-Befehl.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IQuickActivateImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Ruft die aktuelle Anzeige Größe für ein ausgelaufendes Steuerelement ab.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Führt die schnelle Initialisierung von Steuerelementen aus, die geladen werden.|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Informiert das Steuerelement darüber, wie viel Anzeigebereich dem Container zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Mithilfe der [iquickaktivierungs](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) -Schnittstelle können Container Verzögerungen beim Laden von Steuerelementen vermeiden, indem die Initialisierung in einem einzelnen-Befehl kombiniert wird Die `QuickActivate` -Methode ermöglicht es dem Container, einen Zeiger auf eine [QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer) -Struktur zu übergeben, die Zeiger auf alle Schnittstellen enthält, die das Steuerelement benötigt. Bei der Rückgabe übergibt das Steuerelement einen Zeiger auf eine [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) -Struktur, die Zeiger auf seine eigenen Schnittstellen enthält, die vom Container verwendet werden. Die `IQuickActivateImpl` -Klasse stellt eine Standard `IQuickActivate` Implementierung von `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="getcontentextent"></a>Iquickactivateimpl:: GetContentExtent

Ruft die aktuelle Anzeige Größe für ein ausgelaufendes Steuerelement ab.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Hinweise

Die Größe ist für ein vollständiges Rendering des Steuer Elements und wird in HIMETRIC-Einheiten angegeben.

Weitere Informationen finden Sie unter [iquickaktivierungs:: GetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) im Windows SDK.

##  <a name="quickactivate"></a>Iquickactivateimpl:: quickaktivierungs

Führt die schnelle Initialisierung von Steuerelementen aus, die geladen werden.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Hinweise

Die-Struktur enthält Zeiger auf Schnittstellen, die vom-Steuerelement und den Werten einiger Ambient-Eigenschaften benötigt werden. Bei der Rückgabe übergibt das Steuerelement einen Zeiger auf eine [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) -Struktur, die Zeiger auf seine eigenen Schnittstellen enthält, die der Container benötigt, sowie zusätzliche Statusinformationen.

Weitere Informationen finden Sie unter [iquickaktivierung:: quickaktivierung](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) im Windows SDK.

##  <a name="setcontentextent"></a>Iquickactivateimpl:: setcontentextent

Informiert das Steuerelement darüber, wie viel Anzeigebereich dem Container zugeordnet ist.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Hinweise

Die Größe wird in HIMETRIC-Einheiten angegeben.

Weitere Informationen finden Sie unter [iquickaktivierungs:: setcontentextent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[CComControl-Klasse](../../atl/reference/ccomcontrol-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
