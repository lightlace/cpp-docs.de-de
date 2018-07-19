---
title: IObjectWithSiteImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9403ed1a4ba82a1e60c42ed0e57e975e73d1dd
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883787"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl-Klasse
Diese Klasse stellt die Methoden, dass ein Objekt mit dem Standort kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Fragt den Standort für einen Schnittstellenzeiger auf.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Verwaltet den Standort des `IUnknown` Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) Schnittstelle ermöglicht es, ein Objekt mit dem Standort kommunizieren. Klasse `IObjectWithSiteImpl` stellt eine Standardimplementierung dieser Schnittstelle bereit und implementiert `IUnknown` durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus wird erstellt.  
  
 `IObjectWithSiteImpl` gibt zwei Methoden an. Der Client ruft zuerst `SetSite`, und übergeben des Standorts `IUnknown` Zeiger. This-Zeiger wird innerhalb des Objekts gespeichert und können später abgerufen werden, durch einen Aufruf von `GetSite`.  
  
 In der Regel, leiten Sie Ihre Klasse von `IObjectWithSiteImpl` ein Objekt, das für die Erstellung ist kein Steuerelement. Für Steuerelemente, leiten Sie Ihre Klasse von [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), die bietet auch eines Standort-Zeigers. Leiten Sie die Klasse nicht von beiden `IObjectWithSiteImpl` und `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 Fragt den Standort für einen Zeiger auf die Schnittstelle identifizierte `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Standort über diese Schnittstelle unterstützt, wird der Zeiger über zurückgegeben `ppvSite`. Andernfalls `ppvSite` auf NULL festgelegt ist.  
  
 Finden Sie unter [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) in das Windows SDK.  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 Verwaltet den Standort des `IUnknown` Zeiger.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Hinweise  
 `m_spUnkSite` anfänglich empfängt diese Zeiger durch einen Aufruf von [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSite*  
 [in] Zeiger auf die `IUnknown` -Schnittstellenzeiger des Standorts, der dieses Objekt zu verwalten. Wenn der Wert NULL ist, sollte das Objekt aufrufen `IUnknown::Release` an einem vorhandenen Standort, die zu diesem Zeitpunkt das Objekt nicht mehr den Standort weiß.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück.  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 Stellt das Objekt mit des Standorts des `IUnknown` Zeiger.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
