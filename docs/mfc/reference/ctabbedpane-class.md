---
title: CTabbedPane Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs:
- C++
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9da7016e98d9bd84e62c3b05cae32346827142f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121837"
---
# <a name="ctabbedpane-class"></a>CTabbedPane-Klasse
Implementiert die Funktionalität eines Bereichs mit abtrennbaren Registerkarten.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CTabbedPane::CTabbedPane`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabbedPane::DetachPane](#detachpane)|(Überschreibt [cbasetabbedpane:: Detachpane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|  
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Aktiviert oder deaktiviert die automatische Registerkartenfärbung.|  
|[CTabbedPane::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet. (Überschreibt [cbasetabbedpane:: Floattab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CTabbedPane::GetTabArea](#gettabarea)|Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück.|  
|[CTabbedPane::GetTabWnd](#gettabwnd)||  
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Bestimmt, ob der Bereich im Registerkartenformat automatisch in den Hintergrundmodus gewechselt werden kann. (Überschreibt [cbasetabbedpane:: Hasautohidemode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|  
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Bestimmt, ob sich die Registerkarten am unteren Rand des Fensters befinden.|  
|[CTabbedPane::ResetTabs](#resettabs)|Setzt alle Bereiche im Registerkartenformat auf den Standardstatus zurück.|  
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Legt eine Liste benutzerdefinierter Farben fest, die verwendet werden kann, wenn die Funktion für automatische Farben aktiviert ist.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Die Standardposition für Registerkarten in der Anwendung.|  
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Laufzeitklasseninformationen für ein benutzerdefiniertes `CMFCTabCtrl`-abgeleitetes Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Das Framework erstellt automatisch eine Instanz dieser Klasse, wenn ein Benutzer einen Bereich an einen anderen anfügt, indem es auf die Beschriftung des zweiten Bereichs verweist. Alle der vom Framework erstellten Bereiche im Registerkartenformat besitzen eine ID von "-1".  
  
 Um normale Registerkarten anstatt von Registerkarten im Outlook-Format anzugeben, übergeben Sie die Formatvorlage AFX_CBRS_REGULAR_TABS, die [CDockablePane:: CreateEx](../../mfc/reference/cdockablepane-class.md#createex) Methode.  
  
 Wenn Sie einen Bereich im Registerkartenformat mit abtrennbaren Registerkarten erstellen, kann der Bereich automatisch durch das Framework zerstört werden. Speichern Sie daher nicht den Zeiger. Um einen Zeiger zum Bereich im Registerkartenformat zu erhalten, rufen Sie die `CBasePane::GetParentTabbedPane`-Methode auf.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel erstellen wir ein `CTabbedPane`-Objekt. Als Nächstes verwenden wir [cbasetabbedpane:: addTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) um zusätzliche Registerkarten anzufügen.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),  
    TRUE, 
 (UINT) -1,  
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
    WS_CLIPCHILDREN | CBRS_LEFT |    
    CBRS_FLOAT_MULTI)) 
{  
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create  
}  
 
pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```  
  
## <a name="example"></a>Beispiel  
 So erstellen ein Steuerleistenobjekt im Registerkartenformat eine andere Möglichkeit ist die Verwendung [CDockablePane:: Attachtotabwnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). Die `AttachToTabWnd` -Methode erstellt dynamisch ein Bereichsobjekt im Registerformat mithilfe von festgelegten laufzeitklasseninformationen [CDockablePane:: Settabbedpanertc](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).  
  
 In diesem Beispiel erstellen wir einen dynamischen Bereich im Registerkartenformat, fügen zwei Registerkarten an und legen die zweite Registerkarte als nicht entfernbar fest.  
  
