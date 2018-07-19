---
title: IProvideClassInfo2Impl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7e0bd440e2e4bd8d32525fe4be6aaad2c401f6a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880617"
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
 Ein Zeiger auf den Bezeichner für die Co-Klasse.  
  
 *psrcid*  
 Ein Zeiger auf den Bezeichner für die Co-Klasse standardmäßige ausgehende Disp-Schnittstelle.  
  
 *plibid*  
 Ein Zeiger auf die LIBID der Typbibliothek, die Informationen über die Schnittstelle enthält. Standardmäßig wird die Bibliothek auf Serverebene übergeben.  
  
 *wMajor*  
 Die Hauptversion der Typbibliothek Der Standardwert ist 1.  
  
 *wMinor*  
 Die Nebenversion der Typbibliothek Der Standardwert ist 0.  
  
 *tihclass*  
 Die Klasse, die zum Verwalten von Typinformationen für die Co-Klasse verwendet wird. Der Standardwert ist `CComTypeInfoHolder`.  
  
## <a name="members"></a>Member  
  
### <a name="constructors"></a>Konstruktoren  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Ruft eine `ITypeInfo` Zeiger auf die Typinformationen für die Co-Klasse.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Ruft die GUID für ausgehende Dispinterface des Objekts ab.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Verwaltet die Typinformationen für die Co-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) Schnittstelle erweitert [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) durch Hinzufügen der `GetGUID` Methode. Diese Methode ermöglicht einen Client, ein Objekt des ausgehenden Schnittstellen-IID für die Standardereignissatz abzurufen. Klasse `IProvideClassInfo2Impl` stellt eine Standardimplementierung von der `IProvideClassInfo` und `IProvideClassInfo2` Methoden.  
  
 `IProvideClassInfo2Impl` enthält einen statischen Member des Typs `CComTypeInfoHolder` , verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo  
 Ruft eine `ITypeInfo` Zeiger auf die Typinformationen für die Co-Klasse.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Schnittstellenaufruf](http://msdn.microsoft.com/library/windows/desktop/ms690192) in das Windows SDK.  
  
##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID  
 Ruft die GUID für ausgehende Dispinterface des Objekts ab.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) in das Windows SDK.  
  
##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Der Konstruktor.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Hinweise  
 Aufrufe `AddRef` auf die [_tih](#_tih) Member. Der Destruktor ruft `Release` auf.  
  
##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih  
 Diese statischen Datenmember ist eine Instanz der Klassenvorlagenparameter *Tihclass*, d. h. `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Hinweise  
 `_tih` verwaltet die Typinformationen für die Co-Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
