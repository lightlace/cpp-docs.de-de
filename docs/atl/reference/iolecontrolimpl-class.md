---
title: IOleControlImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a54067f53e83d78f063ae5f3694460452e24b26
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361797"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl-Klasse
Diese Klasse stellt eine Standardimplementierung von der **IOleControl** Schnittstelle und implementiert **IUnknown**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IOleControlImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Gibt an, ob der Container ignoriert oder Ereignisse vom Steuerelement akzeptiert.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Informationen über die Tastaturverhalten des Steuerelements füllt. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Informiert ein Steuerelement, dass mindestens eines der Container Umgebungseigenschaften geändert hat. Gibt die ATL-Implementierung `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Informiert, dass ein Benutzer eine angegebene Tastatureingabe gedrückt hat dem Steuerelement. Gibt die ATL-Implementierung **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `IOleControlImpl` stellt eine Standardimplementierung von der [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 In ATLs-Implementierung `FreezeEvents` erhöht der Steuerelementklasse `m_nFreezeEvents` -Datenmember Wenn `bFreeze` ist **"true"**, und dekrementiert `m_nFreezeEvents` Wenn `bFreeze` ist **"false"**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Hinweise  
 `FreezeEvents` Anschließend gibt `S_OK`.  
  
 Finden Sie unter [IOleControl:: FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) im Windows SDK.  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 Informationen über die Tastaturverhalten des Steuerelements füllt.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 Informiert ein Steuerelement, dass mindestens eines der Container Umgebungseigenschaften geändert hat.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) im Windows SDK.  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 Informiert, dass ein Benutzer eine angegebene Tastatureingabe gedrückt hat dem Steuerelement.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IOleObjectImpl-Klasse](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
