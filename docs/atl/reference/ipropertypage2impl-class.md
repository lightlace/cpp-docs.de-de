---
title: IPropertyPage2Impl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 204f62e667bd149dd174f960ba31d8388e01394e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl-Klasse
Diese Klasse implementiert **IUnknown** und erbt die standardmäßige Implementierung des [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPropertyPage2Impl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Gibt an, welches Steuerelement den Fokus erhält, wenn die Eigenschaftsseite "aktiviert ist. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) -Schnittstelle erweitert [IPropertyPage-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms691246) durch Hinzufügen der `EditProperty` Methode. Diese Methode ermöglicht einem Client auf eine bestimmte Eigenschaft in einem Eigenschaft-Page-Objekt.  
  
 Klasse `IPropertyPage2Impl` gibt einfach auftragsantwortnachrichten zurück **E_NOTIMPL** für **IPropertyPage2::EditProperty**. Sie erbt jedoch die standardmäßige Implementierung des [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 Bei der Erstellung einer Eigenschaftenseite wird eine Klasse in der Regel aus abgeleitet `IPropertyPageImpl`. Die zusätzliche Unterstützung bereitstellen **IPropertyPage2**, ändern Sie die Klassendefinition, und überschreiben die `EditProperty` Methode.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty  
 Gibt an, welches Steuerelement den Fokus erhält, wenn die Eigenschaftsseite "aktiviert ist.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
