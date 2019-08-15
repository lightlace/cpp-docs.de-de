---
title: IPropertyPage2Impl-Klasse
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: 5ec6cb2f4fc6931a1bec429068b558bf7ac1906e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495607"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl-Klasse

Diese Klasse implementiert `IUnknown` und erbt die Standard Implementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die von `IPropertyPage2Impl`abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPropertyPage2Impl:: editproperty](#editproperty)|Gibt an, welches Eigenschaften Steuerelement den Fokus erhält, wenn die Eigenschaften Seite aktiviert wird. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) -Schnittstelle erweitert [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) durch `EditProperty` hinzufügen der-Methode. Diese Methode ermöglicht es einem Client, eine bestimmte Eigenschaft in einem Eigenschaften Seiten Objekt auszuwählen.

Class `IPropertyPage2Impl` gibt einfach E_NOTIMPL für `IPropertyPage2::EditProperty`zurück. Er erbt jedoch die Standard Implementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) und implementiert `IUnknown` durch das Senden von Informationen an das dumpgerät in Debugbuilds.

Wenn Sie eine Eigenschaften Seite erstellen, wird die Klasse in der Regel `IPropertyPageImpl`von abgeleitet. Um die zusätzliche Unterstützung von `IPropertyPage2`bereitzustellen, ändern Sie die Klassendefinition `EditProperty` , und überschreiben Sie die-Methode.

**Verwandte Artikel** [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="editproperty"></a>IPropertyPage2Impl:: editproperty

Gibt an, welches Eigenschaften Steuerelement den Fokus erhält, wenn die Eigenschaften Seite aktiviert wird.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IPropertyPage2:: editproperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
