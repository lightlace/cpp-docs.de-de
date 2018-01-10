---
title: IPerPropertyBrowsingImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs: C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dca0c4e519703408af1ca5b6834e4b311c70bd21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl-Klasse
Diese Klasse implementiert **IUnknown** und erlaubt einem Client, die Informationen in den Eigenschaftenseiten für ein Objekt zuzugreifen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IPerPropertyBrowsingImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Ruft ein Array von Zeichenfolgen, die für die Werte, die eine bestimmte Eigenschaft annehmen kann.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Ruft eine **VARIANT** mit dem Wert einer Eigenschaft, die von einer bestimmten DISPID identifiziert. Die DISPID zugeordnet ist, mit den Zeichenfolgennamen entnommen `GetPredefinedStrings`. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Ruft die CLSID der Eigenschaftenseite auf einer angegebenen Eigenschaft zugeordnet.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) Schnittstelle ermöglicht es einen Client Zugriff auf die Informationen in den Eigenschaftenseiten für ein Objekt. Klasse `IPerPropertyBrowsingImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
> [!NOTE]
>  Wenn Sie Microsoft Access als Steuerelementcontainer-Anwendung verwenden, leiten Sie eine Klasse von `IPerPropertyBrowsingImpl`. Access lädt, andernfalls nicht Ihrer Kontrolle.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getdisplaystring"></a>IPerPropertyBrowsingImpl::GetDisplayString  
 Ruft eine Zeichenfolge, die eine bestimmte Eigenschaft beschreibt.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) im Windows SDK.  
  
##  <a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings  
 Füllt jede Array mit 0 (null) Elemente.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>Rückgabewert  
 ATL Implementierung von [GetPredefinedValue](#getpredefinedvalue) gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724) im Windows SDK.  
  
##  <a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue  
 Ruft eine **VARIANT** mit dem Wert einer Eigenschaft, die von einer bestimmten DISPID identifiziert. Die DISPID zugeordnet ist, mit den Zeichenfolgennamen entnommen `GetPredefinedStrings`.  
  
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
  
 Finden Sie unter [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) im Windows SDK.  
  
##  <a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage  
 Ruft die CLSID der Eigenschaftenseite der angegebenen Eigenschaft zugeordnet.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>Hinweise  
 ATL verwendet eigenschaftenzuordnung des Objekts, um diese Informationen abzurufen.  
  
 Finden Sie unter [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IPropertyPageImpl-Klasse](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl-Klasse](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
