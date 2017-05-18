---
title: IDispatchImpl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fff4cbc0a3f87b584f1a4211f4aad37228ed4da7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="idispatchimpl-class"></a>IDispatchImpl-Klasse
Stellt eine Standardimplementierung für die `IDispatch` eine duale Schnittstelle Teil.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `T`  
 Eine duale Schnittstelle.  
  
 [in] `piid`  
 Ein Zeiger auf die ID der `T`.  
  
 [in] `plibid`  
 Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 [in] `wMajor`  
 Die Hauptversion der Typbibliothek. Standardmäßig ist der Wert 1.  
  
 [in] `wMinor`  
 Die Nebenversion der Typbibliothek. Standardmäßig ist der Wert 0.  
  
 [in] `tihclass`  
 Die Klasse zur Verwaltung von Informationen für den `T`. In der Standardeinstellung ist der Wert `CComTypeInfoHolder`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Der Konstruktor. Ruft `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für die duale Schnittstelle ab.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Bestimmt, ob die Typinformationen für die duale Schnittstelle verfügbar ist.|  
|[IDispatchImpl::Invoke](#invoke)|Bietet Zugriff auf die Methoden und Eigenschaften, die von der dualen Schnittstelle verfügbar gemacht werden.|  
  
## <a name="remarks"></a>Hinweise  
 `IDispatchImpl`Stellt eine Standardimplementierung für die `IDispatch` Teil eine duale Schnittstelle für ein Objekt. Eine duale Schnittstelle leitet sich von `IDispatch` und verwendet nur Automatisierungskompatible Datentypen. Wie eine Disp-Schnittstelle unterstützt eine duale Schnittstelle frühen und späten Bindung. eine duale Schnittstelle unterstützt jedoch auch Vtable-Bindung.  
  
 Das folgende Beispiel zeigt eine typische Implementierung der `IDispatchImpl`.  
  
 [!code-cpp[NVC_ATL_COM&#47;](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 In der Standardeinstellung die `IDispatchImpl` Klasse sucht die Typinformationen für `T` in der Registrierung. Um eine nicht registrierte Schnittstelle zu implementieren, können Sie die `IDispatchImpl` -Klasse ohne Zugriff auf die Registrierung mithilfe einer vordefinierten Versionsnummer. Bei der Erstellung einer `IDispatchImpl` -Objekt, das als Wert für 0xFFFF hat `wMajor` und 0xFFFF als Wert für `wMinor`, die `IDispatchImpl` -Klasse ruft die Typbibliothek aus der DLL-Datei anstelle der Registrierung.  
  
 `IDispatchImpl`enthält einen statischen Member des Typs `CComTypeInfoHolder` , der die Typinformationen für die duale Schnittstelle verwaltet. Wenn mehrere Objekte, die die zwei gleiche implementieren Schnittstelle nur eine Instanz des `CComTypeInfoHolder` verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames  
 Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo  
 Ruft die Typinformationen für die duale Schnittstelle ab.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount  
 Bestimmt, ob die Typinformationen für die duale Schnittstelle verfügbar ist.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 See `IDispatch::GetTypeInfoCount` in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl  
 Der Konstruktor. Ruft `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft **Version**.  
  
```
IDispatchImpl();
```  
  
##  <a name="invoke"></a>IDispatchImpl::Invoke  
 Bietet Zugriff auf die Methoden und Eigenschaften, die von der dualen Schnittstelle verfügbar gemacht werden.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

