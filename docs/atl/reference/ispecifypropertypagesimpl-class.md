---
title: ISpecifyPropertyPagesImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb4611c52f65595eb84248507dfb3a85d1ab26fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035960"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl-Klasse

Diese Klasse implementiert `IUnknown` und stellt eine Standardimplementierung von der [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) Schnittstelle.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Füllt ein Array von UUID gezählt-Werte. Jede UUID entspricht die CLSID für eine der Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.|

## <a name="remarks"></a>Hinweise

Die [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) Schnittstelle ermöglicht es einen Client zum Abrufen einer Liste von CLSIDs für die Eigenschaftenseiten, die von einem Objekt unterstützten. Klasse `ISpecifyPropertyPagesImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

> [!NOTE]
>  Machen Sie nicht die `ISpecifyPropertyPages` Schnittstelle, wenn das Objekt Eigenschaftenseiten nicht unterstützt.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages

Füllt das Array der [CAUUID](/windows/desktop/api/ocidl/ns-ocidl-tagcauuid) Struktur mit der CLSID für die Eigenschaftenseiten, die im Eigenschaftenblatt des Objekts angezeigt werden können.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Hinweise

ATL verwendet eigenschaftenzuordnung des Objekts, um jede CLSID abzurufen.

Finden Sie unter [ISpecifyPropertyPages::GetPages](/windows/desktop/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
