---
title: CPane-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPane
- AFXPANE/CPane
- AFXPANE/CPane::AdjustSizeImmediate
- AFXPANE/CPane::AllocElements
- AFXPANE/CPane::AllowShowOnPaneMenu
- AFXPANE/CPane::CalcAvailableSize
- AFXPANE/CPane::CalcInsideRect
- AFXPANE/CPane::CalcRecentDockedRect
- AFXPANE/CPane::CalcSize
- AFXPANE/CPane::CanBeDocked
- AFXPANE/CPane::CanBeTabbedDocument
- AFXPANE/CPane::ConvertToTabbedDocument
- AFXPANE/CPane::CopyState
- AFXPANE/CPane::Create
- AFXPANE/CPane::CreateDefaultMiniframe
- AFXPANE/CPane::CreateEx
- AFXPANE/CPane::DockByMouse
- AFXPANE/CPane::DockPane
- AFXPANE/CPane::DockPaneStandard
- AFXPANE/CPane::DockToFrameWindow
- AFXPANE/CPane::DoesAllowSiblingBars
- AFXPANE/CPane::FloatPane
- AFXPANE/CPane::GetAvailableExpandSize
- AFXPANE/CPane::GetAvailableStretchSize
- AFXPANE/CPane::GetBorders
- AFXPANE/CPane::GetClientHotSpot
- AFXPANE/CPane::GetDockSiteRow
- AFXPANE/CPane::GetExclusiveRowMode
- AFXPANE/CPane::GetHotSpot
- AFXPANE/CPane::GetMinSize
- AFXPANE/CPane::GetPaneName
- AFXPANE/CPane::GetVirtualRect
- AFXPANE/CPane::IsChangeState
- AFXPANE/CPane::IsDragMode
- AFXPANE/CPane::IsInFloatingMultiPaneFrameWnd
- AFXPANE/CPane::IsLeftOf
- AFXPANE/CPane::IsResizable
- AFXPANE/CPane::IsTabbed
- AFXPANE/CPane::LoadState
- AFXPANE/CPane::MoveByAlignment
- AFXPANE/CPane::MovePane
- AFXPANE/CPane::OnAfterChangeParent
- AFXPANE/CPane::OnBeforeChangeParent
- AFXPANE/CPane::OnPressCloseButton
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::RecalcLayout
- AFXPANE/CPane::SaveState
- AFXPANE/CPane::SetActiveInGroup
- AFXPANE/CPane::SetBorders
- AFXPANE/CPane::SetClientHotSpot
- AFXPANE/CPane::SetDockState
- AFXPANE/CPane::SetExclusiveRowMode
- AFXPANE/CPane::SetMiniFrameRTC
- AFXPANE/CPane::SetMinSize
- AFXPANE/CPane::SetVirtualRect
- AFXPANE/CPane::StretchPaneDeferWndPos
- AFXPANE/CPane::ToggleAutoHide
- AFXPANE/CPane::UndockPane
- AFXPANE/CPane::UpdateVirtualRect
- AFXPANE/CPane::OnAfterDock
- AFXPANE/CPane::OnAfterFloat
- AFXPANE/CPane::OnBeforeDock
- AFXPANE/CPane::OnBeforeFloat
- AFXPANE/CPane::m_bHandleMinSize
- AFXPANE/CPane::m_recentDockInfo
dev_langs:
- C++
helpviewer_keywords:
- CPane class
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
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
ms.openlocfilehash: 586133277aa4a9d89ca15cdd496a1ca7e4232632
ms.lasthandoff: 02/24/2017

