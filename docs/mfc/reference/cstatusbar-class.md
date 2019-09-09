---
title: CStatusBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
ms.openlocfilehash: 48de31d95814ce5fc1fb015e69cf38d73337cb79
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502340"
---
# <a name="cstatusbar-class"></a>CStatusBar-Klasse

Eine Steuerleiste mit einer Zeile von Textausgabebereichen ("Indikatoren" genannt).

## <a name="syntax"></a>Syntax

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStatusBar::CStatusBar](#cstatusbar)|Erstellt ein `CStatusBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStatusBar::CommandToIndex](#commandtoindex)|Ruft den Index für eine angegebene Indikator-ID ab.|
|[CStatusBar::Create](#create)|Erstellt die Statusleiste, fügt Sie an das `CStatusBar` -Objekt an und legt die anfängliche Schriftart und die Balken Höhe fest.|
|[CStatusBar::CreateEx](#createex)|Erstellt ein `CStatusBar` -Objekt mit zusätzlichen Stilen für das `CStatusBarCtrl` eingebettete Objekt.|
|[CStatusBar::DrawItem](#drawitem)|Wird aufgerufen, wenn sich ein visueller Aspekt eines Besitzers-Status leisten-Steuer Elements ändert.|
|[CStatusBar::GetItemID](#getitemid)|Ruft die Indikator-ID für einen angegebenen Index ab.|
|[CStatusBar::GetItemRect](#getitemrect)|Ruft das Anzeige Rechteck für einen angegebenen Index ab.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Ruft Indikator-ID,-Stil und-Breite für einen angegebenen Index ab.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Ruft den Indikator Stil für einen angegebenen Index ab.|
|[CStatusBar::GetPaneText](#getpanetext)|Ruft den Indikator Text für einen angegebenen Index ab.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.|
|[CStatusBar::SetIndicators](#setindicators)|Legt Indikator-IDs fest.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Legt Indikator-ID,-Stil und-Breite für einen angegebenen Index fest.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Legt den Indikator Stil für einen angegebenen Index fest.|
|[CStatusBar::SetPaneText](#setpanetext)|Legt den Indikator Text für einen angegebenen Index fest.|

## <a name="remarks"></a>Hinweise

Die Ausgabe Bereiche werden in der Regel als Nachrichtenzeilen und als Status Indikatoren verwendet. Beispiele hierfür sind die Menü Hilfe-Nachrichtenzeilen, in denen der ausgewählte Menübefehl kurz erläutert wird, sowie die Indikatoren, die den Status der Scrollsperre, der NUM-Sperre und anderer Schlüssel anzeigen.

[CStatusBar:: GetStatusBarCtrl](#getstatusbarctrl), eine Member-Funktion, die für MFC 4,0 neu ist, ermöglicht es Ihnen, die Unterstützung für die Statusleiste und zusätzliche Funktionalität der allgemeinen Windows-Steuerelemente zu nutzen. `CStatusBar`Member-Funktionen verfügen über die meisten Funktionen der allgemeinen Windows-Steuerelemente. Wenn Sie jedoch aufzurufen `GetStatusBarCtrl`, können Sie Ihre Status leisten noch mehr über die Merkmale einer Windows 95/98-Statusleiste informieren. Wenn Sie aufzurufen `GetStatusBarCtrl`, wird ein Verweis auf ein `CStatusBarCtrl` -Objekt zurückgegeben. Weitere Informationen zum Entwerfen von Symbolleisten mit allgemeinen Windows-Steuerelementen finden Sie unter [cstatus-STRG](../../mfc/reference/cstatusbarctrl-class.md) . Allgemeinere Informationen zu allgemeinen Steuerelementen finden Sie unter Allgemeine Steuer [Elemente](/windows/win32/Controls/common-controls-intro) in der Windows SDK.

Das Framework speichert Indikator Informationen in einem Array, wobei der äußteste äußteste Indikator an Position 0 ist. Wenn Sie eine Statusleiste erstellen, verwenden Sie ein Array von Zeichen folgen-IDs, die das Framework den entsprechenden Indikatoren zuordnet. Sie können dann entweder eine Zeichen folgen-ID oder einen Index verwenden, um auf einen Indikator zuzugreifen.

Standardmäßig ist der erste Indikator "elastisch": Es wird die Status leisten Länge übernommen, die von den anderen Indikator Bereichen nicht verwendet wird, sodass die anderen Bereiche rechtsbündig ausgerichtet sind.

Gehen Sie folgendermaßen vor, um eine Statusleiste zu erstellen:

1. Erstellen Sie `CStatusBar` das-Objekt.

1. Rufen Sie die [Create](#create) (oder die Funktion "up- [Ex](#createex))" auf, um das Fenster "Statusleiste `CStatusBar` " zu erstellen und an das-Objekt anzufügen.

1. Aufrufen von [setindicator](#setindicators) , um jedem Indikator eine Zeichen folgen-ID zuzuordnen.

Es gibt drei Möglichkeiten, den Text in einem Status Leistenbereich zu aktualisieren:

1. Aufrufen von [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) , um den Text nur in Bereich 0 zu aktualisieren.

1. Aufrufen von [CCmdUI:: SetText](../../mfc/reference/ccmdui-class.md#settext) im ON_UPDATE_COMMAND_UI-Handler der Statusleiste.

1. Aufrufen von [SetPaneText](#setpanetext) , um den Text für einen beliebigen Bereich zu aktualisieren.

Aufrufen von [setpanestyle](#setpanestyle) zum Aktualisieren des Stils eines Status leisten Bereichs.

Weitere Informationen zur Verwendung von `CStatusBar`finden Sie im Artikel zur [Implementierung der Status Leiste in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Technical Note 31: Steuer leisten](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Anforderungen

**Header:** Afxext. h

##  <a name="commandtoindex"></a>CStatusBar:: commandbackindex

Ruft den Indikator Index für eine angegebene ID ab.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parameter

*nIDFind*<br/>
Zeichen folgen-ID des Indikators, dessen Index abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des Indikators, wenn der Vorgang erfolgreich war. -1, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Index des ersten Indikators ist 0 (null).

##  <a name="create"></a>CStatusBar:: Create

Erstellt eine Statusleiste (ein untergeordnetes Fenster) und ordnet diese dem `CStatusBar` -Objekt zu.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Ein Zeiger auf das [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster der Statusleiste übergeordnet ist.

*dwStyle*<br/>
Der Status leisten Stil. Zusätzlich zu den standardmäßigen Windows- [Stilen](../../mfc/reference/styles-used-by-mfc.md#window-styles)werden diese Stile unterstützt.

- Die CBRS_TOP-Steuerleiste befindet sich am oberen Rand des Rahmen Fensters.

- Die CBRS_BOTTOM-Steuerleiste befindet sich am unteren Rand des Rahmen Fensters.

- Die CBRS_NOALIGN-Steuerleiste wird nicht neu positioniert, wenn die Größe des übergeordneten Elements geändert wird.

*nID*<br/>
Die ID des untergeordneten Fensters der Symbolleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Legt auch die ursprüngliche Schriftart fest und legt die Höhe der Statusleiste auf einen Standardwert fest.

##  <a name="createex"></a>CStatusBar:: kreateex

Rufen Sie diese Funktion auf, um eine Statusleiste (ein untergeordnetes Fenster) zu erstellen `CStatusBar` und Sie dem-Objekt zuzuordnen.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Ein Zeiger auf das [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster der Statusleiste übergeordnet ist.

*dwCtrlStyle*<br/>
Zusätzliche Stile für die Erstellung des eingebetteten [cstatus barctrl](../../mfc/reference/cstatusbarctrl-class.md) -Objekts. Der Standardwert gibt eine Statusleiste ohne Größen Zieh Punkt oder QuickInfo-Unterstützung an. Unterstützte StatusBar-Stile:

- SBARS_SIZEGRIP das StatusBar-Steuerelement enthält einen Größen Zieh Punkt am rechten Ende der Statusleiste. Ein Größen Zieh Punkt ähnelt einem Größen Anpassungsrahmen. Es ist ein rechteckiger Bereich, auf den der Benutzer klicken und ziehen kann, um die Größe des übergeordneten Fensters zu ändern.

- SBT_TOOLTIPS die Statusleiste unterstützt Quick Infos.

Ausführliche Informationen zu diesen Stilen finden Sie unter [Settings for the cstatuwaybarctrl](../../mfc/settings-for-the-cstatusbarctrl.md).

*dwStyle*<br/>
Der Stil der Statusleiste. Der Standardwert gibt an, dass am unteren Rand des Frame Fensters eine sichtbare Statusleiste erstellt wird. Wenden Sie eine beliebige Kombination von Status leisten-Steuerelement Stilen an, die unter [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CDialogBar:: Create](../../mfc/reference/cdialogbar-class.md#create)aufgeführt sind Dieser Parameter sollte jedoch immer die Stile WS_CHILD und WS_VISIBLE enthalten.

*nID*<br/>
Die ID des untergeordneten Fensters der Statusleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Funktion legt auch die ursprüngliche Schriftart fest und legt die Höhe der Statusleiste auf einen Standardwert fest.

Verwenden `CreateEx`Sie anstelle von [Create](#create), wenn bestimmte Stile während der Erstellung des eingebetteten StatusBar-Steuer Elements vorhanden sein müssen. Legen Sie z. b. " *dwctrlstyle* " auf "SBT_TOOLTIPS" fest, um Quick Infos in einem Status leisten Objekt anzuzeigen.

##  <a name="cstatusbar"></a>CStatusBar:: CStatusBar

Erstellt ein `CStatusBar` -Objekt, erstellt bei Bedarf eine Standard Schriftart der Statusleiste und legt die Schriftart Eigenschaften auf Standardwerte fest.

```
CStatusBar();
```

##  <a name="drawitem"></a>CStatusBar::D rawitem

Diese Member-Funktion wird von Framework aufgerufen, wenn sich ein visueller Aspekt einer vom Besitzer gezeichneten Statusleiste ändert.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) -Struktur, die Informationen über den erforderlichen Zeichentyp enthält.

### <a name="remarks"></a>Hinweise

Der `itemAction` -Member `DRAWITEMSTRUCT` der-Struktur definiert die Zeichnungs Aktion, die ausgeführt werden soll. Überschreiben Sie diese Member-Funktion, um das Zeichnen für `CStatusBar` ein owner-draw-Objekt zu implementieren Die Anwendung sollte alle GDI-Objekte (Graphics Device Interface), die für den in *lpdrawitemstruct* angegebenen Anzeige Kontext ausgewählt wurden, vor der Beendigung dieser Element Funktion wiederherstellen.

##  <a name="getitemid"></a>CStatusBar:: getItemID

Gibt die ID des durch *nIndex*angegebenen Indikators zurück.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Indikators, dessen ID abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Die ID des durch *nIndex*angegebenen Indikators.

##  <a name="getitemrect"></a>CStatusBar:: GetItemRect

Kopiert die Koordinaten des durch *nIndex* angegebenen Indikators in die-Struktur, auf die von *lprect*verwiesen wird.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Indikators, dessen Rechteck Koordinaten abgerufen werden sollen.

*lpRect*<br/>
Verweist auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des durch *nIndex*angegebenen Indikators empfängt.

### <a name="remarks"></a>Hinweise

Die Koordinaten befinden sich in Pixel relativ zur oberen linken Ecke der Statusleiste.

##  <a name="getpaneinfo"></a>CStatusBar:: getpaneinfo

Legt *NID*, *nstyle*und *cxwidth* auf die ID, den Stil und die Breite des Indikator Bereichs an der durch *nIndex*angegebenen Position fest.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Informationen abgerufen werden sollen.

*nID*<br/>
Verweis auf eine uint, die auf die ID des Bereichs festgelegt ist.

*nStyle*<br/>
Verweis auf einen uint-Wert, der auf den Stil des Bereichs festgelegt ist.

*cxWidth*<br/>
Verweis auf eine Ganzzahl, die auf die Breite des Bereichs festgelegt ist.

##  <a name="getpanestyle"></a>CStatusBar:: getpanestyle

Rufen Sie diese Member-Funktion auf, um den Stil des Bereichs einer Statusleiste abzurufen.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Bereichs, dessen Stil abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Der Stil des Status leisten Bereichs, der durch *nIndex*angegeben wird.

### <a name="remarks"></a>Hinweise

Der Stil eines Bereichs bestimmt, wie der Bereich angezeigt wird.

Eine Liste der Stile, die für Status leisten verfügbar sind, finden Sie unter [Erstellen](#create).

##  <a name="getpanetext"></a>CStatusBar:: getpanetext

Rufen Sie diese Member-Funktion auf, um den Text abzurufen, der in einem Status Leistenbereich angezeigt wird.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Bereichs, dessen Text abgerufen werden soll.

*rString*<br/>
Ein Verweis auf ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den abzurufenden Text enthält.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Text des Bereichs enthält.

### <a name="remarks"></a>Hinweise

Die zweite Form dieser Member-Funktion füllt ein `CString` -Objekt mit dem Zeichen folgen Text.

##  <a name="getstatusbarctrl"></a>CStatusBar:: GetStatusBarCtrl

Diese Member-Funktion ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Enthält einen Verweis auf ein [cstatuenbarctrl](../../mfc/reference/cstatusbarctrl-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Verwenden `GetStatusBarCtrl` Sie, um die Funktionen der allgemeinen Steuerung der Windows-Statusleiste zu nutzen und die Unterstützung von [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) für die Anpassung der Statusleiste zu nutzen. Beispielsweise können Sie mit dem allgemeinen Steuerelement einen Stil angeben, der einen Größen Zieh Punkt auf der Statusleiste enthält, oder Sie können einen Stil angeben, damit die Statusleiste am oberen Rand des Client Bereichs des übergeordneten Fensters angezeigt wird.

Allgemeinere Informationen zu allgemeinen Steuerelementen finden Sie unter Allgemeine Steuer [Elemente](/windows/win32/Controls/common-controls-intro) in der Windows SDK.

##  <a name="setindicators"></a>CStatusBar:: setindicator

Legt die ID jedes Indikators auf den Wert fest, der vom entsprechenden Element des Arrays *lpidarray*angegeben wird, lädt die von jeder ID angegebene Zeichen folgen Ressource und legt den Text des Indikators auf die Zeichenfolge fest.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parameter

*lpIDArray*<br/>
Zeiger auf ein Array von IDs.

*nIDCount*<br/>
Anzahl der Elemente im Array, auf die von *lpidarray*verwiesen wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="setpaneinfo"></a>CStatusBar:: setpaneinfo

Legt den angegebenen Indikator Bereich auf eine neue ID, den Stil und die Breite fest.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Index des Indikator Bereichs, dessen Stil festgelegt werden soll.

*nID*<br/>
Neue ID für den Indikator Bereich.

*nStyle*<br/>
Neuer Stil für den Indikator Bereich.

*cxWidth*<br/>
Neue Breite für den Indikator Bereich.

### <a name="remarks"></a>Hinweise

Die folgenden Indikator Stile werden unterstützt:

- SBPS_NOBORDERS kein 3D-Rahmen um den Bereich.

- SBPS_POPOUT umgekehrter Rahmen, sodass der Text "angezeigt wird".

- SBPS_DISABLED keinen Text zeichnen.

- SBPS_STRETCH Stretch Pane zum Auffüllen von nicht verwendetem Speicherplatz. Nur ein Bereich pro Statusleiste kann dieses Format aufweisen.

- SBPS_NORMAL keine Streckung, Rahmen oder Popup.

##  <a name="setpanestyle"></a>CStatusBar:: setpanestyle

Mit dieser Member-Funktion können Sie den Stil für den Bereich einer Statusleiste festlegen.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Stil festgelegt werden soll.

*nStyle*<br/>
Stil des Bereichs, dessen Stil festgelegt werden soll.

### <a name="remarks"></a>Hinweise

Der Stil eines Bereichs bestimmt, wie der Bereich angezeigt wird.

Eine Liste der Stile, die für Status leisten verfügbar sind, finden Sie unter [setpaneingefo](#setpaneinfo).

##  <a name="setpanetext"></a>CStatusBar:: SetPaneText

Diese Member-Funktion wird aufgerufen, um den Bereichs Text auf die Zeichenfolge festzulegen, auf die von *lpsznewtext*verwiesen wird.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Text festgelegt werden soll.

*lpszNewText*<br/>
Zeiger auf den neuen Bereichs Text.

*bUpdate*<br/>
TRUE gibt an, dass der Bereich für ungültig erklärt wird, nachdem der Text festgelegt wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Nachdem Sie aufgerufen `SetPaneText`haben, müssen Sie einen UI-Update Handler hinzufügen, um den neuen Text in der Statusleiste anzuzeigen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl-Klasse](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)
