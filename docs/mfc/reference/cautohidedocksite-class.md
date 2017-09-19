---
title: Klasse CAutoHideDockSite | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
dev_langs:
- C++
helpviewer_keywords:
- AllowShowOnPaneMenu method
- CAutoHideDockSite class
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
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
ms.openlocfilehash: 58beaa382a2ef04cfaee0fbcf63b9eef36831472
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite-Klasse
Die `CAutoHideDockSite` erweitert die [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md) implementieren automatisch im Hintergrund Bereiche andocken.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CAutoHideDockSite::CAutoHideDockSite`|Erstellt ein `CAutoHideDockSite`-Objekt.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Gibt an, ob die `CAutoHideDockSite` auf das Menü angezeigt wird.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein Basis Pane-Objekt abgeleitet wird die [CMFCAutoHideBar Klasse](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Dies einen Bereich angedockt `CAuotHideDockSite` Objekt.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Ruft die Größe des Standorts Andocken in Bildschirmkoordinaten ab.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Zeichnet den Bereich auf die `CAutoHideDockSite` mit dem globalen Ränder und Abstand der Schaltfläche.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Wird der Rand auf der linken Seite der andockleiste an.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Wird der Rand auf der rechten Seite der andockleiste an.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Aufrufe [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) für Objekte auf der `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Definiert die Größe des Abstands zwischen den Symbolleisten und dem Rand der andockleiste an. Dieser Speicherplatz wird vom linken Rand oder oberen Rand, abhängig von der Ausrichtung für die Dock Speicherplatz gemessen.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Aufruf von [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), erstellt das Framework automatisch ein `CAutoHideDockSite` Objekt. In den meisten Fällen sollten Sie keinen zu instanziieren, oder verwenden Sie diese Klasse direkt.  
  
 Andockleiste ist der Abstand zwischen der linken Seite des Bereichs Andocken und dem linken Rand der [CMFCAutoHideButton Klasse](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen einer `CAutoHideDockSite` -Objekt aus einer `CMFCAutoHideBar` Objekt und den linken und rechten Rand der andockleiste festlegen.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#29;](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 Bestimmt, ob ein Basis-Fenster ist ein [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekt oder abgeleitete `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pBar`|Der Basis-Bereich, den das Framework testet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pBar` abgeleitet ist `CMFCAutoHideBar`; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Basis Pane-Objekt abgeleitet wird `CMFCAutoHideBar`, enthalten eine `CAutoHideDockSite`.  
  
##  <a name="dockpane"></a>CAutoHideDockSite::DockPane  
 Dies einen Bereich angedockt [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) Objekt.  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWnd`|Der Bereich, den das Framework angedockt.|  
|[in] `dockMethod`|Andock-Optionen für den Bereich.|  
|[in] `lpRect`|Ein Rechteck, das die Grenzen des angedockten Bereichs angibt.|  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung verwenden den Parameter nicht `dockMethod`, die für die zukünftige Verwendung bereitgestellt wird.  
  
 Wenn `lpRect` ist `NULL`, das Framework legt den Bereich am Standardspeicherort auf der Website andocken. Bei die Website Andocken horizontaler ist der Standardspeicherort am linken Rand des Standorts andocken. Andernfalls ist der Standardspeicherort am oberen Rand der Website andocken.  
  
##  <a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 Ruft die Größe des Standorts Andocken in Bildschirmkoordinaten ab.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `rect`|Ein Verweis auf ein Rechteck. Die Methode speichert die Größe der Dock-Website in dieses Rechteck.|  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck für den Versatz angepasst, sodass sie nicht eingeschlossen werden.  
  
##  <a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 Die Größe des Abstands zwischen den Rändern der [CAutoHideDockSite Klasse](../../mfc/reference/cautohidedocksite-class.md) und [CMFCAutoHideBar Klasse](../../mfc/reference/cmfcautohidebar-class.md) Objekte.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CMFCAutoHideBar` auf verankert ein `CAutoHideDockSite`, sollte er nicht die gesamte docksite umfassen. Diese globale Variable steuert den zusätzlichen Abstand zwischen dem linken oder oberen Rand der `CMFCAutoHideBar` und die entsprechenden `CAutoHideDockSite` Rand. Gibt an, ob am obere oder linke Rand verwendet wird, hängt von der aktuellen Ausrichtung ab.  
  
##  <a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 Wird der Rand auf der linken Seite der andockleiste an.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Der neue Offset.  
  
### <a name="remarks"></a>Hinweise  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekte sind statisch auf positioniert das `CAutoHideDockSite` Objekt. Dies bedeutet, dass der Benutzer den Speicherort der manuell ändern, kann `CMFCAutoHideBar` Objekte. Die `SetOffsetLeft` Methode steuert den Abstand zwischen dem linken Rand der am weitesten links `CMFCAutoHideBar` und dem linken Rand der `CAutoHideDockSite`.  
  
##  <a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 Wird der Rand auf der rechten Seite der andockleiste an.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Der neue Offset.  
  
### <a name="remarks"></a>Hinweise  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekte sind statisch auf positioniert das `CAutoHideDockSite` Objekt. Dies bedeutet, dass der Benutzer den Speicherort der manuell ändern, kann der `CMFCAutoHideBar` Objekte. Die `SetOffsetRight` Methode steuert den Abstand zwischen dem rechten Rand der äußersten `CMFCAutoHideBar` und rechts neben der `CAutoHideDockSite`.  
  
##  <a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 Zeichnet die Bereiche auf der [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `rectNewClientArea`|Ein reservierter Wert.|  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung verwendet keine `rectNewClientArea`. Es zeichnet die Bereiche mit der globalen Symbolleiste Ränder und Abstand der Schaltfläche neu.  
  
##  <a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 Aufrufe [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) für Objekte auf der Website andocken.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pAutoHideToolbar`|Ein Zeiger auf eine [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objektbereich befindet sich auf der `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht nach der Zeile mit `pAutoHideToolbar`. Sie ruft `CMFCAutoHideBar.UnSetAutoHideMode` für alle der `CMFCAutoHideBar` Objekte in dieser Zeile. Wenn `pAutoHideToolbar` wurde nicht gefunden oder ist `NULL`, ruft diese Methode `CMFCAutoHideBar.UnSetAutoHideMode` für alle der `CMFCAutoHideBar` Objekte auf der `CAutoHideDockSite`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)

