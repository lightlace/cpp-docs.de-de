---
title: IObjectWithSiteImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49574d31ef0c606528f29c0045506e5febe69b28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl-Klasse
Diese Klasse stellt Methoden und ein Objekt mit dem Standort kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Fragt den Standort für einen Schnittstellenzeiger auf.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Verwaltet den Standort **IUnknown** Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 Die ["IObjectWithSite"](http://msdn.microsoft.com/library/windows/desktop/ms693765) Schnittstelle ermöglicht es, ein Objekt mit dem Standort kommunizieren. Klasse `IObjectWithSiteImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 `IObjectWithSiteImpl`gibt zwei Methoden. Der erste Client ruft `SetSite`, übergeben des Standorts **IUnknown** Zeiger. This-Zeiger wird innerhalb des Objekts gespeichert und können später abgerufen werden, durch einen Aufruf von `GetSite`.  
  
 In der Regel, leiten Sie eine Klasse von `IObjectWithSiteImpl` ein Objekt, das für die Erstellung eines Steuerelements ist. Für Steuerelemente, leiten Sie eine Klasse von [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), stellt auch einen Website-Zeiger. Leiten Sie eine Klasse nicht sowohl `IObjectWithSiteImpl` und `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getsite"></a>IObjectWithSiteImpl::GetSite  
 Fragt den Standort für einen Zeiger auf die Schnittstelle identifizierten `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Standort über diese Schnittstelle unterstützt, wird der Zeiger über zurückgegeben `ppvSite`. Andernfalls `ppvSite` festgelegt ist, um **NULL**.  
  
 Finden Sie unter [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) im Windows SDK.  
  
##  <a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite  
 Verwaltet den Standort **IUnknown** Zeiger.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Hinweise  
 `m_spUnkSite`anfänglich empfängt this-Zeiger durch einen Aufruf von [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite  
 Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSite*  
 [in] Zeiger auf die **IUnknown** Schnittstellenzeiger des Standorts, der dieses Objekt zu verwalten. Bei NULL wird das Objekt aufrufen sollte `IUnknown::Release` auf alle vorhandenen Website zu diesem Zeitpunkt das Objekt nicht mehr am Standort weiß.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="setsite"></a>IObjectWithSiteImpl::SetSite  
 Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
