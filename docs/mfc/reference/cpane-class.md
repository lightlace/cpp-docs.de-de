---
title: CPane-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPane [MFC], AdjustSizeImmediate
- CPane [MFC], AllocElements
- CPane [MFC], AllowShowOnPaneMenu
- CPane [MFC], CalcAvailableSize
- CPane [MFC], CalcInsideRect
- CPane [MFC], CalcRecentDockedRect
- CPane [MFC], CalcSize
- CPane [MFC], CanBeDocked
- CPane [MFC], CanBeTabbedDocument
- CPane [MFC], ConvertToTabbedDocument
- CPane [MFC], CopyState
- CPane [MFC], Create
- CPane [MFC], CreateDefaultMiniframe
- CPane [MFC], CreateEx
- CPane [MFC], DockByMouse
- CPane [MFC], DockPane
- CPane [MFC], DockPaneStandard
- CPane [MFC], DockToFrameWindow
- CPane [MFC], DoesAllowSiblingBars
- CPane [MFC], FloatPane
- CPane [MFC], GetAvailableExpandSize
- CPane [MFC], GetAvailableStretchSize
- CPane [MFC], GetBorders
- CPane [MFC], GetClientHotSpot
- CPane [MFC], GetDockSiteRow
- CPane [MFC], GetExclusiveRowMode
- CPane [MFC], GetHotSpot
- CPane [MFC], GetMinSize
- CPane [MFC], GetPaneName
- CPane [MFC], GetVirtualRect
- CPane [MFC], IsChangeState
- CPane [MFC], IsDragMode
- CPane [MFC], IsInFloatingMultiPaneFrameWnd
- CPane [MFC], IsLeftOf
- CPane [MFC], IsResizable
- CPane [MFC], IsTabbed
- CPane [MFC], LoadState
- CPane [MFC], MoveByAlignment
- CPane [MFC], MovePane
- CPane [MFC], OnAfterChangeParent
- CPane [MFC], OnBeforeChangeParent
- CPane [MFC], OnPressCloseButton
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], RecalcLayout
- CPane [MFC], SaveState
- CPane [MFC], SetActiveInGroup
- CPane [MFC], SetBorders
- CPane [MFC], SetClientHotSpot
- CPane [MFC], SetDockState
- CPane [MFC], SetExclusiveRowMode
- CPane [MFC], SetMiniFrameRTC
- CPane [MFC], SetMinSize
- CPane [MFC], SetVirtualRect
- CPane [MFC], StretchPaneDeferWndPos
- CPane [MFC], ToggleAutoHide
- CPane [MFC], UndockPane
- CPane [MFC], UpdateVirtualRect
- CPane [MFC], OnAfterDock
- CPane [MFC], OnAfterFloat
- CPane [MFC], OnBeforeDock
- CPane [MFC], OnBeforeFloat
- CPane [MFC], m_bHandleMinSize
- CPane [MFC], m_recentDockInfo
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b764777f33b0ae8ea1521e931ee45740f7057ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378440"
---
# <a name="cpane-class"></a>CPane Class
Die `CPane` Klasse ist eine Erweiterung dar, der die [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md). Wenn Sie ein vorhandenes MFC-Projekt aktualisieren, ersetzen Sie alle Vorkommen von `CControlBar` mit `CPane`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CPane::~CPane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Sofort berechnet das Layout eines Bereichs ein.|  
|[CPane::AllocElements](#allocelements)|Belegt Speicher für die interne Verwendung.|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Gibt an, ob der Bereich in der Common Language Runtime generierten Liste von Bereichen für die Anwendung aufgeführt wird.|  
|[CPane::CalcAvailableSize](#calcavailablesize)|Berechnet den Unterschied in der Größe zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck.|  
|[CPane::CalcInsideRect](#calcinsiderect)|Berechnet das Innere eines Bereichs, unter Berücksichtigung der Rahmen und ziehelemente Rechteck.|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Berechnet das zuletzt angedockte Rechteck.|  
|[CPane::CalcSize](#calcsize)|Berechnet die Größe des Bereichs.|  
|[CPane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich auf die angegebene Basis Bereich angedockt werden kann.|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.|  
|[CPane::CopyState](#copystate)|Kopiert den Status eines Bereichs an. (Überschreibt [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|  
|[Cpane:: Create](#create)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|  
|[Cpane:: Createdefaultminiframe](#createdefaultminiframe)|Erstellt ein Minirahmenfenster für ein unverankertes Fenster an.|  
|[Cpane:: CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|  
|`CPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CPane::DockByMouse](#dockbymouse)|Dockt einen Bereich mit der Maus Andocken Methode an.|  
|[CPane::DockPane](#dockpane)|Dockt das unverankerte Bereich zu einem Basis-Bereich an.|  
|[CPane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.|  
|[CPane::DockToFrameWindow](#docktoframewindow)|Dockt einen andockbaren Bereich mit einem Frame an. (Überschreibt `CBasePane::DockToFrameWindow`.)|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile andocken können, in dem der aktuelle Bereich angedockt ist.|  
|[CPane::FloatPane](#floatpane)|Gleitkommazahlen im Bereich an.|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Gibt die Menge in Pixel, die der Bereich erweitert werden kann.|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Gibt die Größe in Pixel, die der Bereich verkleinert werden kann.|  
|[CPane::GetBorders](#getborders)|Gibt die Breite des Rahmens des Bereichs zurück.|  
|[CPane::GetClientHotSpot](#getclienthotspot)|Gibt die *Hotspot* für den Bereich.|  
|[CPane::GetDockSiteRow](#getdocksiterow)|Gibt die Dock-Zeile, in der der Bereich angedockt ist.|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Bestimmt, ob der Bereich im exklusiven Modus ist.|  
|[CPane::GetHotSpot](#gethotspot)|Gibt den Hotspot, die in einem zugrunde liegenden gespeichert sind `CMFCDragFrameImpl` Objekt.|  
|[CPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab.|  
|[CPane::GetPaneName](#getpanename)|Ruft den Titel für den Bereich ab.|  
|`CPane::GetResizeStep`|Wird intern verwendet.|  
|`CPane::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CPane::GetVirtualRect](#getvirtualrect)|Ruft die *virtuellen Rechteck* des Bereichs.|  
|[CPane::IsChangeState](#ischangestate)|Als Bereich verschoben wird, diese Methode analysiert die Position der Bereich relativ zu anderen Bereichen, Andocken Zeilen und Minirahmenfenster und gibt den entsprechenden `AFX_CS_STATUS` Wert.|  
|[CPane::IsDragMode](#isdragmode)|Gibt an, ob der Bereich gezogen wird.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist. (Überschreibt `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|  
|[CPane::IsLeftOf](#isleftof)|Bestimmt, ob der Bereich der (oder höher) bleibt das angegebene Rechteck.|  
|[CPane::IsResizable](#isresizable)|Bestimmt, ob der Bereich, dessen Größe angepasst werden kann. (Überschreibt [cbasepane:: isResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CPane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich im Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde. (Überschreibt [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|  
|[CPane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung. (Überschreibt [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|  
|[CPane::MoveByAlignment](#movebyalignment)|Verschiebt den Bereich und die virtuellen Rechteck um den angegebenen Betrag an.|  
|[CPane::MovePane](#movepane)|Verschiebt den Bereich in das angegebene Rechteck.|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde.|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen", auf die Beschriftung für den Bereich auswählt.|  
|`CPane::OnProcessDblClk`|Wird intern verwendet.|  
|[Cpane:: Onshowcontrolbarmenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|  
|[Cpane:: Onshowcontrolbarmenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|  
|`CPane::PrepareToDock`|Wird intern verwendet.|  
|[Cpane:: RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich an. (Überschreibt [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|  
|[CPane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung. (Überschreibt [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|  
|[Cpane:: Setactiveingroup](#setactiveingroup)|Kennzeichnet einen Bereich als aktiv.|  
|[CPane::SetBorders](#setborders)|Legt die rahmenwerte der Bereich fest.|  
|[CPane::SetClientHotSpot](#setclienthotspot)|Legt den Hotspot für den Bereich an.|  
|[CPane::SetDockState](#setdockstate)|Wiederherstellungen, die Statusinformationen für den Bereich andocken.|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Aktiviert oder deaktiviert den Zeilenmodus für exklusive.|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|Legt die laufzeitklasseninformationen für das Standard-Minirahmenfenster fest.|  
|[CPane::SetMinSize](#setminsize)|Legt die minimale zulässige Größe für den Bereich an.|  
|[CPane::SetVirtualRect](#setvirtualrect)|Legt die *virtuellen Rechteck* des Bereichs.|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Streckt Bereich vertikal oder horizontal Grundlage Stil andocken.|  
|[CPane::ToggleAutoHide](#toggleautohide)|Schaltet automatischen Ausblendemodus.|  
|[CPane::UndockPane](#undockpane)|Entfernt den Bereich aus der DockPosition, Standard-Schieberegler, bzw. Minirahmenfenster, wo sie derzeit angedockt ist. (Überschreibt [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Aktualisiert die virtuelle Rechteck.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|Vom Framework aufgerufen, wenn ein Bereich angedockt wurden.|  
|[CPane::OnAfterFloat](#onafterfloat)|Vom Framework aufgerufen, wenn ein Bereich umfließt wurde.|  
|[CPane::OnBeforeDock](#onbeforedock)|Vom Framework aufgerufen, wenn der Bereich ist angedockt werden.|  
|[CPane::OnBeforeFloat](#onbeforefloat)|Vom Framework aufgerufen, wenn ein Bereich ist gleich umfließt werden.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|Ermöglicht die konsistente Behandlung von die minimale Größe für Bereiche.|  
|[Cpane:: M_recentdockinfo](#m_recentdockinfo)|Enthält aktuellen andockbaren Informationen.|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel `CPane` Objekte werden nicht direkt instanziiert werden. Wenn Sie einen Bereich, die andockbaren Funktionen verfügt benötigen, leiten Sie das Objekt aus [CDockablePane](../../mfc/reference/cdockablepane-class.md). Wenn Sie die Funktionen der Berichtssymbolleiste benötigen, leiten Sie das Objekt aus [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 Beim Ableiten einer Klasse von `CPane`, können angedockt werden, einem [CDockSite](../../mfc/reference/cdocksite-class.md) und es kann umfließt werden eine [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>  CPane::AdjustSizeImmediate  
 Sofort berechnet das Layout eines Bereichs ein.  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bRecalcLayout`  
 `TRUE` Das Layout des Bereichs automatisch neu berechnet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn Sie dynamisch das Layout eines Bereichs ändern. Beispielsweise empfiehlt es sich, diese Methode aufzurufen, wenn Sie ein- oder ausblenden Symbolleistenschaltflächen.  
  
##  <a name="allocelements"></a>  CPane::AllocElements  
 Belegt Speicher für die interne Verwendung.  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nElements`  
 Die Anzahl der Elemente, für die Zuteilung des Speichers.  
  
 [in] `cbElement`  
 Die Größe des Elements in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE` Wenn die speicherbelegung fehlschlägt. andernfalls `TRUE`.  
  
##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu  
 Gibt an, ob der Bereich in der Common Language Runtime generierten Liste von Bereichen für die Anwendung aufgeführt wird.  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in der Liste angezeigt wird; andernfalls `FALSE`. Gibt die basisimplementierung immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Die von AppWizard generierte Anwendung enthält eine Menüoption, die Bereiche aufgeführt, die es enthält. Diese Methode bestimmt, ob der Bereich in der Liste angezeigt wird.  
  
##  <a name="calcavailablesize"></a>  CPane::CalcAvailableSize  
 Berechnet den Unterschied in der Größe zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck.  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectRequired`  
 Das erforderliche Rechteck.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Differenz zwischen Breite und Höhe zwischen `rectRequired` und das aktuelle Fenster Rechteck.  
  
##  <a name="calcinsiderect"></a>  CPane::CalcInsideRect  
 Berechnet das Innere eines Bereichs, einschließlich der Rahmen und ziehelemente Rechteck.  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Enthält die Größe und den Offset des Clientbereichs des Bereichs.  
  
 [in] `bHorz`  
 `TRUE` Wenn der Bereich horizontal ausgerichtet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn sie das Layout für einen Bereich neu berechnen muss. Die `rect` Parameter mit der Größe und den Offset des Clientbereichs des Bereichs gefüllt wird. Dies schließt die Rahmen und ziehelemente.  
  
##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect  
 Berechnet das zuletzt angedockte Rechteck.  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode aktualisiert [cpane:: M_recentdockinfo](#m_recentdockinfo).  
  
##  <a name="calcsize"></a>  CPane::CalcSize  
 Berechnet die Größe des Bereichs.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVertDock`  
 `TRUE` Wenn der Bereich wird vertikal angedockt wird `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung dieser Methode gibt eine Größe von (0, 0).  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen müssen diese Methode überschreiben.  
  
##  <a name="canbedocked"></a>  CPane::CanBeDocked  
 Bestimmt, ob der Bereich auf die angegebene Basis Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Gibt den Bereich, in dem dieser Bereich befindet sich angedockt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn in diesem Bereich an der angegebenen andockbaren Bereich; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird in der Regel aufgerufen, durch das Framework, um festzustellen, ob ein Bereich an der angegebenen andockbaren Bereich angedockt werden kann. Aktiviert, um zu bestimmen, ob der Bereich angedockt werden kann, die Methode im Bereichs derzeit ergibt andockbaren Ausrichtung.  
  
 Sie aktivieren Sie das Andocken an den verschiedenen Seiten des Rahmenfensters durch Aufrufen von [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument  
 Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE` Wenn verhindern, dass einen Bereich wird in ein Dokument im Registerkartenformat konvertiert werden sollen. Ein Dokument im Registerkartenformat wird nicht in die Position des Fensters im Menü aufgelistet werden.  
  
##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument  
 Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Nicht im verwendet `CPane::ConvertToTabbedDocument`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in Dokumente im Registerformat konvertiert werden. Informationen finden Sie unter [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).  
  
##  <a name="copystate"></a>  CPane::CopyState  
 Kopiert den Status eines Bereichs an.  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOrgBar`  
 Ein Zeiger auf einen Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Status des `pOrgBar` in den aktuellen Bereich.  
  
##  <a name="create"></a>  Cpane:: Create  
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
 Gibt an, die Fenster-Stilattribute. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Gibt an, die ursprüngliche Größe und Position von der `pParentWnd` Fenster, in Clientkoordinaten.  
  
 [in] [out] `pParentWnd`  
 Gibt das übergeordnete Fenster eines in diesem Bereich an.  
  
 [in] `nID`  
 Gibt die ID des Bereichs.  
  
 [in] `dwControlBarStyle`  
 Gibt den Stil für den Bereich an. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] `pContext`  
 Gibt den erstellen-Kontext des Bereichs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.  
  
 Wenn Sie nicht explizit initialisiert haben [cpane:: M_recentdockinfo](#m_recentdockinfo) vor dem Aufruf `Create`, den Parameter `rect` wird das Rechteck beim Gleitkommatyp oder Andocken Bereich verwendet werden.  
  
##  <a name="createdefaultminiframe"></a>  Cpane:: Createdefaultminiframe  
 Erstellt ein Minirahmenfenster für ein unverankertes Fenster an.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectInitial`  
 Gibt die Anfangsgröße und die Position in Bildschirmkoordinaten, der das Minirahmenfenster erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das neu erstellte Minirahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework ein Minirahmenfenster zu erstellen, wenn ein Bereich umfließt ist. Das Minirahmenfenster kann vom Typ [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) oder vom Typ [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Ein Minirahmenfenster Multi wird erstellt, wenn der Bereich verfügt über die `AFX_CBRS_FLOAT_MULTI` Stil.  
  
 Die Laufzeit-Klasseninformationen für das Minirahmenfenster befindet sich in der `CPane::m_pMiniFrameRTC` Member. Sie können eine abgeleitete Klasse verwenden, dieses Elements festgelegt wird, wenn Sie benutzerdefinierte Minirahmenfenster erstellen möchten.  
  
##  <a name="createex"></a>  Cpane:: CreateEx  
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
 Gibt erweiterte Fenster Stilattribute. Weitere Informationen finden Sie unter [erweiterten Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
 [in] `lpszClassName`  
 Gibt den Namen der Windows-Klasse.  
  
 [in] `dwStyle`  
 Gibt die Formatattribute Fenster an. Weitere Informationen finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 Gibt an, die ursprüngliche Größe und Position von der `pParentWnd` Fenster, in Clientkoordinaten.  
  
 [in] [out] `pParentWnd`  
 Gibt das übergeordnete Fenster eines in diesem Bereich an.  
  
 [in] `nID`  
 Gibt die ID des Bereichs.  
  
 [in] `dwControlBarStyle`  
 Gibt den Stil für den Bereich an. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out] `pContext`  
 Gibt den erstellen-Kontext für den Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.  
  
 Wenn Sie nicht explizit initialisiert haben [cpane:: M_recentdockinfo](#m_recentdockinfo) vor dem Aufruf `CreateEx`, den Parameter `rect` wird das Rechteck beim Gleitkommatyp oder Andocken Bereich verwendet werden.  
  
##  <a name="dockbymouse"></a>  CPane::DockByMouse  
 Dockt einen Bereich mit der Maus an.  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Gibt an, Bereich "Basis", um diesen Bereich anzudocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
##  <a name="dockpane"></a>  CPane::DockPane  
 Dockt das unverankerte Bereich zu einem Basis-Bereich an.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pDockBar`  
 Gibt die Basis Bereich, um diesen Bereich zum Andocken.  
  
 [in] `lpRect`  
 Gibt das Rechteck auf der Basis Bereich, in dem dieser Bereich befindet sich angedockt werden.  
  
 [in] `dockMethod`  
 Gibt die zu verwendende andockbaren Methode an. Nachfolgend sind die verfügbare Optionen:  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`DM_UNKNOWN`|Das Framework verwendet diese Option aus, wenn die andockbare Methode nicht bekannt ist. Der Bereich werden die letzte unverankerte Position nicht gespeichert werden. Diese Option können auch programmgesteuert einen Bereich anzudocken, wenn Sie nicht verfügen, um die Position des letzten unverankerte zu speichern.|  
|`DM_MOUSE`|Wird intern verwendet.|  
|`DM_DBL_CLICK`|Diese Option wird verwendet, wenn die Ziehpunkte doppelgeklickt wird. Der Bereich ist an der letzten Position des andockbaren neu angeordnet. Wenn der Bereich durch Doppelklicken auf abgedockten ist, wird im Bereich in seiner Position des letzten unverankerte neu positioniert.|  
|`DM_SHOW`|Diese Option kann verwendet werden, um programmgesteuert auf den Bereich anzudocken. Der Bereich speichert die letzte floating-Position.|  
|`DM_RECT`|Der Bereich wird in den Bereich mit der angegebenen angedockt `lpRect`.|  
|`DM_STANDARD`|Wenn Sie diese Option verwenden, zeichnet das Framework Bereich als eine Gliederung Frame während dieser verschoben wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode Dockt den Bereich an, in den angegebenen Basis-Bereich der `pDockBar` Parameter. Sie müssen zuerst aktivieren, durch den Aufruf Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard  
 Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bWasDocked`  
 `TRUE` Wenn der Bereich erfolgreich angedockt wurde; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer die `this` Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur für Bereiche, die von der abgeleiteten verwendet die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md). Weitere Informationen finden Sie unter [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).  
  
##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow  
 Dockt einen andockbaren Bereich mit einem Frame an.  
  
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
 Die Seite des übergeordneten Frames, die Sie im Bereich, um andocken möchten.  
  
 [in] `lpRect`  
 Die angegebene Größe.  
  
 [in] `dwDockFlags`  
 Ignoriert.  
  
 [in] `pRelativeBar`  
 Ignoriert.  
  
 [in] `nRelativeIndex`  
 Ignoriert.  
  
 [in] `bOuterEdge`  
 Wenn `TRUE` und es gibt andere andockbare Bereiche auf der Seite mit den vom angegebenen `dwAlignment`, ist der Bereich außerhalb der anderen Bereichen angedockt näher an den Rand des übergeordneten Frames. Wenn `FALSE`, Bereich näher an das Rechenzentrum des Clientbereichs angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `FALSE` Wenn eine bereichsteiler ( [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md)) kann nicht erstellt wurde, andernfalls werden `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars  
 Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile andocken können, in dem der aktuelle Bereich angedockt ist.  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn in diesem Bereich in einen anderen Bereich in der gleichen Zeile als selbst Andocken kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie aktivieren oder deaktivieren Sie dieses Verhalten durch den Aufruf [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
 Standardmäßig Symbolleisten haben exklusiven Zeilenmodus deaktiviert, und die Menüleisten hat exklusiven Modus aktiviert.  
  
##  <a name="floatpane"></a>  CPane::FloatPane  
 Gleitkommazahlen im Bereich an.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt den Speicherort, in Bildschirmkoordinaten, um den Bereich zu positionieren, wenn es umfließt ist.  
  
 [in] `dockMethod`  
 Gibt die andockbare Methode zu verwenden, wenn der Bereich umfließt ist. Eine Liste der möglichen Werte finden Sie unter [CPane::DockPane](#dockpane).  
  
 [in] `bShow`  
 `TRUE` um die im Bereich umfließt anzuzeigen; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich umfließt wurde oder Bereich da umfließt kann nicht [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) gibt `FALSE`ist, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Bereich an der Position float, die von angegeben wird die `rectFloat` Parameter. Diese Methode erstellt automatisch eine übergeordnete Minirahmenfenster für den Bereich.  
  
##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize  
 Gibt die Menge in Pixel, die der Bereich erweitert werden kann.  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Bereich horizontal angedockt ist, ist der Rückgabewert der verfügbaren Breite; Andernfalls ist der Rückgabewert der verfügbaren Höhe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize  
 Gibt die Größe in Pixel, die der Bereich verkleinert werden kann.  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Betrag in Pixel, die der Bereich verkleinert werden kann. Wenn der Bereich horizontal angedockt ist, wird diese Menge der verfügbaren Breite; Andernfalls ist es der verfügbaren Höhe.  
  
### <a name="remarks"></a>Hinweise  
 Die verfügbare Größe für die Stretch wird berechnet, indem dem niedrigsten zulässigen Größe für den Bereich Subtraktion ( [CPane::GetMinSize](#getminsize)) von der aktuellen Größe ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).  
  
##  <a name="getborders"></a>  CPane::GetBorders  
 Gibt die Breite des Rahmens des Bereichs zurück.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die aktuelle Breite der einzelnen Rand des Bereichs in Pixel enthält. Beispielsweise den Wert von der `left` Mitglied der `CRect` Objekt ist die Breite des linken Rahmens.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Festlegen der Größe der Rahmen [CPane::SetBorders](#setborders).  
  
##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot  
 Gibt die *Hotspot* für den Bereich.  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die *Hotspot* ist die Stelle im Bereich, die der Benutzer wählt und beinhalten, die auf um den Bereich zu verschieben. Ein Hotspot wird für smooth Animation verwendet, wenn der Bereich von einer verankerten Position verschoben wird.  
  
##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow  
 Gibt die Zeile andocken ( [CDockingPanesRow Klasse](../../mfc/reference/cdockingpanesrow-class.md)) in dem der Bereich angedockt ist.  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CDockingPanesRow`*, verweist auf die Dock-Zeile, in dem der Bereich angedockt ist, oder `NULL` , wenn der Bereich nicht angedockt ist.  
  
##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode  
 Bestimmt, ob der Bereich im exklusiven Modus ist.  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich im exklusiven Modus wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu exklusiven Zeilenmodus, finden Sie unter [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
##  <a name="gethotspot"></a>  CPane::GetHotSpot  
 Gibt den Hotspot, die in einem zugrunde liegenden gespeichert sind `CMFCDragFrameImpl` Objekt.  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Die `CPane` Klasse enthält eine `CMFCDragFrameImpl` Objekt `m_dragFrameImpl`, d. h. dafür verantwortlich, zeichnen das Rechteck, das angezeigt wird, wenn der Benutzer einen Bereich in der Dockingstation Modus "standard" wechselt. Der Hotspot dient zum Zeichnen des Rechtecks relativ zur aktuellen Mausposition, wenn der Benutzer im Bereich bewegt.  
  
##  <a name="getminsize"></a>  CPane::GetMinSize  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit dem niedrigsten zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getpanename"></a>  CPane::GetPaneName  
 Ruft den Titel für den Bereich ab.  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strName`  
 Ein `CString` -Objekt, das mit den Beschriftungsnamen gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Titel im Bereich wird im Bereich "Caption" angezeigt, wenn der Bereich angedockt oder unverankert ist. Wenn der Bereich im Registerkartenformat Gruppe gehört, wird der Titel im Registerkartenbereich angezeigt. Wenn der Bereich in den automatischen Ausblendemodus ist, wird der Titel angezeigt, auf eine `CMFCAutoHideButton`.  
  
##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect  
 Ruft die *virtuellen Rechteck* des Bereichs.  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectVirtual`  
 Ein `CRect` -Objekt, das mit dem virtuellen Rechteck ausgefüllt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Bereich verschoben wird, speichert das Framework die ursprüngliche Position des Bereichs in einem virtuellen Rechteck. Das Framework können virtuelle Rechteck zum Wiederherstellen der ursprünglichen Position des Bereichs.  
  
 Rufen Sie nicht die Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben.  
  
##  <a name="ischangestate"></a>  CPane::IsChangeState  
 Als Bereich verschoben wird, diese Methode seiner Position relativ zu anderen Bereichen, Andocken Zeilen und Minirahmenfenster analysiert, und gibt den entsprechenden `AFX_CS_STATUS` Wert.  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nOffset`  
 Gibt die andockbaren Empfindlichkeit an. Z. B. ein Bereich, der innerhalb verschoben wird `nOffset` Pixel aus einer Zeile Andocken angedockt werden.  
  
 [in] `ppTargetBar`  
 Wenn die Methode zurückkehrt, `ppTargetBar` enthält entweder einen Zeiger auf das Objekt, auf die im aktuellen Bereich angedockt werden soll, oder `NULL` , wenn keine Zuordnung erfolgen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Eines der folgenden `AFX_CS_STATUS` Werte:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CS_NOTHING`|Der Bereich ist nicht in der Nähe von einer docksite. Das Framework ist nicht auf den Bereich anzudocken.|  
|`CS_DOCK_IMMEDIATELY`|Der Bereich wird über eine docksite und die `DT_IMMEDIATE` Format aktiviert ist. Das Framework Dockt den Bereich sofort an.|  
|`CS_DELAY_DOCK`|Der Bereich wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe ist. Das Framework Dockt den Bereich an, wenn der Benutzer die Verschiebung loslässt.|  
|`CS_DELAY_DOCK_TO_TAB`|Der Bereich wird über eine docksite, die bewirkt, dass der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Bereich entweder über die Beschriftung des anderen andockbaren Bereich oder der Registerkartenbereich, der einen Bereich im Registerkartenformat. Das Framework Dockt den Bereich an, wenn der Benutzer die Verschiebung loslässt.|  
  
##  <a name="isdragmode"></a>  CPane::IsDragMode  
 Gibt an, ob der Bereich verschoben wird.  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich verschoben wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in einem Multipane-Rahmenfenster ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in einem Rahmenfenster Multipane float. Aus diesem Grund `CPane::IsInFloatingMultiPaneFrameWnd` gibt immer `FALSE`.  
  
##  <a name="isleftof"></a>  CPane::IsLeftOf  
 Bestimmt, ob der Bereich der (oder höher) bleibt das angegebene Rechteck.  
  
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
 Wenn der Bereich horizontal angedockt ist, wird diese Methode überprüft, unabhängig davon, ob die Position des ist `rect`. Andernfalls, diese Methode überprüft, ob die Position oben `rect`.  
  
##  <a name="isresizable"></a>  CPane::IsResizable  
 Gibt an, ob der Bereich geändert wird.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich geändert wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Base `CPane` Objekte werden nicht geändert werden kann.  
  
 Dock-Manager verwendet das in der Größe veränderbaren Flag Bereichslayout bestimmen. Nicht veränderbare Größen Bereiche befinden sich immer auf den äußeren Rändern eines den übergeordneten Frame.  
  
 Nicht veränderbare Größen Bereiche dürfen nicht in Container andocken sein.  
  
##  <a name="istabbed"></a>  CPane::IsTabbed  
 Bestimmt, ob das Registerkarten-Steuerelement ein Fenster im Registerkartenformat Bereich eingefügt wurden.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich im Registerkartenformat ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die im Registerkartenformat Zustand wird separat von der Gleitkommawert behandelt, angedockt und automatisch im Hintergrund Zustände.  
  
##  <a name="loadstate"></a>  CPane::LoadState  
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
 Im Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich Zustand erfolgreich geladen wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Zustand des Bereichs aus der Registrierung geladen. Überschreiben Sie diese in einer abgeleiteten Klasse zusätzliche Informationen zu laden, die vom gespeichert wird [CPane::SaveState](#savestate).  
  
 Wenn Sie diese Methode überschreiben, rufen Sie die Basismethode auch zurückgeben `FALSE` die Basismethode zurück `FALSE`.  
  
##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize  
 Ermöglicht die konsistente Behandlung der minimalen Bereich Größen.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine oder mehrere andockbare Bereiche in der Anwendung überschreiben `GetMinSize`, oder wenn die Anwendung aufruft `SetMinSize`, Sie möchten dieses statische Element festgelegt werden, um `TRUE` damit können das Framework einheitlich behandeln wie Bereiche deren Größe geändert werden.  
  
 Wenn dieser Wert, um festgelegt wird `TRUE`, alle Bereiche, deren Größe sollte, geringer als die Mindestzeit reduziert werden, abgeschnitten werden, nicht gestreckt. Da das Framework Fenster Regionen Zwecken Sizing Bereich verwendet wird, ändern die Größe des der Fensterregion für andockbare Bereiche aus, wenn dieser Wert, um festgelegt wird nicht `TRUE`.  
  
##  <a name="m_recentdockinfo"></a>  Cpane:: M_recentdockinfo  
 Enthält aktuellen andockbaren Informationen.  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework speichert die neuesten andockbaren Statusinformationen für den Bereich in dieses Elements.  
  
##  <a name="movebyalignment"></a>  CPane::MoveByAlignment  
 Verschiebt den Bereich und die virtuellen Rechteck um den angegebenen Betrag an.  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt im Bereich Ausrichtung an.  
  
 [in] `nOffset`  
 Der Betrag in Pixel, um den Bereich und die virtuellen Rechteck verschieben.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment` eine der folgenden Werte kann sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Ermöglicht der Bereich am Anfang der Clientbereich eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_BOTTOM`|Ermöglicht der Bereich am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.|  
|`CBRS_ALIGN_LEFT`|Können den Bereich, um an der linken Seite des Clientbereichs eines Frame-Fensters angedockt werden.|  
|`CBRS_ALIGN_RIGHT`|Können den Bereich, um auf die rechte Seite des Clientbereichs eines Frame-Fensters angedockt werden.|  
|`CBRS_ALIGN_ANY`|Können den Bereich, um auf jeder Seite des Clientbereichs Rand eines Rahmenfensters angedockt werden.|  
  
 Wenn `dwAlignment` enthält die `CBRS_ALIGN_LEFT` oder `CBRS_ALIGN_RIGHT` Flag, das im Bereich und virtuellen Rechteck werden verschoben werden horizontal, andernfalls, wenn `dwAlignment` enthält die `CBRS_ALIGN_TOP` oder `CBRS_ALIGN_BOTTOM` Flag, das im Bereich und virtuellen Rechteck werden verschoben. vertikal.  
  
##  <a name="movepane"></a>  CPane::MovePane  
 Verschiebt den Bereich in das angegebene Rechteck.  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectNew`  
 Gibt das neue Rechteck für den Bereich an.  
  
 [in] `bForceMove`  
 Wenn `TRUE`, diese Methode ignoriert die minimale zulässige Fenstergröße ( [CPane::GetMinSize](#getminsize)) ist, andernfalls ist der Bereich bei Bedarf, um sicherzustellen, dass mindestens dem niedrigsten zulässigen Größe angepasst.  
  
 [in] `hdwp`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das die Unterschiede in der Breite und Höhe zwischen den alten und neuen Rechtecken enthält (alte Rechteck - `rectNew`).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur für andockbare Bereiche verwendet.  
  
##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent  
 Vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pWndOldParent`  
 Der Bereich vorherigen übergeordneten Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs aufgrund eines andockbaren "oder" Gleitkomma-Vorgangs geändert wurde.  
  
##  <a name="onafterdock"></a>  CPane::OnAfterDock  
 Vom Framework aufgerufen, wenn ein Bereich angedockt wurden.  
  
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
  
##  <a name="onafterfloat"></a>  CPane::OnAfterFloat  
 Vom Framework aufgerufen, nachdem ein Bereich gleitet.  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Verarbeitungsschritte auszuführen, nachdem ein Bereich wird verschoben werden sollen.  
  
##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent  
 Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pWndNewParent`  
 Gibt das neue übergeordnete Fenster.  
  
 [in] `bDelay`  
 `TRUE` um die globalen andockbaren Layout Anpassung verzögern; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs gerade geändert werden, da der Bereich wird angedockt oder umfließt.  
  
 Der Bereich wird standardmäßig mit andockbaren Bereich aufgehoben durch Aufrufen `CDockSite::RemovePane`.  
  
##  <a name="onbeforedock"></a>  CPane::OnBeforeDock  
 Vom Framework aufgerufen, wenn der Bereich zum Andocken wird.  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `ppDockBar`  
 Gibt den Bereich, dem diesen Bereich zum Andocken ist.  
  
 [in] `lpRect`  
 Gibt das Rechteck andocken.  
  
 [in] `dockMethod`  
 Gibt die Andock-Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich angedockt werden kann. Wenn die Funktion zurückgibt `FALSE`, andockbare Vorgang wird abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn gerade ein Bereich angedockt werden. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Sie möchten, um Verarbeitungsschritte auszuführen, bevor Sie schließlich ein Bereich angedockt ist.  
  
##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat  
 Vom Framework aufgerufen, wenn ein Bereich zu "float" befindet.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand ist.  
  
 [in] `dockMethod`  
 Gibt die Methode andockbare Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich umfließt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Bereich zu "float" ist. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, gegebenenfalls um Verarbeitungsschritte auszuführen, bevor Bereich schließlich gleitet.  
  
##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton  
 Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" auf die Beschriftung für den Bereich drückt.  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer drückt die **schließen** Schaltfläche auf den Bereich Beschriftung. Für den Empfang von Benachrichtigungen über die **schließen** -Ereignis können Sie diese Methode in einer abgeleiteten Klasse überschreiben.  
  
##  <a name="onshowcontrolbarmenu"></a>  Cpane:: Onshowcontrolbarmenu  
 Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Speicherort im Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie im Menü angezeigt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Menü enthält mehrere Elemente, die Ihnen ermöglichen, geben Sie im Bereich Verhalten, nämlich: **Unverankert**, **Andocken**, **Taskleisten**, und **ausblenden**. Sie können diesem Menü für alle Bereiche durch Aufrufen von [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).  
  
##  <a name="recalclayout"></a>  Cpane:: RecalcLayout  
 Berechnet die Layoutinformationen für den Bereich an.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich angedockt ist, aktualisiert diese Methode das virtuelle Rechteck für den Bereich durch Festlegen der Größe der aktuellen Größe des Bereichs an.  
  
 Wenn im Bereich unverankert ist, informiert diese Methode der übergeordneten Minirahmenfensters zum Anpassen der Größe des Bereichs auf die Größe des kleinen Rahmenfenster. Das Framework wird sichergestellt, dass die Minirahmenfensters mindestens dem niedrigsten zulässigen Größe für den Bereich ( [CPane::GetMinSize](#getminsize)) und ändert die Größe der Minirahmenfensters bei Bedarf.  
  
##  <a name="savestate"></a>  CPane::SaveState  
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
 Im Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es den Zustand des Bereichs in der Registrierung gespeichert. Überschreiben Sie `SaveState` in einer abgeleiteten Klasse, um zusätzliche Informationen zu speichern.  
  
 Wenn Sie diese Methode überschreiben, rufen Sie die Basismethode auch zurückgeben `FALSE` die Basismethode zurück `FALSE`.  
  
##  <a name="setactiveingroup"></a>  Cpane:: Setactiveingroup  
 Kennzeichnet einen Bereich als aktiv.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 Ein `BOOL` , der angibt, ob der Bereich als aktiv gekennzeichnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Ein andockbaren Bereich oder eine Schaltfläche zum automatischen Ausblenden wird ausgewählt, wird der entsprechenden automatisch ausblendbaren Bereich als aktiv gekennzeichnet.  
  
 Die Darstellung der eine Schaltfläche zum automatischen Ausblenden, die dem Bereich zugeordnet ist, basiert auf zwei Faktoren ab. Wenn der Bereich aktiv ist und die `static BOOL CMFCAutoHideButton::m_bOverlappingTabs` ist `TRUE`, das Framework zeigt die Schaltfläche zum automatischen Ausblenden als ein Symbol und eine Bezeichnung. Für einen inaktiven Bereich zeigt das Framework nur das Symbol "automatisch im Hintergrund".  
  
 Wenn `CMFCAutoHideButton::m_bOverlappingTabs` ist `FALSE`, oder wenn der Bereich nicht in einer Gruppe befindet, zeigt das Framework die Schaltfläche zum automatischen Ausblenden zugeordnete als ein Symbol und eine Bezeichnung.  
  
##  <a name="setborders"></a>  CPane::SetBorders  
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
 Gibt die Breite des rechten Rahmens des Bereichs in Pixel an.  
  
 [in] `cyBottom`  
 Gibt die Breite des unteren Rahmens des Bereichs in Pixel an.  
  
 [in] `lpRect`  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite der einzelnen Rahmen des Bereichs in Pixel enthält.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der Größe der Rahmen des Bereichs.  
  
##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot  
 Legt die *Hotspot* für den Bereich.  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptNew`  
 Ein `CPoint` Objekt, das den neuen Hotspot angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Hotspot* ist die Stelle im Bereich, die der Benutzer wählt und beinhalten, die auf um den Bereich zu verschieben. Ein Hotspot wird für smooth Animation verwendet, wenn der Bereich von einer verankerten Position gezogen wird.  
  
##  <a name="setdockstate"></a>  CPane::SetDockState  
 Wiederherstellungen, die Statusinformationen für den Bereich andocken.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockManager`  
 Ein Zeiger auf die Dock-Manager für das Hauptrahmenfenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework zum Wiederherstellen der neuesten andockbaren Statusinformationen für den Bereich aufgerufen. Ein Bereich speichert aktuelle andockbaren Zustandsinformationen in [cpane:: M_recentdockinfo](#m_recentdockinfo). Weitere Informationen finden Sie unter der [CRecentDockSiteInfo Klasse](../../mfc/reference/crecentdocksiteinfo-class.md).  
  
 Sie können auch aufrufen diese Methode, um den andockzustand festgelegt, wenn Sie im Bereich Informationen aus einer externen Quelle geladen werden.  
  
##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode  
 Aktiviert oder deaktiviert den Zeilenmodus für exklusive.  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bExclusive`  
 `TRUE` So aktivieren Sie die exklusiven Modus; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktivieren oder Deaktivieren der exklusive Modus. Wenn ein Bereich im exklusiven Modus befindet, kann nicht dieselbe Zeile alle anderen Symbolleisten weitergeben.  
  
 Standardmäßig alle Symbolleisten haben exklusiven Zeilenmodus deaktiviert, und die Menüleisten hat exklusiven Modus aktiviert.  
  
##  <a name="setminsize"></a>  CPane::SetMinSize  
 Legt die minimale zulässige Größe für den Bereich an.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `size`  
 Ein `CSize` Objekt, das dem niedrigsten zulässigen Größe für den Bereich enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect  
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
 Ein *virtuellen Rechteck* speichert die ursprüngliche Position eines Bereichs, wenn es verschoben wird. Das Framework können virtuelle Rechteck die ursprüngliche Position wiederhergestellt.  
  
 Rufen Sie nicht die Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben.  
  
##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC  
 Legt die laufzeitklasseninformationen für das Standard-Minirahmenfenster fest.  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pClass`  
 Gibt die laufzeitklasseninformationen für das Minirahmenfenster an.  
  
### <a name="remarks"></a>Hinweise  
 Wird ein Bereich umfließt ist, wird es eingefügt, auf eine [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (Minirahmenfenster). Sie können eine benutzerdefinierte bereitstellen `CPaneFrameWnd`-abgeleitete Klasse, die verwendet wird, wenn [cpane:: Createdefaultminiframe](#createdefaultminiframe) aufgerufen wird.  
  
##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos  
 Streckt Bereich vertikal oder horizontal Grundlage Stil andocken.  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStretchSize`  
 Der Betrag in Pixel, um den Bereich zu Strecken. Verwenden Sie einen negativen Wert, um den Bereich zu verkleinern.  
  
 [in] `hdwp`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die tatsächliche Speicherkapazität in Pixel, dass der Bereich gestreckt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn erforderlich, diese Methode ändert `nStretchSize` um sicherzustellen, dass der Bereich nicht Größenlimits überschritten wird. Diese Grenzen werden durch den Aufruf abgerufen [CPane::GetAvailableStretchSize](#getavailablestretchsize) und [CPane::GetAvailableExpandSize](#getavailableexpandsize).  
  
##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide  
 Schaltet automatischen Ausblendemodus.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den automatischen Ausblendemodus umzuschalten. Ein Bereich muss an einem Hauptrahmenfenster angedockt werden, damit zum automatischen Ausblenden Modus wechseln.  
  
##  <a name="undockpane"></a>  CPane::UndockPane  
 Entfernt den Bereich aus der DockPosition, Standard-Schieberegler, bzw. Minirahmenfenster, wo sie derzeit angedockt ist.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelay`  
 Wenn `FALSE`, das Framework ruft [cbasepane:: Adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) am Layout des Docks anpassen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um programmgesteuert einen Bereich abdocken.  
  
##  <a name="updatevirtualrect"></a>  CPane::UpdateVirtualRect  
 Aktualisiert die virtuelle Rechteck.  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ptOffset`  
 Ein `CPoint` Objekt, das einen Offset nach dem zu verschiebenden Bereich angibt.  
  
 [in] `sizeNew`  
 Ein `CSize` Objekt, das eine neue Größe für den Bereich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung legt das virtuelle Rechteck mit dem aktuellen Position und Größe des Bereichs fest.  
  
 Die zweite Überladung virtuellen Rechtecks um den Betrag, der angegeben wird verlagert `ptOffset`.  
  
 Die dritte Überladung legt das virtuelle Rechteck mit der aktuellen Position des im Bereich und die Größe, die von angegeben wird `sizeNew`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)
