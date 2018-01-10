---
title: IDispatchImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3008d42986fcdc4b98ba6a1f9c85c437f2d335c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idispatchimpl-class"></a>IDispatchImpl-Klasse
Stellt eine Standardimplementierung für die `IDispatch` eine duale Schnittstelle Teil.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
 Ein Zeiger auf die IID der `T`.  
  
 [in] `plibid`  
 Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 [in] `wMajor`  
 Die Hauptversion der Typbibliothek Standardmäßig ist der Wert 1.  
  
 [in] `wMinor`  
 Die Nebenversion der Typbibliothek Standardmäßig ist der Wert 0.  
  
 [in] `tihclass`  
 Die Klasse, die zum Verwalten der Typinformationen für `T`. In der Standardeinstellung ist der Wert `CComTypeInfoHolder`.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Der Konstruktor. Aufrufe `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft `Release` auf.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Ordnet eine Reihe von Namen einer entsprechenden Reihe von Dispatchbezeichnern zu.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Ruft die Typinformationen für die duale Schnittstelle ab.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Bestimmt, ob es Typinformationen für die duale Schnittstelle verfügbar ist.|  
|[IDispatchImpl::Invoke](#invoke)|Bietet Zugriff auf die Methoden und Eigenschaften, die von der dualen Schnittstelle verfügbar gemacht werden.|  
  
## <a name="remarks"></a>Hinweise  
 `IDispatchImpl`Stellt eine Standardimplementierung für die `IDispatch` Teil eine duale Schnittstelle für ein Objekt. Eine duale Schnittstelle abgeleitet `IDispatch` und nur Automation-kompatiblen Typen verwendet. Wie eine Dispinterface unterstützt eine duale Schnittstelle frühes Binden und spätes Binden. eine duale Schnittstelle unterstützt jedoch auch Vtable-Bindung.  
  
 Das folgende Beispiel zeigt eine typische Implementierung der `IDispatchImpl`.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 Wird standardmäßig die `IDispatchImpl` Klasse sucht die Typinformationen für `T` in der Registrierung. Um eine nicht registrierte Schnittstelle zu implementieren, können Sie die `IDispatchImpl` Klasse ohne den Zugriff auf die Registrierung mithilfe einer vordefinierten Versionsnummer. Bei Erstellung einer `IDispatchImpl` -Objekt, das als Wert für 0xFFFF hat `wMajor` und 0xFFFF als Wert für `wMinor`, die `IDispatchImpl` Klasse ruft der Typbibliothek aus der DLL-Datei anstelle der Registrierung ab.  
  
 `IDispatchImpl`enthält einen statischen Member des Typs `CComTypeInfoHolder` , die die Typinformationen für die duale Schnittstelle verwaltet. Wenn Sie mehrere Objekte verfügen, die die gleiche duale implementieren-Schnittstelle, nur eine Instanz des `CComTypeInfoHolder` verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `T`  
  
 `IDispatchImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
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
 Finden Sie unter [GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) im Windows SDK.  
  
##  <a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo  
 Ruft die Typinformationen für die duale Schnittstelle ab.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDispatch:: GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) im Windows SDK.  
  
##  <a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount  
 Bestimmt, ob es Typinformationen für die duale Schnittstelle verfügbar ist.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter `IDispatch::GetTypeInfoCount` im Windows SDK.  
  
##  <a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl  
 Der Konstruktor. Aufrufe `AddRef` für die geschützten Member-Variable, die die Typinformationen für die duale Schnittstelle verwaltet. Der Destruktor ruft **Version**.  
  
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
 Finden Sie unter [IDispatch:: Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
