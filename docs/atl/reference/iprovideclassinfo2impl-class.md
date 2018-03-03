---
title: IProvideClassInfo2Impl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fe466608acaecfaf6219b6d15d27e0611ac2511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl-Klasse
Diese Klasse stellt eine Standardimplementierung von der [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) und [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) Methoden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>Parameter  
 *pcoclsid*  
 Ein Zeiger auf die Co-Klasse-Bezeichner.  
  
 *psrcid*  
 Ein Zeiger auf den Bezeichner für die Co-Klasse Default ausgehende Disp-Schnittstelle.  
  
 `plibid`  
 Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek Der Standardwert ist 1.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse verwendet, um die Co-Klasse Typinformationen zu verwalten. Der Standardwert ist `CComTypeInfoHolder`.  
  
## <a name="members"></a>Member  
  
### <a name="constructors"></a>Konstruktoren  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Ruft eine **ITypeInfo** Zeiger auf die Co-Klasse-Typinformationen.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Ruft die GUID für das Objekt ausgehenden Dispinterface ab.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Verwaltet die Typinformationen für die Co-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) -Schnittstelle erweitert [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) durch Hinzufügen der `GetGUID` Methode. Diese Methode ermöglicht einem Client zum Abrufen eines Objekts Ausgangsschnittstelle IID für seine Standardsatz-Ereignis. Klasse `IProvideClassInfo2Impl` stellt eine Standardimplementierung von der **IProvideClassInfo** und `IProvideClassInfo2` Methoden.  
  
 `IProvideClassInfo2Impl`enthält einen statischen Member des Typs `CComTypeInfoHolder` , verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 Ruft eine `ITypeInfo` Zeiger auf die Co-Klasse-Typinformationen.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schnittstellenaufruf](http://msdn.microsoft.com/library/windows/desktop/ms690192) im Windows SDK.  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 Ruft die GUID für das Objekt ausgehenden Dispinterface ab.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) im Windows SDK.  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Der Konstruktor.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe `AddRef` auf die [_tih](#_tih) Member. Der Destruktor ruft **Version**.  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 Statische Datenmember ist eine Instanz des Vorlagenparameters Klasse `tihclass`, d. h. `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Hinweise  
 `_tih`verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
