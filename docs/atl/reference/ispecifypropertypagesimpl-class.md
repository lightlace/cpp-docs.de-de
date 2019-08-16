---
title: ISpecifyPropertyPagesImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: c201cf6d9d89ab1a6a8e888deee1be79e5770490
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495410"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standard Implementierung der [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) -Schnittstelle bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `ISpecifyPropertyPagesImpl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Füllt ein Gezähltes Array von UUID-Werten. Jede UUID entspricht der CLSID für eine der Eigenschaften Seiten, die auf dem Eigenschaften Blatt des Objekts angezeigt werden kann.|

## <a name="remarks"></a>Hinweise

Mithilfe der [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) -Schnittstelle kann ein Client eine Liste von CLSIDs für die von einem-Objekt unterstützten Eigenschaften Seiten abrufen. Die `ISpecifyPropertyPagesImpl` -Klasse stellt eine Standard Implementierung dieser Schnittstelle `IUnknown` bereit und implementiert durch das Senden von Informationen an das dumpgerät in Debugbuilds.

> [!NOTE]
>  Machen Sie die- `ISpecifyPropertyPages` Schnittstelle nicht verfügbar, wenn das Objekt keine Eigenschaften Seiten unterstützt.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Anforderungen

**Header:** Atlcom. h

##  <a name="getpages"></a>ISpecifyPropertyPagesImpl:: GetPages

Füllt das Array in der [cauuid](/windows/win32/api/ocidl/ns-ocidl-cauuid) -Struktur mit den CLSIDs für die Eigenschaften Seiten aus, die auf dem Eigenschaften Blatt des-Objekts angezeigt werden können.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Hinweise

ATL verwendet die Eigenschaften Zuordnung des Objekts, um jede CLSID abzurufen.

Weitere Informationen finden Sie unter [ISpecifyPropertyPages:: GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
