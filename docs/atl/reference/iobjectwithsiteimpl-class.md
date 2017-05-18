---
title: IObjectWithSiteImpl Klasse | Microsoft-Dokumentation
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
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 49c52810417650c3d80fe4d0c09ccb2b67208ad4
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl-Klasse
Diese Klasse enthält Methoden, dass ein Objekt mit dem Standort kommunizieren.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Fragt die Site für einen Schnittstellenzeiger auf.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Verwaltet den Standort **IUnknown** Zeiger.|  
  
## <a name="remarks"></a>Hinweise  
 Die [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) Schnittstelle ermöglicht es, ein Objekt mit dem Standort kommunizieren. Klasse `IObjectWithSiteImpl` bietet eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 `IObjectWithSiteImpl`gibt zwei Methoden. Der Client ruft zuerst `SetSite`, übergeben der Website **IUnknown** Zeiger. This-Zeiger wird innerhalb des Objekts gespeichert und können später abgerufen werden, durch einen Aufruf von `GetSite`.  
  
 Normalerweise leiten Sie eine Klasse von `IObjectWithSiteImpl` Wenn Sie ein Objekt erstellt werden, ist kein Steuerelement. Für Steuerelemente, leiten Sie eine Klasse von [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), einen Zeiger für die Website bereit. Leiten Sie eine Klasse nicht von beiden `IObjectWithSiteImpl` und `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="getsite"></a>IObjectWithSiteImpl::GetSite  
 Abfragen von der Website für einen Zeiger auf die Schnittstelle, die durch identifizierte `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Standort diese Schnittstelle unterstützt, wird der Zeiger über zurückgegeben `ppvSite`. Andernfalls `ppvSite` Wert **NULL**.  
  
 Finden Sie unter [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite  
 Verwaltet den Standort **IUnknown** Zeiger.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Hinweise  
 `m_spUnkSite`zunächst empfängt diese Zeiger durch einen Aufruf von [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite  
 Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnkSite*  
 [in] Zeiger auf die **IUnknown** -Schnittstellenzeiger des Standorts Verwaltung dieses Objekts. Wenn NULL ist, sollte das Objekt aufrufen `IUnknown::Release` auf alle vorhandenen Website zu diesem Zeitpunkt das Objekt nicht mehr am Standort weiß.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
##  <a name="setsite"></a>IObjectWithSiteImpl::SetSite  
 Stellt das Objekt bereit, mit des Standorts **IUnknown** Zeiger.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

