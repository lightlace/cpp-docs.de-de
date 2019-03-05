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
ms.openlocfilehash: bf76182242f7b76e3a2c18f85b72674e88afa737
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287504"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl-Klasse

Diese Klasse implementiert `IUnknown` und erbt von der Standardimplementierung von [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `IPropertyPage2Impl`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Gibt an, welche Eigenschaftensteuerelement den Fokus erhalten wird, wenn die Eigenschaftenseite aktiviert ist. Die ATL-Implementierung gibt E_NOTIMPL zurück.|

## <a name="remarks"></a>Hinweise

Die [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) Schnittstelle erweitert [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) durch Hinzufügen der `EditProperty` Methode. Diese Methode ermöglicht einen Client, wählen Sie eine bestimmte Eigenschaft in einem Eigenschaft-Page-Objekt.

Klasse `IPropertyPage2Impl` gibt einfach auftragsantwortnachrichten zurück E_NOTIMPL für `IPropertyPage2::EditProperty`. Allerdings erbt die standardmäßige Implementierung des [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.

Wenn Sie auf einer Eigenschaftenseite erstellen, die Klasse in der Regel ergibt sich aus `IPropertyPageImpl`. Die zusätzliche Unterstützung zu `IPropertyPage2`, ändern Sie die Klassendefinition, und überschreiben die `EditProperty` Methode.

**Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty

Gibt an, welche Eigenschaftensteuerelement den Fokus erhalten wird, wenn die Eigenschaftenseite aktiviert ist.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Rückgabewert

Gibt E_NOTIMPL zurück.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IPropertyPage2::EditProperty](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage2-editproperty) in das Windows SDK.

## <a name="see-also"></a>Siehe auch

[IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
