---
title: Klasse IPerPropertyBrowsingImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IPerPropertyBrowsingImpl
- IPerPropertyBrowsing
- ATL::IPerPropertyBrowsingImpl
- ATL::IPerPropertyBrowsingImpl<T>
- IPerPropertyBrowsingImpl
- ATL.IPerPropertyBrowsingImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8f2c2016a83cad906be22183fcffa20ae3da3042
ms.lasthandoff: 02/24/2017

---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl-Klasse
Diese Klasse implementiert **IUnknown** und ermöglicht einem Client Zugriff auf die Informationen in den Eigenschaftenseiten des Objekts.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IPerPropertyBrowsingImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Ruft ein Array von Zeichenfolgen, die für die Werte, die eine bestimmte Eigenschaft annehmen kann.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Ruft eine **VARIANT** mit dem Wert einer Eigenschaft, die von einer bestimmten DISPID identifiziert. Die DISPID zugeordnet ist, mit dem Namen der Zeichenfolge entnommen `GetPredefinedStrings`. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Ruft die CLSID der Eigenschaftenseite eine bestimmte Eigenschaft zugeordnet.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) Schnittstelle ermöglicht es einen Client Zugriff auf die Informationen in den Eigenschaftenseiten des Objekts. Klasse `IPerPropertyBrowsingImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
> [!NOTE]
>  Wenn Sie Microsoft Access als der Container-Anwendung verwenden, leiten Sie eine Klasse von `IPerPropertyBrowsingImpl`. Andernfalls wird Access das Steuerelement nicht geladen.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="a-namegetdisplaystringa--iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>IPerPropertyBrowsingImpl::GetDisplayString  
 Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpredefinedstringsa--iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings  
 Füllt jede Array mit&0; (null) Elemente.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 ATL Implementierung von [GetPredefinedValue](#getpredefinedvalue) gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetpredefinedvaluea--iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue  
 Ruft eine **VARIANT** mit dem Wert einer Eigenschaft, die von einer bestimmten DISPID identifiziert. Die DISPID zugeordnet ist, mit dem Namen der Zeichenfolge entnommen `GetPredefinedStrings`.  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 ATL Implementierung von [GetPredefinedStrings](#getpredefinedstrings) keine entsprechenden Zeichenfolgen abruft.  
  
 Finden Sie unter [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemappropertytopagea--iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage  
 Ruft die CLSID der Eigenschaftenseite der angegebenen Eigenschaft zugeordnet.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet das Objekt eigenschaftszuordnung, um diese Informationen zu erhalten.  
  
 Finden Sie unter [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

