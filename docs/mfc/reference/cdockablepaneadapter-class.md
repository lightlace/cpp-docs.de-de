---
title: CDockablePaneAdapter-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter class
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
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
ms.openlocfilehash: 05d34e3ec84db48e50328b99c38abf1ef73747b4
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter-Klasse
Bietet Andockunterstützung für von `CWnd`abgeleitete Bereiche.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Gibt das umschlossene Fenster zurück.|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(Überschreibt [CDockablePane:: LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917).)|  
|[CDockablePaneAdapter::SaveState](#savestate)|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/c5c24249-8d0d-46cb-96d9-9f5c6dc191db).)|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Hinweise  
 In der Regel das Framework die Objekte dieser Klasse instanziiert, bei Verwendung der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) oder [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) Methoden.  
  
 Wenn Sie anpassen möchten, die `CDockablePaneAdapter` Verhalten, einfach eine neue Klasse ableiten und die Laufzeit-Klasseninformationen für ein Fenster im Registerkartenformat, mit [cmfcbasetabctrl::](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockablePaneAdapter.h  
  
##  <a name="a-namegetwrappedwnda--cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a>CDockablePaneAdapter::GetWrappedWnd  
 Gibt den zugrunde liegenden Fensters für den Adapter andockbaren Bereich zurück.  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das umschlossene Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um das umschlossene Fenster zuzugreifen.  
  
##  <a name="a-nameloadstatea--cdockablepaneadapterloadstate"></a><a name="loadstate"></a>CDockablePaneAdapter::LoadState  
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
 Der Profil-Index.  
  
 [in] `uiID`  
 Die Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesavestatea--cdockablepaneadaptersavestate"></a><a name="savestate"></a>CDockablePaneAdapter::SaveState  
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
 Der Profil-Index (standardmäßig die Steuerelement-ID des Fensters).  
  
 [in] `uiID`  
 Die Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetwrappedwnda--cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a>CDockablePaneAdapter::SetWrappedWnd  
 Das zugrunde liegende Fenster festgelegt für den Adapter andockbaren Bereich.  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf das Fenster für den Adapter Bereich umbrochen.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)

