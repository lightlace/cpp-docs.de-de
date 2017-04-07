---
title: Klasse IPropertyPage2Impl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 43680d12febbd94137009f66242198129d4b3630
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl-Klasse
Diese Klasse implementiert **IUnknown** und erbt die standardmäßige Implementierung des [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IPropertyPage2Impl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Gibt an, welche Eigenschaftensteuerelement den Fokus erhalten wird, wenn die Eigenschaftenseite aktiviert wird. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) Schnittstelle erweitert [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) durch Hinzufügen der `EditProperty` Methode. Diese Methode kann ein Client eine bestimmte Eigenschaft in der Page-Objekt eine Eigenschaft auswählen.  
  
 Klasse `IPropertyPage2Impl` gibt einfach **E_NOTIMPL** für **IPropertyPage2::EditProperty**. Es erbt jedoch die standardmäßige Implementierung des [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 Wenn Sie eine Eigenschaftenseite erstellen, Ihre Klasse wird in der Regel abgeleitet `IPropertyPageImpl`. Die zusätzliche Unterstützung bereitstellen **IPropertyPage2**, ändern Sie die Klassendefinition, und überschreiben Sie die `EditProperty` Methode.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 Gibt an, welche Eigenschaftensteuerelement den Fokus erhalten wird, wenn die Eigenschaftenseite aktiviert wird.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IPerPropertyBrowsingImpl-Klasse](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

