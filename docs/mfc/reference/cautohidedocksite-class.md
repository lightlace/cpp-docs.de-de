---
title: CAutoHideDockSite-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8cc4e9158ae9ff2ef6fd4d48483aa5a75dd9617
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite-Klasse
Die `CAutoHideDockSite` erweitert die [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md) implementieren um Andockbereiche automatisch im Hintergrund.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>Member  
  
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
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Gibt an, ob die `CAutoHideDockSite` wird im Menü angezeigt.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein Objekt für einen Basistyp abgeleitet ist die [CMFCAutoHideBar-Klasse](../../mfc/reference/cmfcautohidebar-class.md).|  
|[CAutoHideDockSite::DockPane](#dockpane)|Dockt einen Bereich an, zu diesem `CAuotHideDockSite` Objekt.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Ruft die Größe der DockPosition in Bildschirmkoordinaten ab.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|Zeichnet den Bereich auf die `CAutoHideDockSite` mit dem globalen Ränder und Abstand der Schaltfläche.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|Legt den Rand auf der linken Seite der andockleiste an.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Legt den Rand auf der rechten Seite der andockleiste an.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|Aufrufe [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) für Objekte auf die `CAutoHideDockSite`.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Definiert die Größe des Abstands zwischen Symbolleisten und dem Rand der andockleiste an. Dieser Speicherplatz wird aus dem linken Rand oder dem oberen Rand, abhängig von der Ausrichtung des Speicherplatzes Andocken gemessen.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Aufruf [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), erstellt das Framework automatisch eine `CAutoHideDockSite` Objekt. In den meisten Fällen sollten Sie keine instanziieren, oder verwenden Sie diese Klasse direkt.  
  
 Andockleiste ist die Lücke zwischen dem linken Rand des Bereichs Andocken und linken Rand der [CMFCAutoHideButton-Klasse](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Abrufen einer `CAutoHideDockSite` -Objekt aus einer `CMFCAutoHideBar` -Objekt, und wie die linken und rechten Rand der andockleiste festgelegt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 Bestimmt, ob ein Basis-Bereich ist eine [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekt oder abgeleitete `CMFCAutoHideBar`.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pBar`|Die Basis-Bereich, den das Framework testet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pBar` stammt aus `CMFCAutoHideBar`; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Objekt für einen Basistyp abgeleitet ist `CMFCAutoHideBar`, enthalten eine `CAutoHideDockSite`.  
  
##  <a name="dockpane"></a>CAutoHideDockSite::DockPane  
 Dockt einen Bereich an, zu diesem [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) Objekt.  
  
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
|[in] `pWnd`|Der Bereich, der das Framework dockt an.|  
|[in] `dockMethod`|Andocken von Optionen für den Bereich.|  
|[in] `lpRect`|Ein Rechteck, das die Grenzen für den angedockten Bereich angibt.|  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung verwendet nicht den Parameter `dockMethod`, die für die zukünftige Verwendung bereitgestellt wird.  
  
 Wenn `lpRect` ist `NULL`, das Framework setzt den Bereich der DockPosition am Standardort. Wenn der DockPosition horizontale ist, ist der Standardspeicherort am linken Rand der DockPosition. Andernfalls ist der Standardspeicherort am oberen Rand der DockPosition.  
  
##  <a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 Ruft die Größe der DockPosition in Bildschirmkoordinaten ab.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `rect`|Ein Verweis auf ein Rechteck. Die Methode speichert die Größe der DockPosition in dieses Rechteck.|  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck für den Versatz angepasst, sodass sie nicht eingeschlossen werden.  
  
##  <a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 Die Größe des Abstands zwischen den Rändern des der [CAutoHideDockSite-Klasse](../../mfc/reference/cautohidedocksite-class.md) und [CMFCAutoHideBar-Klasse](../../mfc/reference/cmfcautohidebar-class.md) Objekte.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CMFCAutoHideBar` am angedockt ist eine `CAutoHideDockSite`, sollten sie nicht die gesamte DockPosition beansprucht. Diese globale Variable steuert den zusätzlichen Abstand zwischen der linken oder oberen Rand der `CMFCAutoHideBar` und dem entsprechenden `CAutoHideDockSite` Edge. Gibt an, ob am obere oder linke Rand verwendet wird, hängt von der aktuellen Ausrichtung ab.  
  
##  <a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 Legt den Rand auf der linken Seite der andockleiste an.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Der neue Offset.  
  
### <a name="remarks"></a>Hinweise  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekte sind statisch auf positioniert das `CAutoHideDockSite` Objekt. Dies bedeutet, dass der Benutzer den Speicherort der manuell ändern kann `CMFCAutoHideBar` Objekte. Die `SetOffsetLeft` Methode steuert den Abstand zwischen der linken Seite des ganz links `CMFCAutoHideBar` und dem linken Rand der `CAutoHideDockSite`.  
  
##  <a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 Legt den Rand auf der rechten Seite der andockleiste an.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Der neue Offset.  
  
### <a name="remarks"></a>Hinweise  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objekte sind statisch auf positioniert das `CAutoHideDockSite` Objekt. Dies bedeutet, dass der Benutzer den Speicherort der manuell ändern, kann die `CMFCAutoHideBar` Objekte. Die `SetOffsetRight` Methode steuert den Abstand zwischen rechts neben der ganz rechts stehenden `CMFCAutoHideBar` und rechts neben der `CAutoHideDockSite`.  
  
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
 Die Standardimplementierung verwendet keine `rectNewClientArea`. Es zeichnet die Bereiche mit der globalen Symbolleiste Ränder und Abstand der Schaltfläche.  
  
##  <a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 Aufrufe [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) für Objekte auf der DockPosition.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pAutoHideToolbar`|Ein Zeiger auf eine [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) Objektbereich befindet sich auf die `CAutoHideDockSite`.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sucht die Zeile mit `pAutoHideToolbar`. Sie ruft `CMFCAutoHideBar.UnSetAutoHideMode` für alle der `CMFCAutoHideBar` Objekte in dieser Zeile. Wenn `pAutoHideToolbar` wurde nicht gefunden oder ist `NULL`, diese Methode ruft `CMFCAutoHideBar.UnSetAutoHideMode` für alle der `CMFCAutoHideBar` Objekte auf der `CAutoHideDockSite`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)
