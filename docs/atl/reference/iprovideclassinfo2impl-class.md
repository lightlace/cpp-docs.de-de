---
title: Klasse IProvideClassInfo2Impl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.openlocfilehash: 0d3bed0f625e396b63ada19ded02ba9ad3b697b0
ms.lasthandoff: 02/24/2017

---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl-Klasse
Diese Klasse enthält die standardmäßige Implementierung der [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) und [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) Methoden.  
  
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
 Ein Zeiger auf den Bezeichner für die Co-Klasse Standard ausgehende Disp-Schnittstelle.  
  
 `plibid`  
 Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Typbibliothek auf Serverebene übergeben.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek. Der Standardwert ist 1.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek. Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse zur Verwaltung der Co-Klasse Typinformationen. Der Standardwert ist `CComTypeInfoHolder`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Ruft eine **ITypeInfo** Zeiger auf die Co-Klasse Typinformationen.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Ruft die GUID für das Objekt ausgehenden Dispinterface ab.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Verwaltet die Typinformationen für die Co-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) Schnittstelle erweitert [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) durch Hinzufügen der `GetGUID` Methode. Diese Methode kann ein Client zum Abrufen eines Objekts Ausgangsschnittstelle IID für den Ereignis-Standardeigenschaften. Klasse `IProvideClassInfo2Impl` enthält die standardmäßige Implementierung der **IProvideClassInfo** und `IProvideClassInfo2` Methoden.  
  
 `IProvideClassInfo2Impl`enthält einen statischen Member des Typs `CComTypeInfoHolder` , verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 Ruft eine `ITypeInfo` Zeiger auf die Co-Klasse Typinformationen.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schnittstellenaufruf](http://msdn.microsoft.com/library/windows/desktop/ms690192) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 Ruft die GUID für das Objekt ausgehenden Dispinterface ab.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Der Konstruktor.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe `AddRef` auf der [_tih](#_tih) Element. Der Destruktor ruft **Version**.  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 Statische Datenmember ist eine Instanz des Vorlagenparameters Klasse `tihclass`, d. h. `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Hinweise  
 `_tih`verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

