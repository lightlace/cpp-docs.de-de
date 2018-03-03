---
title: CDockablePaneAdapter-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb0e10490a381784e40167e16d1c7ec4e7e1a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter-Klasse
Bietet Andockunterstützung für von `CWnd`abgeleitete Bereiche.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Gibt das umschlossene Fenster zurück.|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(Überschreibt [CDockablePane:: LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Hinweise  
 Das Framework instanziiert in der Regel Objekte dieser Klasse, bei der Verwendung der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) oder [cmfcbasetabctrl:: insertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) Methoden.  
  
 Wenn Sie anpassen möchten, die `CDockablePaneAdapter` Verhalten, nur eine neue Klasse ableiten und die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, mit [cmfcbasetabctrl::](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockablePaneAdapter.h  
  
##  <a name="getwrappedwnd"></a>CDockablePaneAdapter::GetWrappedWnd  
 Gibt das zugrunde liegende Fenster für den Adapter andockbaren Bereich zurück.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das umschlossene Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion auf das umschlossene Fenster zugreifen.  
  
##  <a name="loadstate"></a>CDockablePaneAdapter::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Profilname.  
  
 [in] `nIndex`  
 Der Index des Profils.  
  
 [in] `uiID`  
 Der Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="savestate"></a>CDockablePaneAdapter::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Der Profilname.  
  
 [in] `nIndex`  
 Der Index der Profile (Standardwert die Steuerelement-ID des Fensters).  
  
 [in] `uiID`  
 Der Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setwrappedwnd"></a>CDockablePaneAdapter::SetWrappedWnd  
 Das zugrunde liegende Fenster festgelegt für den Adapter andockbaren Bereich.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf das Fenster für den Adapter Bereich zu umschließen.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