---
# <a name="cpane-class"></a>CPane Class
Die `CPane` Klasse ist eine Erweiterung von der [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md). Wenn Sie ein vorhandenen MFC-Projekt aktualisieren, ersetzen Sie alle Vorkommen von `CControlBar` mit `CPane`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CPane::~CPane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Sofort neu berechnet das Layout eines Bereichs ein.|  
|[CPane::AllocElements](#allocelements)|Belegt Speicher für die interne Verwendung.|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Gibt an, ob der Bereich in der Laufzeit generierte Liste von Bereichen für die Anwendung aufgelistet ist.|  
|[CPane::CalcAvailableSize](#calcavailablesize)|Berechnet den Unterschied zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck in der Größe.|  
|[CPane::CalcInsideRect](#calcinsiderect)|Berechnet die innere Rechteck eines Bereichs, der unter Berücksichtigung der Rahmen und ziehelemente.|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Berechnet das vor kurzem angedockte Rechteck.|  
|[CPane::CalcSize](#calcsize)|Berechnet die Größe des Bereichs.|  
|[CPane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich der angegebenen Basis Bereich angedockt werden kann.|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.|  
|[CPane::CopyState](#copystate)|Kopiert den Status eines Bereichs an. (Überschreibt [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|  
|[CPane::Create](#create)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|  
|[Cpane:: Createdefaultminiframe](#createdefaultminiframe)|Erstellt ein Minirahmenfenster für ein nicht verankertes Fenster.|  
|[Cpane:: CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|  
|`CPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CPane::DockByMouse](#dockbymouse)|Wird einen Bereich mit der Maus Andocken Methode angedockt.|  
|[CPane::DockPane](#dockpane)|Die Gleitkommazahlen im Bereich einer Basis Bereich angedockt.|  
|[CPane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) andocken.|  
|[CPane::DockToFrameWindow](#docktoframewindow)|Ein Frame ein andockbares Fenster angedockt. (Überschreibt `CBasePane::DockToFrameWindow`.)|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile angedockt werden können, wo der aktuelle Bereich angedockt wird.|  
|[CPane::FloatPane](#floatpane)|Befindet sich im Bereich.|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Gibt die Menge in Pixel an, die den Bereich zu erweitern.|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Gibt die Menge in Pixel an, die im Bereich Größe verkleinert werden kann.|  
|[CPane::GetBorders](#getborders)|Gibt die Breite des Rahmens des Bereichs zurück.|  
|[CPane::GetClientHotSpot](#getclienthotspot)|Gibt die *Hotspot* für den Bereich.|  
|[CPane::GetDockSiteRow](#getdocksiterow)|Gibt die Dock-Zeile in der Bereich angedockt ist.|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Bestimmt, ob der Bereich im exklusiven Modus ist.|  
|[CPane::GetHotSpot](#gethotspot)|Gibt den Hotspot, die in einer zugrunde liegenden gespeichert ist `CMFCDragFrameImpl` Objekt.|  
|[CPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab.|  
|[CPane::GetPaneName](#getpanename)|Ruft den Titel für den Bereich ab.|  
|`CPane::GetResizeStep`|Wird intern verwendet.|  
|`CPane::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CPane::GetVirtualRect](#getvirtualrect)|Ruft die *virtuellen Rechteck* des Bereichs.|  
|[CPane::IsChangeState](#ischangestate)|Während der Bereich verschoben wird, diese Methode die Position des Bereichs relativ zu anderen Bereichen, Dock Zeilen und Minirahmenfenster analysiert und gibt den entsprechenden `AFX_CS_STATUS` Wert.|  
|[CPane::IsDragMode](#isdragmode)|Gibt an, ob der Bereich gezogen wird.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen. (Überschreibt `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|  
|[CPane::IsLeftOf](#isleftof)|Bestimmt, ob der Bereich nach links (oder höher) des angegebenen Rechtecks.|  
|[CPane::IsResizable](#isresizable)|Bestimmt, ob der Bereich angepasst werden kann. (Überschreibt [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CPane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich in das Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde. (Überschreibt [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|  
|[CPane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung. (Überschreibt [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|  
|[CPane::MoveByAlignment](#movebyalignment)|Verschiebt den Bereich und das virtuelle Rechteck um den angegebenen Betrag.|  
|[CPane::MovePane](#movepane)|Verschiebt den Bereich im angegebenen Rechteck.|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert hat.|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf die Beschriftung für den Bereich auswählt.|  
|`CPane::OnProcessDblClk`|Wird intern verwendet.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|  
|`CPane::PrepareToDock`|Wird intern verwendet.|  
|[Cpane:: RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich. (Überschreibt [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|  
|[CPane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung. (Überschreibt [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|  
|[CPane::SetActiveInGroup](#setactiveingroup)|Kennzeichnet einen Bereich als aktiv.|  
|[CPane::SetBorders](#setborders)|Legt die rahmenwerte der Bereich fest.|  
|[CPane::SetClientHotSpot](#setclienthotspot)|Legt den Hotspot für den Bereich fest.|  
|[CPane::SetDockState](#setdockstate)|Stellt Statusinformationen für den Bereich andocken.|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Aktiviert oder deaktiviert die exklusiven Modus.|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|Legt die Laufzeit-Klasseninformationen für das Standard-Minirahmenfenster fest.|  
|[CPane::SetMinSize](#setminsize)|Legt den minimal zulässigen Größe für den Bereich fest.|  
|[CPane::SetVirtualRect](#setvirtualrect)|Legt die *virtuellen Rechteck* des Bereichs.|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Streckt Bereich vertikal oder horizontal anhand Stil andocken.|  
|[CPane::ToggleAutoHide](#toggleautohide)|Schaltet das automatische Ausblenden Modus.|  
|[CPane::UndockPane](#undockpane)|Entfernt im Bereich von docksite, Standard-Schieberegler oder Minirahmenfenster, in denen es derzeit angedockt ist. (Überschreibt [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Aktualisiert das virtuelle Rechteck.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|Wird vom Framework aufgerufen, wenn ein Bereich angedockt wurden.|  
|[CPane::OnAfterFloat](#onafterfloat)|Wird vom Framework aufgerufen, wenn ein Bereich abgedockt wurde.|  
|[CPane::OnBeforeDock](#onbeforedock)|Vom Framework aufgerufen, wenn der Bereich ist angedockt werden.|  
|[CPane::OnBeforeFloat](#onbeforefloat)|Wird vom Framework aufgerufen, wenn ein Bereich wird abgedockt werden.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|Ermöglicht die konsistente Behandlung von die minimale Größe für Bereiche.|  
|[CPane::m_recentDockInfo](#m_recentdockinfo)|Enthält aktuellen docking Informationen.|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel `CPane` Objekte werden nicht direkt instanziiert werden. Wenn Sie einen Bereich, das Andocken Funktionalität verfügt benötigen, leiten Sie das Objekt aus [CDockablePane](../../mfc/reference/cdockablepane-class.md). Wenn Sie Toolbar-Funktionalität benötigen, leiten Sie das Objekt aus [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Beim Ableiten einer Klasse von `CPane`, können angedockt werden, einem [CDockSite](../../mfc/reference/cdocksite-class.md) und es kann abgedockt werden eine [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>CPane::AdjustSizeImmediate  
 Sofort neu berechnet das Layout eines Bereichs ein.  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bRecalcLayout`  
 `TRUE`Das Layout der im Bereich automatisch neu berechnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen Sie diese Methode wird, wenn Sie dynamisch das Layout eines Bereichs ändern. Zum Beispiel: Sie möchten diese Methode aufrufen, wenn Sie aus- oder Einblenden von Symbolleisten-Schaltflächen.  
  
##  <a name="allocelements"></a>CPane::AllocElements  
 Belegt Speicher für die interne Verwendung.  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nElements`  
 Die Anzahl der Elemente, für die Speicher reserviert werden.  
  
 [in] `cbElement`  
 Die Größe des Elements in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE`Wenn die speicherbelegung fehlschlägt. andernfalls `TRUE`.  
  
##  <a name="allowshowonpanemenu"></a>CPane::AllowShowOnPaneMenu  
 Gibt an, ob der Bereich in der Laufzeit generierte Liste von Bereichen für die Anwendung aufgelistet ist.  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in der Liste angezeigt wird; andernfalls `FALSE`. Die grundlegende Implementierung gibt immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Der AppWizard generierte Anwendung enthält eine Menüoption, die Bereiche aufgeführt, die es enthält. Diese Methode bestimmt, ob der Bereich in der Liste angezeigt wird.  
  
##  <a name="calcavailablesize"></a>CPane::CalcAvailableSize  
 Berechnet den Unterschied zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck in der Größe.  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectRequired`  
 Das erforderliche Rechteck.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Unterschied in der Breite und Höhe zwischen `rectRequired` und das aktuelle Fenster Rechteck.  
  
##  <a name="calcinsiderect"></a>CPane::CalcInsideRect  
 Berechnet die innere Rechteck eines Bereichs, einschließlich der Rahmen und ziehelemente.  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Enthält die Größe und den Offset des Clientbereichs des Bereichs.  
  
 [in] `bHorz`  
 `TRUE`Wenn der Bereich horizontal ausgerichtet ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn das Layout für einen Bereich neu berechnet werden kann. Die `rect` Parameter mit der Größe und den Offset des Clientbereichs des Bereichs gefüllt ist. Dies schließt die Rahmen und ziehelemente.  
  
##  <a name="calcrecentdockedrect"></a>CPane::CalcRecentDockedRect  
 Berechnet das vor kurzem angedockte Rechteck.  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert [CPane::m_recentDockInfo](#m_recentdockinfo).  
  
##  <a name="calcsize"></a>CPane::CalcSize  
 Berechnet die Größe des Bereichs.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVertDock`  
 `TRUE`ist der Bereich vertikal angedockt wird `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung dieser Methode gibt eine Größe von (0, 0).  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen sollten diese Methode überschreiben.  
  
##  <a name="canbedocked"></a>CPane::CanBeDocked  
 Bestimmt, ob der Bereich der angegebenen Basis Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Gibt den Bereich, in dem dieser Bereich befindet sich angedockt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn in diesem Bereich an der angegebenen andockbaren; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird normalerweise aufgerufen, durch das Framework zu bestimmen, ob ein Bereich an der angegebenen andockbaren Bereich angedockt werden kann. Aktiviert, um zu bestimmen, ob der Bereich angedockt werden kann, die Methode im Bereichs derzeit ergibt andockbaren Ausrichtung.  
  
 Sie aktivieren Sie das Andocken an die verschiedenen Seiten des Rahmenfensters durch Aufrufen von [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="canbetabbeddocument"></a>CPane::CanBeTabbedDocument  
 Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` , wenn Sie verhindern möchten, einen Bereich in ein Dokument im Registerkartenformat konvertiert wird. Ein Dokument im Registerkartenformat werden in die Position des Fensters im Menü nicht angezeigt werden.  
  
##  <a name="converttotabbeddocument"></a>CPane::ConvertToTabbedDocument  
 Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Nicht verwendet in `CPane::ConvertToTabbedDocument`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können auf Dokumente im Registerformat konvertiert werden. Weitere Informationen finden Sie unter [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).  
  
##  <a name="copystate"></a>CPane::CopyState  
 Kopiert den Status eines Bereichs an.  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOrgBar`  
 Ein Zeiger auf einen Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Zustand des `pOrgBar` in den aktuellen Bereich.  
  
##  <a name="create"></a>CPane::Create  
 Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszClassName`  
 Gibt den Namen der Windows-Klasse.  
  
 [in] `dwStyle`  
 Gibt die Stilattribute Fenster an. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der der `pParentWnd` Fenster, in Clientkoordinaten.  
  
 [in] [out]`pParentWnd`  
 Gibt das übergeordnete Fenster des in diesem Bereich an.  
  
 [in] `nID`  
 Gibt die ID des Bereichs.  
  
 [in] `dwControlBarStyle`  
 Gibt den Stil für den Bereich. Weitere Informationen finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out]`pContext`  
 Gibt den Kontext Erstellen des Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.  
  
 Wenn Sie nicht explizit initialisiert haben [CPane::m_recentDockInfo](#m_recentdockinfo) vor dem Aufruf von `Create`, den Parameter `rect` verwendet werden, wie das Rechteck beim Gleitkommazahl oder Bereich andocken.  
  
##  <a name="createdefaultminiframe"></a>Cpane:: Createdefaultminiframe  
 Erstellt ein Minirahmenfenster für ein nicht verankertes Fenster.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectInitial`  
 Gibt die ursprüngliche Größe und Position in Bildschirmkoordinaten, das Minirahmenfenster erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neu erstellte Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework ein Minirahmenfenster zu erstellen, wenn ein Bereich umfließt wird aufgerufen. Das Minirahmenfenster kann vom Typ [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) oder vom Typ [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Ein Minirahmenfenster mit mehreren wird erstellt, wenn im Bereich der `AFX_CBRS_FLOAT_MULTI` Stil.  
  
 Die Laufzeit-Klasseninformationen für das Minirahmenfenster befindet sich in der `CPane::m_pMiniFrameRTC` Member. Eine abgeleitete Klasse können Sie dieses Element festlegen, wenn Sie benutzerdefinierte Minirahmenfenster erstellen möchten.  
  
##  <a name="createex"></a>Cpane:: CreateEx  
 Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyleEx`  
 Gibt die erweiterten Stilattribute. Weitere Informationen finden Sie unter [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md).  
  
 [in] `lpszClassName`  
 Gibt den Namen der Windows-Klasse.  
  
 [in] `dwStyle`  
 Gibt die Formatattribute Fenster. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Gibt die ursprüngliche Größe und Position der der `pParentWnd` Fenster, in Clientkoordinaten.  
  
 [in] [out]`pParentWnd`  
 Gibt das übergeordnete Fenster des in diesem Bereich an.  
  
 [in] `nID`  
 Gibt die ID des Bereichs.  
  
 [in] `dwControlBarStyle`  
 Gibt den Stil für den Bereich. Weitere Informationen finden Sie unter [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out]`pContext`  
 Gibt den erstellen-Kontext für den Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.  
  
 Wenn Sie nicht explizit initialisiert haben [CPane::m_recentDockInfo](#m_recentdockinfo) vor dem Aufruf von `CreateEx`, den Parameter `rect` verwendet werden, wie das Rechteck beim Gleitkommazahl oder Bereich andocken.  
  
##  <a name="dockbymouse"></a>CPane::DockByMouse  
 Dockt einen Bereich mit der Maus.  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Gibt die Basis Bereich, der in diesem Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
##  <a name="dockpane"></a>CPane::DockPane  
 Die Gleitkommazahlen im Bereich einer Basis Bereich angedockt.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pDockBar`  
 Gibt base Bereich um diesem Bereich anzudocken.  
  
 [in] `lpRect`  
 Gibt das Rechteck auf der Basis Bereich, in dem dieser Bereich befindet sich angedockt werden.  
  
 [in] `dockMethod`  
 Gibt die Dockingstation Methode verwenden. Die verfügbaren Optionen lauten folgendermaßen:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`DM_UNKNOWN`|Das Framework verwendet diese Option, wenn die Dockingstation Methode bekannt ist. Die aktuellste schwebende Position im Bereich nicht gespeichert. Diese Option können auch um einen Bereich programmgesteuert zu verankern, wenn Sie nicht zum Speichern der aktuellen schwebenden Position verfügen.|  
|`DM_MOUSE`|Wird intern verwendet.|  
|`DM_DBL_CLICK`|Diese Option wird verwendet, wenn die Ziehpunkte doppelgeklickt wird. Der Bereich wird an der Position des letzten andockbaren neu positioniert. Wenn der Bereich durch Doppelklicken auf abgedockt ist, wird im Bereich an der Position des letzten schwebenden neu positioniert.|  
|`DM_SHOW`|Diese Option kann verwendet werden, um programmgesteuert auf den Bereich anzudocken. Im Bereich wird die aktuellste schwebende Position gespeichert.|  
|`DM_RECT`|Im Bereich in der Region, der von angegebene angedockt ist `lpRect`.|  
|`DM_STANDARD`|Wenn Sie diese Option verwenden, zeichnet das Framework Bereich als eine Gliederung Frame, während es verschoben wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode Dockt den Bereich an, in den Basis-Bereich, der durch angegeben ist die `pDockBar` Parameter. Sie müssen zuerst aktivieren, durch Aufrufen von Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="dockpanestandard"></a>CPane::DockPaneStandard  
 Dockt einen Bereich mithilfe der Gliederung (standard) andocken.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bWasDocked`  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer den `this` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur für Bereiche, die von abgeleitet sind verwendet die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md). Weitere Informationen finden Sie unter [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).  
  
##  <a name="docktoframewindow"></a>CPane::DockToFrameWindow  
 Ein Frame ein andockbares Fenster angedockt.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Die Seite des übergeordneten Frames, die Sie im Bereich zum andocken möchten.  
  
 [in] `lpRect`  
 Die angegebene Größe.  
  
 [in] `dwDockFlags`  
 Ignoriert.  
  
 [in] `pRelativeBar`  
 Ignoriert.  
  
 [in] `nRelativeIndex`  
 Ignoriert.  
  
 [in] `bOuterEdge`  
 Wenn `TRUE` , und es gibt andere andockbare Bereiche auf der Seite mit den vom angegebenen `dwAlignment`, der Bereich außerhalb der anderen Bereiche angedockt wird näher an den Rand des übergeordneten Rahmens. Wenn `FALSE`, im Bereich in der Mitte des Clientbereichs näher angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE`Wenn eine Trennlinie ( [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md)), andernfalls nicht `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="doesallowsiblingbars"></a>CPane::DoesAllowSiblingBars  
 Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile angedockt werden können, wo der aktuelle Bereich angedockt wird.  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn in diesem Bereich in einen anderen Bereich auf derselben Zeile wie selbst angedockt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können aktivieren oder deaktivieren Sie dieses Verhalten durch Aufrufen von [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
 Standardmäßig Symbolleisten exklusiven Modus deaktiviert haben, und die Menüleiste exklusiven Modus aktiviert ist.  
  
##  <a name="floatpane"></a>CPane::FloatPane  
 Befindet sich im Bereich.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Position in Bildschirmkoordinaten um Bereich zu positionieren, wenn sie abgedockt ist.  
  
 [in] `dockMethod`  
 Gibt die Dockingstation Methode zu verwenden, wenn der Bereich umfließt ist. Eine Liste der möglichen Werte finden Sie unter [CPane::DockPane](#dockpane).  
  
 [in] `bShow`  
 `TRUE`der Bereich umfließt angezeigt; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich abgedockt wurde oder im Bereich da umfließt kann nicht [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) gibt `FALSE`, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Bereich an der Position float, der durch angegeben ist die `rectFloat` Parameter. Diese Methode erstellt automatisch eine übergeordnete Minirahmenfenster für den Bereich.  
  
##  <a name="getavailableexpandsize"></a>CPane::GetAvailableExpandSize  
 Gibt die Menge in Pixel an, die den Bereich zu erweitern.  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Bereich horizontal angedockt ist, ist der Rückgabewert der verfügbaren Breite; Andernfalls ist der Rückgabewert der verfügbaren Höhe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getavailablestretchsize"></a>CPane::GetAvailableStretchSize  
 Gibt die Menge in Pixel an, die im Bereich Größe verkleinert werden kann.  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Betrag in Pixel an, die im Bereich Größe verkleinert werden kann. Wenn Bereich horizontal angedockt ist, ist diese Menge der verfügbaren Breite. Andernfalls ist es der verfügbaren Höhe.  
  
### <a name="remarks"></a>Hinweise  
 Die Stretch verfügbare Größe wird berechnet, indem den minimal zulässigen Größe für den Bereich ( [CPane::GetMinSize](#getminsize)) von der aktuellen Größe ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).  
  
##  <a name="getborders"></a>CPane::GetBorders  
 Gibt die Breite des Rahmens des Bereichs zurück.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die aktuelle Breite des jeder Seite des Bereichs in Pixel enthält. Z. B. der Wert der `left` Mitglied der `CRect` -Objekt ist die Breite des linken Rahmens.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Festlegen der Größe der Rahmen [CPane::SetBorders](#setborders).  
  
##  <a name="getclienthotspot"></a>CPane::GetClientHotSpot  
 Gibt die *Hotspot* für den Bereich.  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die *Hotspot* ist der Punkt auf den Bereich, den der Benutzer auswählt, und verschieben Sie den Bereich enthält. Ein Hotspot wird für flüssige Animation verwendet, wenn im Bereich von einer verankerten Position verschoben wird.  
  
##  <a name="getdocksiterow"></a>CPane::GetDockSiteRow  
 Gibt die Zeile andocken ( [CDockingPanesRow Klasse](../../mfc/reference/cdockingpanesrow-class.md)) in dem Bereich angedockt ist.  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CDockingPanesRow`*, verweist auf die Dock-Zeile in dem Bereich angedockt ist, oder `NULL` , wenn der Bereich nicht angedockt ist.  
  
##  <a name="getexclusiverowmode"></a>CPane::GetExclusiveRowMode  
 Bestimmt, ob der Bereich im exklusiven Modus ist.  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich im exklusiven Modus wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu exklusiven Modus, finden Sie unter [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
##  <a name="gethotspot"></a>CPane::GetHotSpot  
 Gibt den Hotspot, die in einer zugrunde liegenden gespeichert ist `CMFCDragFrameImpl` Objekt.  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die `CPane` -Klasse enthält eine `CMFCDragFrameImpl` Objekt `m_dragFrameImpl`, d. h. dafür verantwortlich, zeichnen das Rechteck, das angezeigt wird, wenn der Benutzer einen Bereich in der standardmäßigen Andockmodus bewegt. Der Hotspot dient zum Zeichnen des Rechtecks relativ zu der aktuellen Position, wenn der Benutzer im Bereich bewegt.  
  
##  <a name="getminsize"></a>CPane::GetMinSize  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanename"></a>CPane::GetPaneName  
 Ruft den Titel für den Bereich ab.  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strName`  
 Ein `CString` -Objekt, das mit den Beschriftungsnamen gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Bereich Titel wird im Headerbereich angezeigt, wenn der Bereich angedockt oder unverankert ist. Wenn der Bereich einer Gruppe im Registerkartenformat gehört, wird der Titel in der Registerkarte angezeigt. Wenn der Bereich automatisch ausgeblendet wird, wird der Titel angezeigt, auf eine `CMFCAutoHideButton`.  
  
##  <a name="getvirtualrect"></a>CPane::GetVirtualRect  
 Ruft die *virtuellen Rechteck* des Bereichs.  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectVirtual`  
 Ein `CRect` -Objekt, das mit dem virtuellen Rechteck ausgefüllt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Bereich verschoben wird, speichert das Framework die ursprüngliche Position des Bereichs in einem virtuellen Rechteck. Das Framework können virtuelle Rechtecks zum Wiederherstellen der ursprünglichen Position des Bereichs.  
  
 Rufen Sie Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben.  
  
##  <a name="ischangestate"></a>CPane::IsChangeState  
 Während der Bereich verschoben wird, diese Methode analysiert seine Position relativ zu anderen Bereichen, Dock Zeilen und Minirahmenfenster und gibt den entsprechenden `AFX_CS_STATUS` Wert.  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Gibt andockbaren Empfindlichkeit an. Z. B. einen Bereich, der innerhalb verschoben wird `nOffset` Pixel in einer Zeile Andocken angedockt werden.  
  
 [in] `ppTargetBar`  
 Wenn die Methode zurückkehrt, `ppTargetBar` enthält entweder einen Zeiger auf das Objekt, der aktuelle Bereich angedockt werden soll, oder `NULL` , wenn keine Zuordnung erfolgen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine der folgenden `AFX_CS_STATUS` Werte:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CS_NOTHING`|Der Bereich ist nicht in der Nähe einer docksite. Das Framework ist nicht im Bereich andocken.|  
|`CS_DOCK_IMMEDIATELY`|Der Bereich wird über eine docksite und `DT_IMMEDIATE` -Stil ist aktiviert. Das Framework Dockt den Bereich sofort an.|  
|`CS_DELAY_DOCK`|Der Bereich wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe ist. Das Framework Dockt den Bereich an, wenn der Benutzer die Verschiebung loslässt.|  
|`CS_DELAY_DOCK_TO_TAB`|Der Bereich wird über eine docksite, bei dem der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Bereich über die Beschriftung des anderen andockbaren Bereich oder über den Registerkartenbereich für ein Fenster mit Registerkarten. Das Framework Dockt den Bereich an, wenn der Benutzer die Verschiebung loslässt.|  
  
##  <a name="isdragmode"></a>CPane::IsDragMode  
 Gibt an, ob der Bereich verschoben wird.  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich verschoben wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CPane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in einem Rahmenfenster mit mehreren Bereichen wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in einem Rahmenfenster mit mehreren Bereichen float. Aus diesem Grund `CPane::IsInFloatingMultiPaneFrameWnd` gibt immer `FALSE`.  
  
##  <a name="isleftof"></a>CPane::IsLeftOf  
 Bestimmt, ob der Bereich nach links (oder höher) des angegebenen Rechtecks.  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Ein `CRect` -Objekt, das für den Vergleich verwendet wird.  
  
 [in] `bWindowRect`  
 Wenn `TRUE`, `rect` wird davon ausgegangen, dass enthalten Bildschirmkoordinaten; Wenn `FALSE`, `rect` wird davon ausgegangen, dass Clientkoordinaten enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Ist der Bereich horizontal angedockt, diese Methode überprüft, ob die Position links ist `rect`. Andernfalls diese Methode überprüft, ob der Speicherort über `rect`.  
  
##  <a name="isresizable"></a>CPane::IsResizable  
 Gibt an, ob der Bereich geändert werden.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich geändert wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Base `CPane` Objekte sind nicht geändert werden kann.  
  
 Der docking-Manager verwendet das in der Größe veränderbaren Flag Bereichslayout festzulegen. Nicht mit veränderbarer Größe Bereiche befinden sich immer an den äußeren Kanten des übergeordneten Rahmens.  
  
 Bereiche mit veränderbarer Größe nicht können nicht in Container andocken befinden.  
  
##  <a name="istabbed"></a>CPane::IsTabbed  
 Bestimmt, ob das Registerkarten-Steuerelement ein Fenster im Registerkartenformat Bereich eingefügt wurden.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich mit Registerkarten ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Status im Registerformat wird separat von der Gleitkommatyp behandelt angedockt und automatisch im Hintergrund Zustände.  
  
##  <a name="loadstate"></a>CPane::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `nIndex`  
 Profil-Index.  
  
 [in] `uiID`  
 Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand des Bereichs erfolgreich geladen wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Bereich Status aus der Registrierung laden. Überschreiben Sie diese in einer abgeleiteten Klasse zusätzliche Informationen zu laden, die durch gespeichert wird, [CPane::SaveState](#savestate).  
  
 Wenn Sie diese Methode überschreiben, auch die Basismethode aufrufen und zurückgeben `FALSE` Wenn der Basismethode zurückgegeben `FALSE`.  
  
##  <a name="m_bhandleminsize"></a>CPane::m_bHandleMinSize  
 Ermöglicht die konsistente Behandlung von minimalen Bereich Größen.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine oder mehrere andockbare Bereiche in Ihrer Anwendung überschreiben `GetMinSize`, oder wenn die Anwendung aufruft `SetMinSize`, Sie möchten dieses statische Element auf festgelegt `TRUE` damit das Framework konsistent behandeln wie Bereiche angepasst werden können.  
  
 Wenn dieser Wert, um festgelegt wird `TRUE`, alle Bereiche, deren Größe unter die minimale Größe reduziert werden sollte, werden abgeschnitten, nicht gestreckt. Da das Framework Fensterbereiche für Bereich Größe verwendet, Ändern der Größe der Fensterbereich für andockbare Bereiche aus, wenn dieser Wert, um festgelegt wird nicht `TRUE`.  
  
##  <a name="m_recentdockinfo"></a>CPane::m_recentDockInfo  
 Enthält aktuellen docking Informationen.  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework speichert die neuesten andockbaren Statusinformationen für den Bereich in dieser Member.  
  
##  <a name="movebyalignment"></a>CPane::MoveByAlignment  
 Verschiebt den Bereich und das virtuelle Rechteck um den angegebenen Betrag.  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt im Bereich Ausrichtung.  
  
 [in] `nOffset`  
 Der Betrag in Pixel, um den Bereich und das virtuelle Rechteck verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment`die folgenden Werte sind möglich:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Ermöglicht der Bereich am Anfang der Clientbereich eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_BOTTOM`|Ermöglicht der Bereich am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_LEFT`|Ermöglicht der Bereich auf der linken Seite des Clientbereichs eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_RIGHT`|Ermöglicht der Bereich auf der rechten Seite des Clientbereichs eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_ANY`|Ermöglicht der Bereich auf jeder Seite des Clientbereichs eines Rahmenfensters angedockt werden.|  
  
 Wenn `dwAlignment` enthält die `CBRS_ALIGN_LEFT` oder `CBRS_ALIGN_RIGHT` Flag, das im Bereich und virtuellen Rechteck verschoben horizontal ist, andernfalls ist `dwAlignment` enthält die `CBRS_ALIGN_TOP` oder `CBRS_ALIGN_BOTTOM` Flag, das im Bereich und virtuellen Rechteck vertikal verschoben werden.  
  
##  <a name="movepane"></a>CPane::MovePane  
 Verschiebt den Bereich im angegebenen Rechteck.  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectNew`  
 Gibt das neue Rechteck für den Bereich.  
  
 [in] `bForceMove`  
 Wenn `TRUE`, diese Methode ignoriert die minimale zulässige Größe ( [CPane::GetMinSize](#getminsize)), andernfalls Bereich angepasst wird, falls erforderlich, um sicherzustellen, dass es mindestens den minimal zulässigen Größe ist.  
  
 [in] `hdwp`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` -Objekt, das die Breite und Höhe Unterschiede zwischen der alten und neuen Rechtecke enthält (alte Rechteck – `rectNew`).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist nur für andockbare Bereiche verwendet.  
  
##  <a name="onafterchangeparent"></a>CPane::OnAfterChangeParent  
 Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert hat.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pWndOldParent`  
 Im Bereich vorherigen übergeordneten Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs aufgrund eines Vorgangs andocken oder nicht geändert wurde.  
  
##  <a name="onafterdock"></a>CPane::OnAfterDock  
 Wird vom Framework aufgerufen, wenn ein Bereich angedockt wurden.  
  
```  
virtual void OnAfterDock(
    CBasePane* pBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `lpRect`  
 Dieser Parameter wird nicht verwendet.  
  
 [in] `dockMethod`  
 Dieser Parameter wird nicht verwendet.  
  
##  <a name="onafterfloat"></a>CPane::OnAfterFloat  
 Wird vom Framework aufgerufen, nachdem ein Bereich befindet.  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn die Verarbeitung auszuführen, nachdem ein Fenster gleitet werden soll.  
  
##  <a name="onbeforechangeparent"></a>CPane::OnBeforeChangeParent  
 Wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pWndNewParent`  
 Gibt den neuen übergeordneten Fenster.  
  
 [in] `bDelay`  
 `TRUE`verzögert die globale andockbaren Layout Anpassung; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs ist, zu ändern, da der Bereich wird angedockt oder abgedockt.  
  
 Im Bereich wird standardmäßig die andockbaren deregistriert durch Aufrufen von `CDockSite::RemovePane`.  
  
##  <a name="onbeforedock"></a>CPane::OnBeforeDock  
 Wird vom Framework aufgerufen, wenn der Bereich zum Andocken wird.  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`ppDockBar`  
 Gibt den Bereich, dem in diesem Bereich zum Andocken wird.  
  
 [in] `lpRect`  
 Gibt das Rechteck andocken.  
  
 [in] `dockMethod`  
 Gibt die Methode andocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich angedockt werden kann. Wenn die Funktion zurückgibt `FALSE`, der Andocken Vorgang wird abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Fenster ist angedockt werden. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, sollten Sie Verarbeitungsschritte auszuführen, bevor Sie schließlich ein Bereich angedockt ist.  
  
##  <a name="onbeforefloat"></a>CPane::OnBeforeFloat  
 Wird vom Framework aufgerufen, wenn ein Bereich in einen Gleitkommawert ist.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand ist.  
  
 [in] `dockMethod`  
 Gibt die Methode Andocken des Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich abgedockt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Bereich in einen Gleitkommawert ist. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Verarbeitungsschritte auszuführen, bevor schließlich Bereich gleitet werden soll.  
  
##  <a name="onpressclosebutton"></a>CPane::OnPressCloseButton  
 Wird vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf die Beschriftung für den Bereich drückt.  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer drückt die **schließen** auf den Titel des Bereichs. Empfangen von Benachrichtigungen über die **schließen** Ereignis, können Sie diese Methode in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="onshowcontrolbarmenu"></a>CPane::OnShowControlBarMenu  
 Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Speicherort im Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie im Menü angezeigt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Menü enthält mehrere Elemente, die Sie im Bereich Verhalten, nämlich angeben können: **Unverankert**, **Andocken**, **automatisch im Hintergrund**, und **ausblenden**. Sie können dieses Menü für alle Bereiche durch Aufrufen von [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).  
  
##  <a name="recalclayout"></a>Cpane:: RecalcLayout  
 Berechnet die Layoutinformationen für den Bereich.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich angedockt ist, aktualisiert diese Methode das virtuelle Rechteck für den Bereich durch Festlegen der Größe der aktuellen Größe des Bereichs.  
  
 Wenn der Bereich verankert ist, benachrichtigt diese Methode den übergeordneten Mini-Frame zum Anpassen der Größe des Bereichs auf die Größe des Mini-Frames. Das Framework stellt sicher, dass die Minirahmenfensters mindestens den minimal zulässigen Größe für den Bereich ( [CPane::GetMinSize](#getminsize)) und ändert die Größe der Minirahmenfensters bei Bedarf.  
  
##  <a name="savestate"></a>CPane::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `nIndex`  
 Profil-Index.  
  
 [in] `uiID`  
 Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn er den Zustand des Bereichs in der Registrierung speichert. Überschreiben Sie `SaveState` in einer abgeleiteten Klasse zum Speichern zusätzlicher Informationen.  
  
 Wenn Sie diese Methode überschreiben, auch die Basismethode aufrufen und zurückgeben `FALSE` Wenn der Basismethode zurückgegeben `FALSE`.  
  
##  <a name="setactiveingroup"></a>CPane::SetActiveInGroup  
 Kennzeichnet einen Bereich als aktiv.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 Ein `BOOL` , der angibt, ob der Bereich als aktiv gekennzeichnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein andockbares Fenster oder eine Schaltfläche automatisch im Hintergrund ausgewählt ist, wird der entsprechende Bereich automatisch im Hintergrund als aktiv gekennzeichnet.  
  
 Zwei Faktoren bildet die Grundlage für der Darstellung einer automatisch im Hintergrund-Schaltfläche, die dem Bereich zugeordnet ist. Wenn der Bereich aktiv ist und die `static``BOOL``CMFCAutoHideButton::m_bOverlappingTabs` ist `TRUE`, das Framework zeigt die Schaltfläche automatisch im Hintergrund als ein Symbol und eine Bezeichnung. Für einen inaktiven Bereich zeigt das Framework nur auf das Symbol automatisch im Hintergrund.  
  
 Wenn `CMFCAutoHideButton::m_bOverlappingTabs` ist `FALSE`, oder wenn der Bereich nicht in einer Gruppe befindet, zeigt das Framework die zugeordneten automatisch im Hintergrund-Schaltfläche als ein Symbol und eine Bezeichnung.  
  
##  <a name="setborders"></a>CPane::SetBorders  
 Legt die rahmenwerte der Bereich fest.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `cxLeft`  
 Gibt die Breite des linken Rahmens des Bereichs in Pixel an.  
  
 [in] `cyTop`  
 Gibt die Breite des oberen Rahmens des Bereichs in Pixel an.  
  
 [in] `cxRight`  
 Gibt die Breite des rechten Rand des Bereichs in Pixel an.  
  
 [in] `cyBottom`  
 Gibt die Breite des unteren Rahmens des Bereichs in Pixel an.  
  
 [in] `lpRect`  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Breite der einzelnen Rand des Bereichs in Pixel enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die Größe der Rahmen des Bereichs fest.  
  
##  <a name="setclienthotspot"></a>CPane::SetClientHotSpot  
 Legt die *Hotspot* für den Bereich.  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptNew`  
 Ein `CPoint` Objekt, das den neuen Hotspot angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Hotspot* ist der Punkt auf den Bereich, den der Benutzer auswählt, und verschieben Sie den Bereich enthält. Ein Hotspot wird für flüssige Animation verwendet, wenn der Bereich aus einer verankerten Position gezogen wird.  
  
##  <a name="setdockstate"></a>CPane::SetDockState  
 Stellt Statusinformationen für den Bereich andocken.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockManager`  
 Ein Zeiger auf den docking-Manager für das Hauptrahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aktuelle andockbaren Zustandsinformationen für den Bereich der wiederherzustellenden aufgerufen. Ein Bereich speichert aktuelle andockbaren Zustandsinformationen in [CPane::m_recentDockInfo](#m_recentdockinfo). Weitere Informationen finden Sie unter der [CRecentDockSiteInfo Klasse](../../mfc/reference/crecentdocksiteinfo-class.md).  
  
 Sie können auch diese Methode, um der Andockstatus festgelegt, wenn Sie im Bereich Informationen aus einer externen Quelle laden aufrufen.  
  
##  <a name="setexclusiverowmode"></a>CPane::SetExclusiveRowMode  
 Aktiviert oder deaktiviert die exklusiven Modus.  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bExclusive`  
 `TRUE`So aktivieren Sie die exklusiven Modus; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktivieren oder Deaktivieren der exklusive Modus. Wenn ein Bereich im exklusiven Modus befindet, kann nicht dieselbe Zeile alle anderen Symbolleisten weitergeben.  
  
 Standardmäßig alle Symbolleisten exklusiven Modus deaktiviert haben, und die Menüleiste exklusiven Modus aktiviert ist.  
  
##  <a name="setminsize"></a>CPane::SetMinSize  
 Legt den minimal zulässigen Größe für den Bereich fest.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `size`  
 Ein `CSize` -Objekt, das den minimal zulässigen Größe für den Bereich enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setvirtualrect"></a>CPane::SetVirtualRect  
 Legt die *virtuellen Rechteck* des Bereichs.  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Ein `CRect` Objekt, das das virtuelle Rechteck festgelegt werden angibt.  
  
 [in] `bMapToParent`  
 Geben Sie `TRUE` Wenn `rect` Punkte relativ zum übergeordneten Fensters enthält.  
  
### <a name="remarks"></a>Hinweise  
 Ein *virtuellen Rechteck* speichert die ursprüngliche Position eines Bereichs, wenn es verschoben wird. Das virtuelle Rechteck können das Framework die ursprüngliche Position wiederherstellen.  
  
 Rufen Sie Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben.  
  
##  <a name="setminiframertc"></a>CPane::SetMiniFrameRTC  
 Legt die Laufzeit-Klasseninformationen für das Standard-Minirahmenfenster fest.  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pClass`  
 Gibt die Laufzeit-Klasseninformationen für das Minirahmenfenster an.  
  
### <a name="remarks"></a>Hinweise  
 Ein Bereich umfließt ist, stellen sie ist auf eine [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (Minirahmenfenster). Sie können ein benutzerdefiniertes bereitstellen `CPaneFrameWnd`-abgeleitete Klasse, die verwendet werden, wenn [cpane:: Createdefaultminiframe](#createdefaultminiframe) aufgerufen wird.  
  
##  <a name="stretchpanedeferwndpos"></a>CPane::StretchPaneDeferWndPos  
 Streckt Bereich vertikal oder horizontal anhand Stil andocken.  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStretchSize`  
 Der Betrag in Pixel, um den Bereich zu vergrößern. Verwenden Sie einen negativen Wert, um den Bereich zu verkleinern.  
  
 [in] `hdwp`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Der tatsächliche Betrag in Pixel, Bereich gezogen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn erforderlich, diese Methode ändert `nStretchSize` um sicherzustellen, dass der Bereich nicht Größenlimits überschritten wird. Diese Grenzwerte werden erhalten, indem [CPane::GetAvailableStretchSize](#getavailablestretchsize) und [CPane::GetAvailableExpandSize](#getavailableexpandsize).  
  
##  <a name="toggleautohide"></a>CPane::ToggleAutoHide  
 Schaltet das automatische Ausblenden Modus.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um automatisch im Hintergrund-Modus zu wechseln. Ein Bereich muss ein Hauptrahmenfenster um Switch automatisch ausgeblendet werden angedockt werden.  
  
##  <a name="undockpane"></a>CPane::UndockPane  
 Entfernt im Bereich von docksite, Standard-Schieberegler oder Minirahmenfenster, in denen es derzeit angedockt ist.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelay`  
 Wenn `FALSE`, das Framework ruft [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) der andocklayout anpassen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um programmgesteuert einen Bereich abdocken.  
  
##  <a name="updatevirtualrect"></a>CPane::UpdateVirtualRect  
 Aktualisiert das virtuelle Rechteck.  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptOffset`  
 Ein `CPoint` -Objekt, das einen Offset, um den Bereich verschoben angibt.  
  
 [in] `sizeNew`  
 Ein `CSize` Objekt, das eine neue Größe für den Bereich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung wird das virtuelle Rechteck mit der aktuellen Position und Größe des Bereichs.  
  
 Die zweite Überladung verschiebt virtuelle Rechtecks um den Betrag der von angegebenen `ptOffset`.  
  
 Die dritte Überladung legt das virtuelle Rechteck mit der aktuellen Position des Bereichs und die Größe, die durch angegeben wird `sizeNew`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)

