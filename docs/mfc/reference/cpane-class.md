---
title: CPane-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 1a32625001ae86f4d6dffa7eeb953c538822d207
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080220"
---
# <a name="cpane-class"></a>CPane Class

Die `CPane` Klasse ist eine Erweiterung von der [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md). Wenn Sie ein vorhandenes MFC-Projekt aktualisieren, ersetzen Sie alle Vorkommen von `CControlBar` mit `CPane`.

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
|[CPane::AllocElements](#allocelements)|Weist Speicher für die interne Verwendung.|
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Gibt an, ob der Bereich in der Laufzeit generierte Liste von Bereichen für die Anwendung aufgeführt wird.|
|[CPane::CalcAvailableSize](#calcavailablesize)|Berechnet den Unterschied in der Größe zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck.|
|[CPane::CalcInsideRect](#calcinsiderect)|Berechnet den inneren Rechteck eines Bereichs, der Rahmen und ziehelemente berücksichtigt.|
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Berechnet das vor kurzem angedockte Rechteck.|
|[CPane::CalcSize](#calcsize)|Berechnet die Größe des Bereichs.|
|[CPane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich auf die angegebene Basis Bereich angedockt werden kann.|
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.|
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.|
|[CPane::CopyState](#copystate)|Kopiert den Status eines Bereichs an. (Überschreibt [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|
|[Cpane:: Create](#create)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|
|[Cpane:: Createdefaultminiframe](#createdefaultminiframe)|Erstellt ein Minirahmenfenster für einen unverankerten Bereichs klicken.|
|[Cpane:: CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der `CPane` Objekt.|
|`CPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CPane::DockByMouse](#dockbymouse)|Dockt einen Bereich mit der Maus docking-Methode an.|
|[CPane::DockPane](#dockpane)|Dockt das unverankerten Bereichs klicken auf einen Basis-Bereich an.|
|[CPane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.|
|[CPane::DockToFrameWindow](#docktoframewindow)|Dockt einen andockbaren Bereich in einen Datenrahmen an. (Überschreibt `CBasePane::DockToFrameWindow`.)|
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile angedockt werden können, in dem der aktuelle Bereich angedockt ist.|
|[CPane::FloatPane](#floatpane)|Wird im Bereich verschoben.|
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Gibt die Menge, in Pixel, die den Bereich zu erweitern, kann zurück.|
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Gibt die Menge, in Pixel, die im Bereich verkleinert werden kann.|
|[CPane::GetBorders](#getborders)|Gibt die Breite des Rahmens des Bereichs zurück.|
|[CPane::GetClientHotSpot](#getclienthotspot)|Gibt die *Hotspot* für den Bereich.|
|[CPane::GetDockSiteRow](#getdocksiterow)|Gibt zurück, die Dock-Zeile, in der der Bereich angedockt ist.|
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Bestimmt, ob der Bereich im Zeilenmodus exklusiv ist.|
|[CPane::GetHotSpot](#gethotspot)|Gibt den Hotspot, die in einer zugrunde liegenden gespeicherten `CMFCDragFrameImpl` Objekt.|
|[CPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab.|
|[CPane::GetPaneName](#getpanename)|Ruft den Titel für den Bereich ab.|
|`CPane::GetResizeStep`|Wird intern verwendet.|
|`CPane::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CPane::GetVirtualRect](#getvirtualrect)|Ruft die *virtuellen Rechteck* des Bereichs.|
|[CPane::IsChangeState](#ischangestate)|Wie der Bereich wird verschoben wird, wird diese Methode die Position der Bereich relativ zu anderen Bereichen, analysiert andocken, Zeilen und Minirahmenfenster und den entsprechenden AFX_CS_STATUS Wert zurückgibt.|
|[CPane::IsDragMode](#isdragmode)|Gibt an, ob der Bereich gezogen wird.|
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist. (Überschreibt `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|
|[CPane::IsLeftOf](#isleftof)|Bestimmt, ob im Bereich (oder höher) bleibt das angegebene Rechteck.|
|[CPane::IsResizable](#isresizable)|Bestimmt, ob der Bereich geändert werden kann. (Überschreibt [cbasepane:: isResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CPane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich im Registerkarten-Steuerelement von einem Fenster im Registerkartenformat eingefügt wurde. (Überschreibt [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|
|[CPane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung. (Überschreibt [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|
|[CPane::MoveByAlignment](#movebyalignment)|Verschiebt den Bereich und das virtuelle Rechteck den angegebenen Betrag an.|
|[CPane::MovePane](#movepane)|Verschiebt den Bereich in das angegebene Rechteck.|
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde.|
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.|
|[CPane::OnPressCloseButton](#onpressclosebutton)|Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen", auf die Beschriftung für den Bereich auswählt.|
|`CPane::OnProcessDblClk`|Wird intern verwendet.|
|[Cpane:: Onshowcontrolbarmenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|
|[Cpane:: Onshowcontrolbarmenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.|
|`CPane::PrepareToDock`|Wird intern verwendet.|
|[Cpane:: RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich an. (Überschreibt [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|
|[CPane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung. (Überschreibt [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|
|[Cpane:: Setactiveingroup](#setactiveingroup)|Bitflags, die einen Bereich als aktiv.|
|[CPane::SetBorders](#setborders)|Legt die rahmenwerte der Bereich fest.|
|[CPane::SetClientHotSpot](#setclienthotspot)|Legt den Hotspot für den Bereich fest.|
|[CPane::SetDockState](#setdockstate)|Stellt Statusinformationen für den Bereich andocken.|
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Aktiviert oder deaktiviert den Zeilenmodus für exklusive.|
|[CPane::SetMiniFrameRTC](#setminiframertc)|Legt fest, die laufzeitklasseninformationen für das Standard-Minirahmenfenster.|
|[CPane::SetMinSize](#setminsize)|Legt fest, den minimal zulässige Größe für den Bereich.|
|[CPane::SetVirtualRect](#setvirtualrect)|Legt die *virtuellen Rechteck* des Bereichs.|
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Wird im Bereich vertikal oder horizontal andockstil Grundlage gestreckt.|
|[CPane::ToggleAutoHide](#toggleautohide)|Schaltet automatischen Ausblendemodus.|
|[CPane::UndockPane](#undockpane)|Entfernt den Bereich aus der DockPosition, Standard-Schieberegler oder ein Minirahmenfenster, in dem sie zurzeit angedockt wird. (Überschreibt [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Aktualisiert das virtuelle Rechteck.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPane::OnAfterDock](#onafterdock)|Vom Framework aufgerufen, wenn Sie ein Bereich angedockt wurden, hat.|
|[CPane::OnAfterFloat](#onafterfloat)|Vom Framework aufgerufen, wenn ein Bereich ist abgedockt wurde.|
|[CPane::OnBeforeDock](#onbeforedock)|Vom Framework aufgerufen, wenn der Bereich ist angedockt werden.|
|[CPane::OnBeforeFloat](#onbeforefloat)|Vom Framework aufgerufen, wenn ein Bereich wird abgedockt werden.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|Ermöglicht die konsistente Behandlung von die minimale Größe für Bereiche.|
|[Cpane:: M_recentdockinfo](#m_recentdockinfo)|Enthält die aktuellen Informationen zur andocken.|

## <a name="remarks"></a>Hinweise

In der Regel `CPane` Objekte werden nicht direkt instanziiert werden. Wenn Sie einen Bereich, das Andocken Funktionen verfügt benötigen, leiten Sie das Objekt aus [CDockablePane](../../mfc/reference/cdockablepane-class.md). Wenn Sie die Funktionen der Berichtssymbolleiste benötigen, leiten Sie das Objekt aus [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).

Beim Ableiten einer Klasse von `CPane`, es der angedockt werden kann, eine [CDockSite](../../mfc/reference/cdocksite-class.md) und sie können abgedockt werden eine [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).

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

*bRecalcLayout*<br/>
[in] True, um das Layout des Bereichs automatisch neu berechnet. andernfalls "false".

### <a name="remarks"></a>Hinweise

Aufgerufen Sie diese Methode wird, wenn Sie dynamisch das Layout eines Bereichs ändern. Beispielsweise empfiehlt es sich, diese Methode aufzurufen, wenn Sie aus- oder Einblenden von Symbolleisten-Schaltflächen.

##  <a name="allocelements"></a>  CPane::AllocElements

Weist Speicher für die interne Verwendung.

```
BOOL AllocElements(
    int nElements,
    int cbElement);
```

### <a name="parameters"></a>Parameter

*nElements*<br/>
[in] Die Anzahl der Elemente, für die speicherbelegung.

*cbElement*<br/>
[in] Die Größe in Bytes eines Elements.

### <a name="return-value"></a>Rückgabewert

FALSE, wenn die speicherbelegung fehlschlägt. andernfalls "true" fest.

##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu

Gibt an, ob der Bereich in der Laufzeit generierte Liste von Bereichen für die Anwendung aufgeführt wird.

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich in der Liste angezeigt wird. andernfalls "false". Die basisimplementierung immer gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Die Anwendungs-Assistenten generierte Anwendung enthält eine Menüoption, die Bereiche aufgeführt, die sie enthält. Diese Methode bestimmt, ob der Bereich in der Liste angezeigt wird.

##  <a name="calcavailablesize"></a>  CPane::CalcAvailableSize

Berechnet den Unterschied in der Größe zwischen einem angegebenen Rechteck und das aktuelle Fenster Rechteck.

```
virtual CSize CalcAvailableSize(CRect rectRequired);
```

### <a name="parameters"></a>Parameter

*rectRequired*<br/>
[in] Das erforderliche Rechteck.

### <a name="return-value"></a>Rückgabewert

Die Differenz zwischen Breite und Höhe zwischen *RectRequired* und das aktuelle Fenster Rechteck.

##  <a name="calcinsiderect"></a>  CPane::CalcInsideRect

Berechnet den inneren Rechteck eines Bereichs, einschließlich der Rahmen und ziehelemente.

```
void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
[out] Enthält die Größe und den Offset des Clientbereichs des Bereichs.

*bHorz*<br/>
[in] True, wenn der Bereich horizontal ausgerichtet ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn es besitzt, um das Layout für einen Bereich neu zu berechnen. Die *Rect* Parameter mit der Größe und den Offset des Clientbereichs des Bereichs gefüllt ist. Dies schließt die Rahmen und ziehelemente.

##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect

Berechnet das vor kurzem angedockte Rechteck.

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

*bVertDock*<br/>
[in] TRUE, wenn der Bereich vertikal "false" andernfalls angedockt wird.

### <a name="return-value"></a>Rückgabewert

Die Standardimplementierung dieser Methode gibt eine Größe von (0, 0).

### <a name="remarks"></a>Hinweise

Abgeleitete Klassen sollten diese Methode überschreiben.

##  <a name="canbedocked"></a>  CPane::CanBeDocked

Bestimmt, ob der Bereich auf die angegebene Basis Bereich angedockt werden kann.

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>Parameter

*pDockBar*<br/>
[in] Gibt den Bereich, in denen dieser Bereich befindet sich angedockt werden.

### <a name="return-value"></a>Rückgabewert

True, wenn in diesem Bereich an der angegebenen andockbaren Bereich angedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird in der Regel aufgerufen, durch das Framework, um festzustellen, ob ein Bereich auf den angegebenen andockbaren Bereich angedockt werden kann. Aktiviert Andocken Ausrichtung, um zu bestimmen, ob der Bereich angedockt werden kann, die Methode des Bereichs derzeit ausgewertet wird.

Sie aktivieren Sie das Andocken an den verschiedenen Seiten des Rahmenfensters durch Aufrufen von [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).

##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument

Bestimmt, ob der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann.

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse und zurückgegeben Sie "false", wenn Sie möchten, um zu verhindern, dass einen Bereich in ein Dokument im Registerkartenformat konvertiert wird. Ein Dokument mit Registerkarten werden in die Position des Fensters im Menü nicht aufgeführt.

##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument

Konvertiert einen andockbaren Bereich, ein Dokument im Registerkartenformat.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bActiveTabOnly*<br/>
[in] Nicht verwendet in `CPane::ConvertToTabbedDocument`.

### <a name="remarks"></a>Hinweise

Nur andockbare Bereiche können in Dokumente im Registerformat konvertiert werden. Weitere Informationen finden Sie unter [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).

##  <a name="copystate"></a>  CPane::CopyState

Kopiert den Status eines Bereichs an.

```
virtual void CopyState(CPane* pOrgBar);
```

### <a name="parameters"></a>Parameter

*pOrgBar*<br/>
[in] Ein Zeiger auf einen Bereich.

### <a name="remarks"></a>Hinweise

Diese Methode kopiert, den Status der *pOrgBar* in den aktuellen Bereich.

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

*"lpszclassname"*<br/>
[in] Gibt den Namen der Windows-Klasse.

*dwStyle*<br/>
[in] Gibt an, der die Stilattribute für Fenster. Weitere Informationen finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Gibt an, die ursprüngliche Größe und Position der der *pParentWnd* Fenster, in Clientkoordinaten.

*pParentWnd*<br/>
[in, out] Gibt das übergeordnete Fenster dieses Bereichs an.

*nID*<br/>
[in] Gibt die ID des Bereichs.

*dwControlBarStyle*<br/>
[in] Gibt das Format für den Bereich. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).

*pContext*<br/>
[in, out] Gibt den Kontext Erstellen des Bereichs.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich wurde erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.

Wenn Sie nicht explizit initialisiert haben [cpane:: M_recentdockinfo](#m_recentdockinfo) vor dem Aufruf `Create`, den Parameter *Rect* verwendet werden, wie das Rechteck aus, wenn floating oder im Bereich andocken.

##  <a name="createdefaultminiframe"></a>  Cpane:: Createdefaultminiframe

Erstellt ein Minirahmenfenster für einen unverankerten Bereichs klicken.

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>Parameter

*rectInitial*<br/>
[in] Gibt an, die ursprüngliche Größe und Position in Bildschirmkoordinaten, der das Minirahmenfenster erstellen.

### <a name="return-value"></a>Rückgabewert

Das neu erstellte Minirahmenfenster.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, durch das Framework ein Minirahmenfenster zu erstellen, wenn ein Bereich abgedockt wird. Das Minirahmenfenster kann von sein [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) oder eines Typs [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Ein Minirahmenfenster mit mehreren wird erstellt, wenn der Bereich den AFX_CBRS_FLOAT_MULTI Stil.

Die Laufzeit-Klasseninformationen für das Minirahmenfenster befindet sich in der `CPane::m_pMiniFrameRTC` Member. Sie können eine abgeleitete Klasse verwenden, dieses Element festlegen, wenn Sie benutzerdefinierte Minirahmenfenster erstellen möchten.

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

*dwStyleEx*<br/>
[in] Gibt Attribute an erweiterten Stil. Weitere Informationen finden Sie unter [erweiterte Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

*"lpszclassname"*<br/>
[in] Gibt den Namen der Windows-Klasse.

*dwStyle*<br/>
[in] Gibt die Stilattribute für die Fenster an. Weitere Informationen finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Gibt an, die ursprüngliche Größe und Position der der *pParentWnd* Fenster, in Clientkoordinaten.

*pParentWnd*<br/>
[in, out] Gibt das übergeordnete Fenster dieses Bereichs an.

*nID*<br/>
[in] Gibt die ID des Bereichs.

*dwControlBarStyle*<br/>
[in] Gibt das Format für den Bereich. Weitere Informationen finden Sie unter [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex).

*pContext*<br/>
[in, out] Gibt den Kontext erstellen, für den Bereich.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich wurde erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode erstellt einen Windows-Bereich und fügt es der `CPane` Objekt.

Wenn Sie nicht explizit initialisiert haben [cpane:: M_recentdockinfo](#m_recentdockinfo) vor dem Aufruf `CreateEx`, den Parameter *Rect* verwendet werden, wie das Rechteck aus, wenn floating oder im Bereich andocken.

##  <a name="dockbymouse"></a>  CPane::DockByMouse

Dockt einen Bereich mit der Maus an.

```
virtual BOOL DockByMouse(CBasePane* pDockBar);
```

### <a name="parameters"></a>Parameter

*pDockBar*<br/>
[in] Gibt an, Bereich "Basis", um diesem Bereich anzudocken.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich erfolgreich angedockt wurde. andernfalls "false".

##  <a name="dockpane"></a>  CPane::DockPane

Dockt das unverankerten Bereichs klicken auf einen Basis-Bereich an.

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*pDockBar*<br/>
[in, out] Gibt an, die Basis Bereich aus, um diesen Bereich zum Andocken.

*lpRect*<br/>
[in] Gibt das Rechteck im Basis-Bereich, in denen dieser Bereich befindet sich angedockt werden.

*dockMethod*<br/>
[in] Gibt an, die zu verwendende docking-Methode. Verfügbare Optionen lauten wie folgt aus:

|Option|Beschreibung|
|------------|-----------------|
|DM_UNKNOWN|Das Framework verwendet diese Option aus, wenn die docking-Methode nicht bekannt ist. Im Bereich werden die letzte unverankerte Position nicht gespeichert werden. Sie können diese Option auch verwenden, programmgesteuert einen Bereich angedockt wird, wenn Sie nicht verfügen, um die Position des letzten unverankerte zu speichern.|
|DM_MOUSE|Wird intern verwendet.|
|DM_DBL_CLICK|Diese Option wird verwendet, wenn das ziehelement doppelgeklickt wird. Der Bereich wird auf der letzten Position des andockbaren neu positioniert. Wenn Sie im Bereich durch Doppelklicken auf abgedockt ist, wird im Bereich an der Position des letzten unverankerte neu positioniert werden.|
|DM_SHOW|Diese Option kann verwendet werden, um programmgesteuert auf den Bereich anzudocken. Im Bereich werden die aktuellste unverankerte Position gespeichert.|
|DM_RECT|Der Bereich angedockt ist, in der Region, die angegeben wird *LpRect*.|
|DM_STANDARD|Wenn Sie diese Option verwenden, zeichnet das Framework Bereich als eine Gliederung Frame, während dieser verschoben wird.|

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich erfolgreich angedockt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode Dockt den Bereich an, auf der Basis-Bereich, der angegeben wird die *pDockBar* Parameter. Sie müssen zuerst aktivieren, durch den Aufruf Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).

##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard

Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.

```
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```

### <a name="parameters"></a>Parameter

*bWasDocked*<br/>
[in] True, wenn der Bereich erfolgreich angedockt wurde. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt immer die **dies** Zeiger.

### <a name="remarks"></a>Hinweise

Diese Methode wird verwendet, nur für die Bereiche, die abgeleitet sind die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md). Weitere Informationen finden Sie unter [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).

##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow

Dockt einen andockbaren Bereich in einen Datenrahmen an.

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

*dwAlignment*<br/>
[in] Die Seite des übergeordneten Rahmens, die Sie im Bereich, um andocken möchten.

*lpRect*<br/>
[in] Die angegebene Größe.

*dwDockFlags*<br/>
[in] Ignoriert.

*pRelativeBar*<br/>
[in] Ignoriert.

*nRelativeIndex*<br/>
[in] Ignoriert.

*bOuterEdge*<br/>
[in] Wenn "true", und es andere andockbare Bereiche auf der Seite mit den vom angegebenen sind *DwAlignment*, der Bereich angedockt ist, außerhalb von den anderen Bereichen, näher an den Rand des übergeordneten Rahmens. Wenn "FALSE" ist der Bereich in der Mitte des Clientbereichs näher angedockt.

### <a name="return-value"></a>Rückgabewert

FALSE, wenn auf einen bereichsteiler ( [CPaneDivider-Klasse](../../mfc/reference/cpanedivider-class.md)) kann nicht erstellt werden; andernfalls "true" fest.

### <a name="remarks"></a>Hinweise

##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars

Gibt an, ob Sie einen anderen Bereich in der gleichen Zeile angedockt werden können, in dem der aktuelle Bereich angedockt ist.

```
virtual BOOL DoesAllowSiblingBars() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn in diesem Bereich auf derselben Zeile, als Sie selbst zu einem anderen Bereich angedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Sie können aktivieren oder deaktivieren Sie dieses Verhalten durch Aufrufen von [CPane::SetExclusiveRowMode](#setexclusiverowmode).

In der Standardeinstellung Symbolleisten haben exklusive Zeilenmodus deaktiviert, und die Menüleisten hat exklusiven Zeilenmodus aktiviert.

##  <a name="floatpane"></a>  CPane::FloatPane

Wird im Bereich verschoben.

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,
    bool bShow = true);
```

### <a name="parameters"></a>Parameter

*rectFloat*<br/>
[in] Gibt den Speicherort ein, in Bildschirmkoordinaten, an den Bereich zu positionieren, wenn Sie es abgedockt wird.

*dockMethod*<br/>
[in] Gibt die docking-Methode zu verwenden, wenn der Bereich abgedockt wird. Eine Liste der möglichen Werte, finden Sie unter [CPane::DockPane](#dockpane).

*bShow*<br/>
[in] True, um im Bereich, wenn abgedockt angezeigt. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

TRUE, wenn im Bereich erfolgreich abgedockt wurde, oder wenn der Bereich kann nicht da abgedockt werden [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) gibt "false" ist, andernfalls "false" zurück.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um den Bereich an der Position, die angegeben wird, "float" die *RectFloat* Parameter. Diese Methode erstellt automatisch ein Minirahmenfenster der übergeordneten für den Bereich.

##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize

Gibt die Menge, in Pixel, die den Bereich zu erweitern, kann zurück.

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn der Bereich horizontal angedockt ist, ist der Rückgabewert der verfügbaren Breite; Andernfalls ist der Rückgabewert der verfügbaren Höhe.

### <a name="remarks"></a>Hinweise

##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize

Gibt die Menge, in Pixel, die im Bereich verkleinert werden kann.

```
virtual int GetAvailableStretchSize() const;
```

### <a name="return-value"></a>Rückgabewert

Das Ausmaß in Pixel, die im Bereich verkleinert werden kann. Wenn der Bereich horizontal angedockt ist, wird diese Menge der verfügbaren Breite; Andernfalls ist es die verfügbare Höhe.

### <a name="remarks"></a>Hinweise

Stretch beträgt die verfügbare Größe wird durch Subtrahieren des minimal zulässige Größe für den Bereich berechnet ( [CPane::GetMinSize](#getminsize)) von der aktuellen Größe ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).

##  <a name="getborders"></a>  CPane::GetBorders

Gibt die Breite des Rahmens des Bereichs zurück.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die aktuelle Breite der einzelnen Seite des Bereichs in Pixel enthält. Z. B. der Wert, der die `left` Mitglied der `CRect` Objekt ist die Breite des linken Rahmens.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Festlegen der Größe der Rahmen [CPane::SetBorders](#setborders).

##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot

Gibt die *Hotspot* für den Bereich.

```
CPoint GetClientHotSpot() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die *Hotspot* ist die Stelle im Bereich, die der Benutzer auswählt, und verschieben Sie den Bereich enthält. Ein Hotspot wird für flüssige Animation verwendet, wenn der Bereich von einer verankerten Position verschoben wird.

##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow

Gibt die Dock-Zeile zurück ( [CDockingPanesRow-Klasse](../../mfc/reference/cdockingpanesrow-class.md)) in dem der Bereich angedockt ist.

```
CDockingPanesRow* GetDockSiteRow() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CDockingPanesRow`*, verweist auf die Dock-Zeile, in dem der Bereich angedockt ist, oder NULL, wenn der Bereich nicht angedockt ist.

##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode

Bestimmt, ob der Bereich im Zeilenmodus exklusiv ist.

```
virtual BOOL GetExclusiveRowMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich im Zeilenmodus exklusiv ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Weitere Informationen zu exklusiven Zeilenmodus, finden Sie unter [CPane::SetExclusiveRowMode](#setexclusiverowmode).

##  <a name="gethotspot"></a>  CPane::GetHotSpot

Gibt den Hotspot, die in einer zugrunde liegenden gespeicherten `CMFCDragFrameImpl` Objekt.

```
CPoint GetHotSpot() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die `CPane` -Klasse enthält eine `CMFCDragFrameImpl` Objekt `m_dragFrameImpl`, d. h. für das Zeichnen des Rechtecks, das angezeigt wird, wenn der Benutzer einen Bereich in der standard Andockmodus verantwortlich. Den Hotspot wird zum Zeichnen des Rechtecks relativ zu der aktuellen Position, wenn der Benutzer im Bereich bewegt.

##  <a name="getminsize"></a>  CPane::GetMinSize

Ruft den minimal zulässigen Größe für den Bereich ab.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parameter

*size*<br/>
[out] Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.

### <a name="remarks"></a>Hinweise

##  <a name="getpanename"></a>  CPane::GetPaneName

Ruft den Titel für den Bereich ab.

```
virtual void GetPaneName(CString& strName) const;
```

### <a name="parameters"></a>Parameter

*strName*<br/>
[out] Ein `CString` -Objekt, das mit den Beschriftungsnamen gefüllt ist.

### <a name="remarks"></a>Hinweise

Der Titel im Bereich wird im Headerbereich angezeigt, wenn der Bereich angedockt oder unverankert ist. Wenn der Bereich Teil einer Gruppe im Registerkartenformat ist, wird der Titel in der Registerkarte angezeigt. Wenn der Bereich im Modus "automatisch ausblenden" ist, wird der Titel angezeigt, auf eine `CMFCAutoHideButton`.

##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect

Ruft die *virtuellen Rechteck* des Bereichs.

```
void GetVirtualRect(CRect& rectVirtual) const;
```

### <a name="parameters"></a>Parameter

*rectVirtual*<br/>
[out] Ein `CRect` -Objekt, das mit dem virtuellen Rechteck ausgefüllt wird.

### <a name="remarks"></a>Hinweise

Wenn ein Bereich verschoben wird, speichert das Framework die ursprüngliche Position des Bereichs in einem virtuellen Rechteck. Das Framework kann das virtuelle Rechteck verwenden, zum Wiederherstellen der ursprünglichen Position des Bereichs.

Rufen Sie Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben nicht.

##  <a name="ischangestate"></a>  CPane::IsChangeState

Wie der Bereich wird verschoben wird, wird diese Methode die Position relativ zu anderen Bereichen, analysiert andocken, Zeilen und Minirahmenfenster und den entsprechenden AFX_CS_STATUS Wert zurückgibt.

```
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,
    CBasePane** ppTargetBar) const;
```

### <a name="parameters"></a>Parameter

*nOffset*<br/>
[in] Gibt an, andockbaren Vertraulichkeit. Z. B. ein Bereich, der innerhalb verschoben wird *nOffset* Pixel in einer Zeile Dock angedockt werden.

*ppTargetBar*<br/>
[in] Wenn die Methode zurückgibt, *PpTargetBar* enthält entweder einen Zeiger auf das Objekt, das auf die im aktuelle Bereich angedockt werden soll, oder NULL, wenn keine Andocken erfolgen soll.

### <a name="return-value"></a>Rückgabewert

Eine der folgenden AFX_CS_STATUS Werte:

|Wert|Beschreibung|
|-----------|-----------------|
|CS_NOTHING|Der Bereich ist nicht in der Nähe eine docksite. Das Framework ist nicht auf den Bereich anzudocken.|
|CS_DOCK_IMMEDIATELY|Der Bereich wird über eine docksite, und der DT_IMMEDIATE-Stil ist aktiviert. Das Framework Dockt den Bereich sofort an.|
|CS_DELAY_DOCK|Der Bereich wird über eine docksite, die entweder einen anderen andockbaren Bereich oder eine Kante der Hauptframe ist. Das Framework Dockt den Bereich an, wenn der Benutzer das verschieben.|
|CS_DELAY_DOCK_TO_TAB|Der Bereich wird über eine docksite, die bewirkt, dass den Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Bereich entweder über die Beschriftung von einem anderen andockbaren Bereich oder der Registerkartenbereich von einem Bereich im Registerkartenformat ist. Das Framework Dockt den Bereich an, wenn der Benutzer das verschieben.|

##  <a name="isdragmode"></a>  CPane::IsDragMode

Gibt an, ob der Bereich verschoben wird.

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich verschoben wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd

Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd-Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich in einem Fenster mit mehreren Rahmen. andernfalls "false".

### <a name="remarks"></a>Hinweise

Nur andockbare Bereiche können in einem Multipane-Rahmenfenster "float". Aus diesem Grund `CPane::IsInFloatingMultiPaneFrameWnd` gibt immer "false" zurück.

##  <a name="isleftof"></a>  CPane::IsLeftOf

Bestimmt, ob im Bereich (oder höher) bleibt das angegebene Rechteck.

```
bool IsLeftOf(
    CRect rect,
    bool bWindowRect = true) const;
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
[in] Ein `CRect` -Objekt, das für den Vergleich verwendet wird.

*bWindowRect*<br/>
[in] True gibt an, *Rect* wird davon ausgegangen, dass die Bildschirmkoordinaten; Wenn "FALSE" enthalten *Rect* wird davon ausgegangen, dass Clientkoordinaten enthalten.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Ist der Bereich horizontal angedockt, diese Methode überprüft, ob am Speicherort des Links wird *Rect*. Hingegen diese Methode überprüft, ob der Speicherort über *Rect*.

##  <a name="isresizable"></a>  CPane::IsResizable

Gibt an, ob der Bereich geändert werden kann.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich geändert werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Base `CPane` Objekte kann nicht geändert werden.

Dock-Manager verwendet das Flag mit veränderbarer Größe um Bereichslayout zu bestimmen. Nicht veränderbare Größen Bereiche befinden sich immer an den äußeren Kanten des übergeordneten Rahmens.

Nicht veränderbare Größen Bereiche dürfen nicht in Container andocken sein.

##  <a name="istabbed"></a>  CPane::IsTabbed

Bestimmt, ob der Bereich in das Registerkarten-Steuerelement von einem Fenster im Registerkartenformat eingefügt wurde.

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich im Registerkartenformat ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Status im Registerkartenformat separat behandelt wird, aus der Gleitkommazahlen, angedockt und automatisch im Hintergrund Zustände.

##  <a name="loadstate"></a>  CPane::LoadState

Lädt den Zustand des Bereichs aus der Registrierung.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Profilname.

*nIndex*<br/>
[in] Profil-Index.

*uiID*<br/>
[in] Im Bereich-ID an.

### <a name="return-value"></a>Rückgabewert

True, wenn der Zustand des Bereichs erfolgreich geladen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um den Zustand des Bereichs in der Registrierung geladen werden. Überschreiben Sie diese in einer abgeleiteten Klasse zusätzliche Informationen zu laden, die durch gespeichert wird, [CPane::SaveState](#savestate).

Wenn Sie diese Methode überschreiben, auch rufen Sie die Basismethode auf, und zurückgeben Sie "false", wenn die Basismethode "false" zurückgibt.

##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize

Ermöglicht die konsistente Behandlung von minimalen Bereich Größen.

```
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;
```

### <a name="remarks"></a>Hinweise

Wenn eine oder mehrere andockbare Bereiche in Ihrer Anwendung außer Kraft setzen `GetMinSize`, oder wenn die Anwendung aufruft `SetMinSize`, Sie möchten dieses statische Element auf "true" festgelegt, damit das Framework um konsistent zu behandeln, wie Bereiche groß werden können.

Wenn dieser Wert auf "true" festgelegt ist, werden alle Bereiche, deren Größe soll, geringer als die Mindestzeit reduziert werden, abgeschnitten, nicht gestreckt wird. Da das Framework Fensterbereiche zu größenanpassung Bereich verwendet wird, ändern Sie nicht die Größe des den Fensterbereich für andockbare Bereiche aus, wenn dieser Wert auf "true" festgelegt ist.

##  <a name="m_recentdockinfo"></a>  Cpane:: M_recentdockinfo

Enthält die aktuellen Informationen zur andocken.

```
CRecentDockSiteInfo m_recentDockInfo;
```

### <a name="remarks"></a>Hinweise

Das Framework speichert die neueste Andocken Statusinformationen für den Bereich, in diesem Member.

##  <a name="movebyalignment"></a>  CPane::MoveByAlignment

Verschiebt den Bereich und das virtuelle Rechteck den angegebenen Betrag an.

```
BOOL MoveByAlignment(
    DWORD dwAlignment,
    int nOffset);
```

### <a name="parameters"></a>Parameter

*dwAlignment*<br/>
[in] Gibt die im Bereich Ausrichtung.

*nOffset*<br/>
[in] Das Ausmaß in Pixel, um den Bereich und das virtuelle Rechteck verschieben.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

*DwAlignment* kann eines der folgenden Werte sein:

|Wert|Beschreibung|
|-----------|-----------------|
|CBRS_ALIGN_TOP|Ermöglicht der Bereich am oberen Rand der Clientbereich eines Rahmenfensters angedockt werden.|
|CBRS_ALIGN_BOTTOM|Ermöglicht der Bereich am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.|
|CBRS_ALIGN_LEFT|Ermöglicht der Bereich auf die linke Seite des Clientbereichs eines Frame-Fensters angedockt werden.|
|CBRS_ALIGN_RIGHT|Ermöglicht der Bereich auf die rechte Seite des Clientbereichs eines Frame-Fensters angedockt werden.|
|CBRS_ALIGN_ANY|Können den Bereich, um jede Seite des Clientbereichs des ein Framefenster angedockt werden.|

Wenn *DwAlignment* enthält das CBRS_ALIGN_LEFT oder CBRS_ALIGN_RIGHT-Flag, das Bereich und die virtuellen Rechteck werden verschoben, horizontal ist, andernfalls Wenn *DwAlignment* enthält die CBRS_ALIGN_TOP oder CBRS_ALIGN _Untere Gruppe von Flags, die im Bereich und die virtuellen Rechteck vertikal verschoben.

##  <a name="movepane"></a>  CPane::MovePane

Verschiebt den Bereich in das angegebene Rechteck.

```
virtual CSize MovePane(
    CRect rectNew,
    BOOL bForceMove,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parameter

*rectNew*<br/>
[in] Gibt das neue Rechteck für den Bereich an.

*bForceMove*<br/>
[in] True gibt an, gibt diese Methode die Größe der minimalen zulässigen Bereich ignoriert ( [CPane::GetMinSize](#getminsize)) ist, andernfalls im Bereich verwendet wird, falls erforderlich, um sicherzustellen, dass sie mindestens den minimal zulässigen Größe angepasst.

*hdwp*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` Objekt, das die Unterschiede in der Breite und Höhe der Rechtecke den alten und neuen enthält (alte Rechteck - *RectNew*).

### <a name="remarks"></a>Hinweise

Diese Methode wird nur für andockbare Bereiche verwendet.

##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent

Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parameter

*pWndOldParent*<br/>
[in, out] Im Bereich des vorherigen übergeordneten Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs aufgrund eines andockbaren "oder" Gleitkomma-Vorgangs geändert wurde.

##  <a name="onafterdock"></a>  CPane::OnAfterDock

Vom Framework aufgerufen, wenn Sie ein Bereich angedockt wurden, hat.

```
virtual void OnAfterDock(
    CBasePane* pBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in] Dieser Parameter wird nicht verwendet.

*lpRect*<br/>
[in] Dieser Parameter wird nicht verwendet.

*dockMethod*<br/>
[in] Dieser Parameter wird nicht verwendet.

##  <a name="onafterfloat"></a>  CPane::OnAfterFloat

Vom Framework aufgerufen, nachdem ein Bereich wird verschoben.

```
virtual void OnAfterFloat();
```

### <a name="remarks"></a>Hinweise

Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn die Verarbeitung auszuführen, nachdem ein Bereich wird verschoben werden sollen.

##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent

Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parameter

*pWndNewParent*<br/>
[in, out] Gibt an, das neue übergeordnete Fenster.

*bDelay*<br/>
[in] True, um die globale docking-Layout-Anpassung zu verzögern. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs zu ändern, da der Bereich wird ist angedockt oder abgedockt.

Im Bereich wird standardmäßig nicht mit der andockbaren Bereich registrierte durch Aufrufen von `CDockSite::RemovePane`.

##  <a name="onbeforedock"></a>  CPane::OnBeforeDock

Vom Framework aufgerufen, wenn der Bereich zum Andocken wird.

```
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*ppDockBar*<br/>
[in, out] Gibt an, dem Bereich, dem diesen Bereich zum Andocken wird.

*lpRect*<br/>
[in] Gibt das Rechteck andocken.

*dockMethod*<br/>
[in] Gibt die docking-Methode.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Bereich angedockt werden kann. Wenn die Funktion "false" zurückgibt, wird der docking-Vorgang abgebrochen.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Bereich ist angedockt werden. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Sie möchten, um Verarbeitungsschritte auszuführen, bevor Sie schließlich ein Bereich angedockt ist.

##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat

Vom Framework aufgerufen, wenn ein Bereich, der auf "float" geht.

```
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*rectFloat*<br/>
[in] Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand befindet.

*dockMethod*<br/>
[in] Gibt die docking-Methode des Bereichs.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich abgedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Bereich, der auf "float" geht. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Sie möchten, um Verarbeitungsschritte auszuführen, bevor Bereich schließlich gleitet.

##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton

Vom Framework aufgerufen, wenn der Benutzer die Schaltfläche "Schließen" für die Beschriftung für den Bereich drückt.

```
virtual void OnPressCloseButton();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Benutzer drückt die **schließen** Schaltfläche auf den Bereich der Beschriftung. Empfangen von Benachrichtigungen über die **schließen** Ereignis können Sie diese Methode in einer abgeleiteten Klasse überschreiben.

##  <a name="onshowcontrolbarmenu"></a>  Cpane:: Onshowcontrolbarmenu

Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.

```
virtual BOOL OnShowControlBarMenu(CPoint point);
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
[in] Gibt den Speicherort im Menü.

### <a name="return-value"></a>Rückgabewert

True, wenn das Menü angezeigt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Menü enthält mehrere Elemente, die Sie im Bereich des Verhalten, nämlich angeben können: **Unverankert**, **Andocken**, **automatisch im Hintergrund**, und **ausblenden**. Sie können dieses Menü für alle Bereiche aktivieren, durch den Aufruf [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).

##  <a name="recalclayout"></a>  Cpane:: RecalcLayout

Berechnet die Layoutinformationen für den Bereich an.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Hinweise

Wenn der Bereich angedockt ist, aktualisiert diese Methode das virtuelle Rechteck für den Bereich durch Festlegen der Größe der aktuellen Größe des Bereichs.

Wenn der Bereich verankert ist, benachrichtigt diese Methode der übergeordneten Minirahmenfensters Anpassen der Größe des Bereichs auf die Größe des der Minirahmenfensters an. Das Framework stellt sicher, dass die Minirahmenfensters mindestens den minimal zulässigen Größe für den Bereich ( [CPane::GetMinSize](#getminsize)) und ändert die Größe der Minirahmenfensters bei Bedarf.

##  <a name="savestate"></a>  CPane::SaveState

Speichert den Zustand des Bereichs in der Registrierung.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Profilname.

*nIndex*<br/>
[in] Profil-Index.

*uiID*<br/>
[in] Im Bereich-ID an.

### <a name="return-value"></a>Rückgabewert

True, wenn der Zustand erfolgreich gespeichert wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode beim Speichern den Zustand des Bereichs in der Registrierung. Außer Kraft setzen `SaveState` in einer abgeleiteten Klasse, um weitere Informationen zu speichern.

Wenn Sie diese Methode überschreiben, auch rufen Sie die Basismethode auf, und zurückgeben Sie "false", wenn die Basismethode "false" zurückgibt.

##  <a name="setactiveingroup"></a>  Cpane:: Setactiveingroup

Bitflags, die einen Bereich als aktiv.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Parameter

*bActive*<br/>
[in] Ein boolescher Wert, der angibt, ob der Bereich als aktiv gekennzeichnet ist.

### <a name="remarks"></a>Hinweise

Wenn Sie ein andockbaren Bereich angezeigt wird, oder eine Schaltfläche zum automatischen Ausblenden wird ausgewählt, wird im entsprechenden Bereich der automatisch ausblendbaren als aktiv markiert.

Die Darstellung einer Schaltfläche zum automatischen Ausblenden, die dem Bereich zugeordnet ist, basiert auf zwei Faktoren. Wenn der Bereich aktiv ist und die `static BOOL CMFCAutoHideButton::m_bOverlappingTabs` ist "true", das Framework zeigt der automatisch ausblendbaren Schaltfläche ein Symbol und eine Bezeichnung. Für einen inaktiven Bereich zeigt das Framework nur das Symbol "automatisch ausblenden".

Wenn `CMFCAutoHideButton::m_bOverlappingTabs` ist "false", oder wenn der Bereich nicht in einer Gruppe befindet, zeigt das Framework die Schaltfläche zum automatischen Ausblenden zugeordnete als ein Symbol und eine Bezeichnung.

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

*cxLeft*<br/>
[in] Gibt die Breite des linken Rahmens des Bereichs in Pixel an.

*cyTop*<br/>
[in] Gibt die Breite des oberen Rahmens des Bereichs in Pixel an.

*cxRight*<br/>
[in] Gibt die Breite des rechten Rahmens des Bereichs in Pixel an.

*cyBottom*<br/>
[in] Gibt die Breite des unteren Rahmens des Bereichs in Pixel an.

*lpRect*<br/>
[in] Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die Breite der einzelnen Rahmen des Bereichs in Pixel enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um die Größe des Bereichs Rahmen fest.

##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot

Legt die *Hotspot* für den Bereich.

```
void SetClientHotSpot(const CPoint& ptNew);
```

### <a name="parameters"></a>Parameter

*ptNew*<br/>
[in] Ein `CPoint` Objekt, das den neuen Hotspot angibt.

### <a name="remarks"></a>Hinweise

Die *Hotspot* ist die Stelle im Bereich, die der Benutzer auswählt, und verschieben Sie den Bereich enthält. Ein Hotspot wird für flüssige Animation verwendet, wenn im Bereich von einer verankerten Position gezogen wird.

##  <a name="setdockstate"></a>  CPane::SetDockState

Stellt Statusinformationen für den Bereich andocken.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>Parameter

*pDockManager*<br/>
[in] Zeiger auf die Dock-Manager für das Hauptrahmenfenster.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework Andocken aktuelle Zustandsinformationen für den Bereich der wiederherzustellenden aufgerufen. Ein Bereich speichert die aktuelle Andocken Zustandsinformationen in [cpane:: M_recentdockinfo](#m_recentdockinfo). Weitere Informationen finden Sie unter den [CRecentDockSiteInfo-Klasse](../../mfc/reference/crecentdocksiteinfo-class.md).

Sie können auch aufrufen, dass diese Methode, um den andockzustand festgelegt werden soll, wenn Sie im Bereich-Informationen aus einer externen Quelle geladen werden.

##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode

Aktiviert oder deaktiviert den Zeilenmodus für exklusive.

```
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```

### <a name="parameters"></a>Parameter

*bExclusive*<br/>
[in] True, um exklusiven Zeilenmodus zu aktivieren. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Aktivieren oder deaktivieren exklusive Zeilenmodus auf. Wenn ein Bereich im Zeilenmodus exklusiv ist, kann keine sie alle anderen Symbolleisten die gleiche Zeile freigeben.

In der Standardeinstellung alle Symbolleisten haben exklusive Zeilenmodus deaktiviert, und die Menüleisten hat exklusiven Zeilenmodus aktiviert.

##  <a name="setminsize"></a>  CPane::SetMinSize

Legt fest, den minimal zulässige Größe für den Bereich.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
[in] Ein `CSize` Objekt, das den minimal zulässige Größe für den Bereich enthält.

### <a name="remarks"></a>Hinweise

##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect

Legt die *virtuellen Rechteck* des Bereichs.

```
void SetVirtualRect(
    const CRect& rect,
    BOOL bMapToParent = TRUE);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
[in] Ein `CRect` -Objekt, das gibt an, das virtuelle Rechteck festgelegt werden.

*bMapToParent*<br/>
[in] Geben Sie "true", wenn *Rect* Punkt relativ zum übergeordneten Fenster enthält.

### <a name="remarks"></a>Hinweise

Ein *virtuellen Rechteck* die ursprüngliche Position eines Bereichs speichert, wenn es verschoben wird. Das Framework kann das virtuelle Rechteck verwenden, die ursprüngliche Position wiederhergestellt.

Rufen Sie Methoden, die mit virtuellen Rechtecke verknüpft sind, es sei denn, Sie Bereiche programmgesteuert verschieben nicht.

##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC

Legt fest, die laufzeitklasseninformationen für das Standard-Minirahmenfenster.

```
void SetMiniFrameRTC(CRuntimeClass* pClass);
```

### <a name="parameters"></a>Parameter

*pClass*<br/>
[in, out] Gibt die Laufzeit-Klasseninformationen für das Minirahmenfenster an.

### <a name="remarks"></a>Hinweise

Wenn ein Bereich abgedockt ist, wird Sie auf versetzt einen [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) (Minirahmenfenster). Sie können angeben, dass ein benutzerdefiniertes `CPaneFrameWnd`-abgeleitete Klasse, die verwendet wird, wenn [cpane:: Createdefaultminiframe](#createdefaultminiframe) aufgerufen wird.

##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos

Wird im Bereich vertikal oder horizontal andockstil Grundlage gestreckt.

```
virtual int StretchPaneDeferWndPos(
    int nStretchSize,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parameter

*nStretchSize*<br/>
[in] Das Ausmaß in Pixel, um stretch-Bereich. Verwenden Sie einen negativen Wert, um den Bereich zu verkleinern.

*hdwp*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Der tatsächliche Umfang, in Pixeln, um die im Bereich ein stretching durchgeführt wurde.

### <a name="remarks"></a>Hinweise

Wenn erforderlich, diese Methode ändert *nStretchSize* um sicherzustellen, dass im Bereich Grenzwerte nicht überschritten wird. Diese Grenzwerte werden abgerufen, durch den Aufruf [CPane::GetAvailableStretchSize](#getavailablestretchsize) und [CPane::GetAvailableExpandSize](#getavailableexpandsize).

##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide

Schaltet automatischen Ausblendemodus.

```
virtual void ToggleAutoHide();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um den automatischen Ausblendemodus umschalten. Ein Bereich muss an einem Hauptrahmenfenster angedockt sein, um zum automatischen Ausblenden-Modus wechseln.

##  <a name="undockpane"></a>  CPane::UndockPane

Entfernt den Bereich aus der DockPosition, Standard-Schieberegler oder ein Minirahmenfenster, in dem sie zurzeit angedockt wird.

```
virtual void UndockPane(BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parameter

*bDelay*<br/>
[in] False gibt an, das Framework ruft [cbasepane:: Adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) Layout des Docks anpassen.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um programmgesteuert einen Bereich abdocken.

##  <a name="updatevirtualrect"></a>  CPane::UpdateVirtualRect

Aktualisiert das virtuelle Rechteck.

```
void UpdateVirtualRect();
void UpdateVirtualRect(CPoint ptOffset);
  void UpdateVirtualRect(CSize sizeNew);
```

### <a name="parameters"></a>Parameter

*ptOffset*<br/>
[in] Ein `CPoint` Objekt, das einen Offset, um den Bereich verschieben angibt.

*sizeNew*<br/>
[in] Ein `CSize` Objekt, das eine neue Größe für den Bereich angibt.

### <a name="remarks"></a>Hinweise

Die erste Überladung wird das virtuelle Rechteck mithilfe der aktuellen Position und Größe des Bereichs.

Die zweite Überladung der Betrag, der angegeben wird das virtuelle Rechteck verschiebt *PtOffset*.

Die dritte Überladung wird das Rechteck des virtuelle, indem Sie die aktuelle Position im Bereich und die Größe, die angegeben wird *SizeNew*.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)
