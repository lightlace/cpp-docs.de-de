---
title: CDockablePaneAdapter-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71d89020869db10b45688dbaae71f38711d2667c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676362"
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
|[CDockablePaneAdapter::LoadState](#loadstate)|(Überschreibt [CDockablePane:: LoadState](cdockablepane-class.md#loadstate).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(Überschreibt [CDockablePane:: SaveState](cdockablepane-class.md).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Hinweise  
 Das Framework instanziiert in der Regel Objekte dieser Klasse, bei der Verwendung der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) oder [cmfcbasetabctrl:: insertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) Methoden.  
  
 Wenn Sie anpassen möchten die `CDockablePaneAdapter` Verhalten einfach eine neue Klasse davon ableiten und die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, mithilfe von [cmfcbasetabctrl:: Setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockablePaneAdapter.h  
  
##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd  
 Gibt das zugrunde liegende Fenster für die Karte des andockbaren Bereich zurück.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das umschlossene Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um das umschlossene Fenster zuzugreifen.  
  
##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszProfileName*  
 Der Profilname.  
  
 [in] *nIndex*  
 Der Index des Profils.  
  
 [in] *UiID*  
 Der Bereich-ID  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszProfileName*  
 Der Profilname.  
  
 [in] *nIndex*  
 Der Profil-Index (standardmäßig die Steuerelement-ID des Fensters).  
  
 [in] *UiID*  
 Der Bereich-ID  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd  
 Das zugrunde liegende Fenster festgelegt für die Karte des andockbaren Bereich.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *aufnehmen*  
 Ein Zeiger auf das Fenster für den Bereich-Adapter zum umschließen.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
