---
title: Klasse IOleControlImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5e63849a504b931de30141dd91af557f16c67fd8
ms.lasthandoff: 02/24/2017

---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl-Klasse
Diese Klasse enthält die standardmäßige Implementierung der **IOleControl** -Schnittstelle und implementiert **IUnknown**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IOleControlImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Gibt an, ob der Container ignoriert oder Ereignisse aus dem Steuerelement akzeptiert.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Informationen über die Tastaturverhalten des Steuerelements eingefügt. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Informiert ein Steuerelement, dass eine oder mehrere der ambient-Eigenschaften des Containers geändert hat. Der ATL-Implementierung zurückgegeben `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Benachrichtigt, dass ein Benutzer eine angegebene Tastenkombination gedrückt hat das Steuerelement. Der ATL-Implementierung zurückgegeben **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `IOleControlImpl` enthält die standardmäßige Implementierung der [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) -Schnittstelle und implementiert **IUnknown** durch Senden von Informationen an das Speicherabbild Gerät im Debugmodus erstellt.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 In ATL Implementierung `FreezeEvents` erhöht der Control-Klasse `m_nFreezeEvents` -Datenmember Wenn `bFreeze` ist **TRUE**, und dekrementiert `m_nFreezeEvents` Wenn `bFreeze` ist **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Hinweise  
 `FreezeEvents`Gibt `S_OK`.  
  
 Finden Sie unter [IOleControl:: FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 Informationen über die Tastaturverhalten des Steuerelements eingefügt.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange  
 Informiert ein Steuerelement, dass eine oder mehrere der ambient-Eigenschaften des Containers geändert hat.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK`zurück.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 Benachrichtigt, dass ein Benutzer eine angegebene Tastenkombination gedrückt hat das Steuerelement.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **E_NOTIMPL**.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IOleObjectImpl-Klasse](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX-Steuerelemente Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