```  
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTabbedPane.h  
  
##  <a name="detachpane"></a>  CTabbedPane::DetachPane  

  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 [in] *bHide*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletabautocolor"></a>  CTabbedPane::EnableTabAutoColor  
 Aktiviert oder deaktiviert die automatische Registerkartenfärbung.  
  
```  
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 True, um die automatische registerkartenfärbung zu aktivieren. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese statische Methode zum Aktivieren oder deaktivieren die automatische registerkartenfärbung in alle Bereiche im Registerkartenformat in der Anwendung. Wenn diese Funktion aktiviert ist, wird jede Registerkarte durch eine eigene Farbe gefüllt. Sie finden die Liste der Farben, die verwendet werden, um die Farbe der Registerkarten durch Aufrufen der [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) Methode.  
  
 Sie können angeben, die Liste der Farben, die durch den Aufruf für Registerkarten verwendet werden [CTabbedPane::SetTabAutoColors](#settabautocolors).  
  
 Standardmäßig ist diese Option deaktiviert.  
  
##  <a name="floattab"></a>  CTabbedPane::FloatTab  

  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 [in] *nTabID*  
 [in] *DockMethod*  
 [in] *bHide*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabarea"></a>  CTabbedPane::GetTabArea  
 Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] *RectTabAreaTop*  
 Enthält die Größe und Position in Bildschirmkoordinaten des oberen Registerkartenbereichs.  
  
 [out] *RectTabAreaBottom*  
 Enthält die Größe und Position des Registerkartenbereichs unteren Bereich, in Bildschirmkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, wie einen Bereich anzudocken, den ein Benutzer gezogen wird. Wenn der Benutzer einen Bereich auf der Registerkarte "Zielbereich" "des bewegt, versucht das Framework für die hinzuzufügende als neue Registerkarte des Bereichs" Ziel ". Andernfalls wird versucht, den Bereich auf den Rand des Bereichs Ziel anzudocken die umfasst das Erstellen eines neuen Bereich-Containers mit einer bereichsteiler, der die beiden Bereiche trennt.  
  
 Überschreiben Sie diese Methode in einer `CTabbedPane`-abgeleitete Klasse, um dieses Verhalten zu ändern.  
  
##  <a name="gettabwnd"></a>  CTabbedPane::GetTabWnd  

  
```  
CMFCTabCtrl* GetTabWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hasautohidemode"></a>  CTabbedPane::HasAutoHideMode  

  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="istablocationbottom"></a>  CTabbedPane::IsTabLocationBottom  
 Bestimmt, ob sich die Registerkarten am unteren Rand des Fensters befinden.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Registerkartenbereich am unteren Rand des Fensters im Registerkartenformat befindet. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_btabsalwaystop"></a>  CTabbedPane::m_bTabsAlwaysTop  
 Die Standardposition für Registerkarten in der Anwendung.  
  
```  
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses statische Element auf "true" erzwingen, die alle Registerkarten in der Anwendung, die am oberen Rand der Seite im Registerformat angezeigt werden.  
  
 Dieser Wert muss festgelegt werden, bevor Sie ein Bereich im Registerkartenformat erstellt wurde.  
  
 Der Standardwert ist "false".  
  
##  <a name="m_ptabwndrtc"></a>  CTabbedPane::m_pTabWndRTC  
 Laufzeitklasseninformationen für ein benutzerdefiniertes `CMFCTabCtrl`-abgeleitetes Objekt.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diese statische Membervariable in einen Zeiger auf die laufzeitklasseninformationen eine `CMFCTabCtrl`-abgeleitetes Objekt aus, wenn Sie ein benutzerdefiniertes Fenster im Registerkartenformat in einem Bereich mit Registerkarten verwenden.  
  
##  <a name="resettabs"></a>  CTabbedPane::ResetTabs  
 Setzt alle Bereiche im Registerkartenformat auf den Standardstatus zurück.  
  
```  
static void ResetTabs();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um alle Bereiche im Registerkartenformat auf ihren Standardzustand zurückgesetzt. Wenn aufgerufen wird, setzt diese Methode die Border-Größe und Farbe Status alle Bereiche im Registerkartenformat automatisch zurück.  
  
##  <a name="settabautocolors"></a>  CTabbedPane::SetTabAutoColors  
 Legt eine Liste benutzerdefinierter Farben, die verwendet werden, wenn die Funktion für automatische Farben aktiviert ist.  
  
```  
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *ArColors*  
 Enthält das Array der Farben festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Liste der Farben anpassen, die verwendet werden, wenn die Funktion für automatische Farben aktiviert ist. Dies ist eine statische Funktion und wirkt sich auf alle im Registerkartenformat Bereiche in der Anwendung.  
  
 Verwendung [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) aktivieren oder Deaktivieren der Funktion für automatische Farben.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)
