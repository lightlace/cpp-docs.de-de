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
ms.openlocfilehash: d714159aa9fd52df682b1e5f3dbf3957bbef1b91
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777336"
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
|[CStatusBar::CommandToIndex](#commandtoindex)|Ruft Index für einen bestimmten Indikator-ID.|
|[CStatusBar::Create](#create)|Erstellt der Statusleiste angezeigt wird, fügt es der `CStatusBar` Objekt und legt die anfängliche Höhe der Schriftart und Balken.|
|[CStatusBar::CreateEx](#createex)|Erstellt eine `CStatusBar` Objekt mit zusätzlichen Stilen für den eingebetteten `CStatusBarCtrl` Objekt.|
|[CStatusBar::DrawItem](#drawitem)|Wird aufgerufen, wenn ein visueller Aspekt der ein ownerdrawn-Statusleisten-Steuerelements ändert.|
|[CStatusBar::GetItemID](#getitemid)|Ruft den Indikator-ID für einen bestimmten Index ab.|
|[CStatusBar::GetItemRect](#getitemrect)|Ruft anzeigen Rechteck für einen bestimmten Index.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Ruft Indicator-ID, Stil und die Breite für einen bestimmten Index ab.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Ruft die indikatorart für einen bestimmten Index ab.|
|[CStatusBar::GetPaneText](#getpanetext)|Ruft den Text fest, der für einen bestimmten Index ab.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.|
|[CStatusBar::SetIndicators](#setindicators)|Legt fest, Indicator-IDs.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Indikator-ID, Stil und Breite für einen bestimmten Index festgelegt.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Legt die indikatorart für einen bestimmten Index fest.|
|[CStatusBar::SetPaneText](#setpanetext)|Legt Text fest, der für einen bestimmten Index fest.|

## <a name="remarks"></a>Hinweise

Die Ausgabebereiche werden häufig als Nachricht Zeilen und Statusindikatoren verwendet. Beispiele sind im Menü hilfemeldung Zeilen, die der ausgewählten Menübefehls kurz erläutert wird und die Indikatoren, die den Status des Rollen-Taste, NUM- und andere Product Keys anzuzeigen.

[GetStatusBarCtrl](#getstatusbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für die Statusleiste anpassen und zusätzliche Funktionen nutzen. `CStatusBar` Member-Funktionen bieten Ihnen die meisten Funktionen der allgemeinen Windows-Steuerelemente; Wenn Sie jedoch aufrufen, `GetStatusBarCtrl`, Sie können den Statusleisten erteilen, sogar noch mehr Merkmale der Statusleiste Windows 95/98. Beim Aufruf `GetStatusBarCtrl`, es gibt einen Verweis auf eine `CStatusBarCtrl` Objekt. Finden Sie unter [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) für Weitere Informationen zum Verwenden von Windows-Standardsteuerelementen Symbolleisten entwerfen. Weitere allgemeine Informationen über allgemeine Steuerelemente, finden Sie unter [Standardsteuerelementen](/windows/desktop/Controls/common-controls-intro) im Windows SDK.

Das Framework speichert Informationen Indicator in ein Array mit den am weitesten links stehende Indikator an Position 0. Wenn Sie eine Statusleiste erstellen, verwenden Sie ein Array von Zeichenfolgen-IDs, die das Framework die entsprechenden Indikatoren zuordnet. Klicken Sie dann können entweder eine Zeichenfolgen-ID oder einen Index auf einen Indikator.

Standardmäßig ist der erste Indikator "elastic": Es nimmt die Statusleiste-Länge, die nicht von den anderen Indikator Bereichen verwendet, damit die anderen Bereiche sind rechtsbündig ausgerichtet.

Um eine Statusleiste zu erstellen, gehen Sie folgendermaßen vor:

1. Erstellen der `CStatusBar` Objekt.

1. Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex))-Funktion zum Erstellen Sie das Fenster mit der Statusleiste, und fügen Sie ihn auf die `CStatusBar` Objekt.

1. Rufen Sie [SetIndicators](#setindicators) , jedes Indikators eine Zeichenfolgen-ID zugeordnet werden soll.

Es gibt drei Möglichkeiten, um den Text in einem Bereich mit der Statusleiste zu aktualisieren:

1. Rufen Sie [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) auf den Text im Bereich 0 nur zu aktualisieren.

1. Rufen Sie [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) in der Statusleiste ON_UPDATE_COMMAND_UI-Ereignishandler.

1. Rufen Sie [SetPaneText aufgerufen wird](#setpanetext) um den Text für einen beliebigen Bereich zu aktualisieren.

Rufen Sie [SetPaneStyle](#setpanestyle) den Stil eines Bereichs mit der Statusleiste zu aktualisieren.

Weitere Informationen zur Verwendung von `CStatusBar`, finden Sie im Artikel [Status Befehlsleisten-Standardimplementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex

Ruft den Index der Indikator für eine bestimmte-ID.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parameter

*nIDFind*<br/>
Zeichenfolgen Sie-ID des Indikators, dessen Index ist, abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Der Index des Indikators, wenn erfolgreich; -1, wenn nicht erfolgreich.

### <a name="remarks"></a>Hinweise

Der Index des ersten Indikators ist 0.

##  <a name="create"></a>  CStatusBar::Create

Erstellt eine Statusleiste (ein untergeordnetes Fenster) und ordnet ihn dem `CStatusBar` Objekt.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.

*dwStyle*<br/>
Der Stil mit der Statusleiste. Zusätzlich zu den standardmäßigen Windows [Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles), diese Formate werden unterstützt.

- CBRS_TOP Steuerleiste ist am Anfang Rahmenfenster.

- CBRS_BOTTOM Steuerleiste ist am unteren Rand eines Rahmenfensters.

- CBRS_NOALIGN Steuerleiste ist nicht neu angeordnet, wenn das übergeordnete Element geändert wird.

*nID*<br/>
Der Symbolleiste auf die untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Außerdem wird die erste Schriftart und legt den Status der Höhe des Balkens einen Standardwert.

##  <a name="createex"></a>  CStatusBar:: CreateEx

Mit dieser Funktion wird zum Erstellen einer Statusleiste (ein untergeordnetes Fenster), und ordnen sie die `CStatusBar` Objekt.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.

*dwCtrlStyle*<br/>
Weitere Formate für die Erstellung der eingebetteten [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Objekt. Der Standardwert gibt an, eine Statusleiste, ohne ein Ziehpunkt zur Größenänderung oder eine QuickInfo zu unterstützen. Status werden-Leiste unterstützt:

- SBARS_SIZEGRIP das StatusBar-Steuerelement enthält einen Größenziehpunkt am rechten Ende der Statusleiste angezeigt. Ein Größenziehpunkt ist vergleichbar mit einem Rahmen; Es ist eines rechteckigen Bereichs, das der Benutzer kann klicken und ziehen Sie zum Ändern der Größe des übergeordneten Fensters.

- SBT_TOOLTIPS die Statusleiste unterstützt QuickInfos.

Weitere Informationen zu diesen Formaten finden Sie unter [Einstellungen für CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).

*dwStyle*<br/>
Statusleistenstil. Der Standardwert gibt an, dass eine sichtbare Statusleiste am unteren Rand des Rahmenfensters erstellt werden. Wenden Sie eine beliebige Kombination der Stile von Listensteuerelementen aufgeführt, die der Statusleiste [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Allerdings sollten diesen Parameter immer die Stile WS_CHILD und WS_VISIBLE enthalten.

*nID*<br/>
ID des untergeordneten Fensters mit der Statusleiste

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Diese Funktion auch wird die erste Schriftart und legt den Status der Höhe des Balkens einen Standardwert.

Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formate während der Erstellung der eingebetteten Statusleisten-Steuerelement vorhanden sein müssen. Legen Sie z. B. *DwCtrlStyle* zu SBT_TOOLTIPS zum Anzeigen von QuickInfos in einem Status Leiste-Objekt.

##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar

Erstellt eine `CStatusBar` Objekt, eine Statusleiste Standardschriftart bei Bedarf erstellt und die Eigenschaften der Schriftart auf Standardwerte festgelegt.

```
CStatusBar();
```

##  <a name="drawitem"></a>  CStatusBar::DrawItem

Diese Memberfunktion wird durch das Framework, wenn ein ownerdrawn-Statusleiste ändert sich ein Darstellungsaspekt aufgerufen.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) -Struktur, Informationen über den Typ der Zeichnung, die erforderlich sind enthält.

### <a name="remarks"></a>Hinweise

Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CStatusBar` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext in angegeben wiederherstellen *LpDrawItemStruct* vor der Beendigung von dieser Memberfunktion.

##  <a name="getitemid"></a>  CStatusBar::GetItemID

Gibt die ID des Indikators gemäß *nIndex*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Indikators, deren ID wird abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Die ID des Indikators gemäß *nIndex*.

##  <a name="getitemrect"></a>  CStatusBar::GetItemRect

Kopiert die Koordinaten des Indikators gemäß *nIndex* in die Struktur verweist *LpRect*.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Indikators, dessen Rechteckkoordinaten sind, abgerufen werden sollen.

*lpRect*<br/>
Verweist auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Indikators gemäß erhält *nIndex*.

### <a name="remarks"></a>Hinweise

Koordinaten werden in Pixel relativ to zum der oberen linken Ecke der Statusleiste.

##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo

Legt *nID*, *nStyle*, und *CxWidth* bis zum-ID, den Stil und die Breite des Indikatorbereichs an die vom angegebenen Speicherort *nIndex*.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Informationen sind, abgerufen werden sollen.

*nID*<br/>
Verweis auf eine "uint", die auf die ID des Bereichs festgelegt wird.

*nStyle*<br/>
Verweis auf eine "uint", die den Stil des Bereichs festgelegt wird.

*cxWidth*<br/>
Verweis auf eine ganze Zahl, die auf die Breite des Bereichs festgelegt wird.

##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle

Rufen Sie diese Memberfunktion um den Stil einer Statusleiste Bereich abzurufen.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Stil ist, abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Das Format des Bereichs mit der Statusleiste von angegeben *nIndex*.

### <a name="remarks"></a>Hinweise

Ein Bereich des Stil wird bestimmt, wie der Bereich wird angezeigt.

Eine Liste der verfügbaren zeigerformate von Statusleisten, finden Sie unter [erstellen](#create).

##  <a name="getpanetext"></a>  CStatusBar::GetPaneText

Rufen Sie diese Memberfunktion zum Abrufen des Texts, der in einem Bereich mit der Statusleiste angezeigt wird.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Text befindet, abgerufen werden sollen.

*rString*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Text abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein `CString` Objekt, das im Bereich Text enthält.

### <a name="remarks"></a>Hinweise

Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit der Text der Zeichenfolge.

##  <a name="getstatusbarctrl"></a>  GetStatusBarCtrl

Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Enthält einen Verweis auf eine [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Verwendung `GetStatusBarCtrl` nutzen die Funktionalität des allgemeinen Windows-Taskleiste-Steuerelements, und die Unterstützung nutzen [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) bietet bei der Anpassung der Statusleiste. Z. B. mit dem allgemeinen Steuerelement, können Sie angeben, ein Format, das einen Größenziehpunkt in der Statusleiste enthält, oder Sie können angeben, dass ein Format für die Statusleiste am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt werden.

Weitere allgemeine Informationen über allgemeine Steuerelemente, finden Sie unter [Standardsteuerelementen](/windows/desktop/Controls/common-controls-intro) im Windows SDK.

##  <a name="setindicators"></a>  CStatusBar:: SetIndicators

Wird jedes Indikators-ID auf den Wert, der durch das entsprechende Element des Arrays angegeben *LpIDArray*, lädt die durch jede ID angegebene Zeichenfolgenressource und setzt Sie auf die Zeichenfolge des Indikators Text.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parameter

*lpIDArray*<br/>
Zeiger auf ein Array von IDs.

*nIDCount*<br/>
Anzahl der Elemente im Array zeigt *LpIDArray*.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo

Legt den angegebenen Indikatorbereichs auf eine neue ID, Stil und die Breite fest.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Indikatorbereichs, dessen Stil ist, festgelegt werden.

*nID*<br/>
Neue ID für den Bereich des Indikators.

*nStyle*<br/>
Neue Formatvorlage für den Bereich des Indikators.

*cxWidth*<br/>
Die neue Breite für den Bereich des Indikators.

### <a name="remarks"></a>Hinweise

Die folgenden Stile für den Indikator werden unterstützt:

- SBPS_NOBORDERS Nr. 3-d Rahmens im Bereich.

- SBPS_POPOUT Reverse Rahmen, sodass Text "eingeblendet."

- Zeichnen von Text SBPS_DISABLED führen nicht.

- Zum Ausfüllen von nicht belegtem Speicherplatzes SBPS_STRETCH Stretch-Bereich. Nur ein Bereich pro Statusleiste kann dieses Format haben.

- SBPS_NORMAL keine Stretch "," Rahmen "oder" Pop-Out ".

##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle

Rufen Sie diese Memberfunktion um den Stil einer Statusleiste Bereich festzulegen.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Stil ist, festgelegt werden.

*nStyle*<br/>
Die Art des Bereichs, dessen Stil ist, festgelegt werden.

### <a name="remarks"></a>Hinweise

Ein Bereich des Stil wird bestimmt, wie der Bereich wird angezeigt.

Eine Liste der verfügbaren zeigerformate von Statusleisten, finden Sie unter [SetPaneInfo](#setpaneinfo).

##  <a name="setpanetext"></a>  CStatusBar::SetPaneText

Rufen Sie diese Memberfunktion zum Festlegen des Texts im Bereich der Zeichenfolge verweist *LpszNewText*.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Bereichs, dessen Text befindet, festgelegt werden.

*lpszNewText*<br/>
Zeiger auf den neuen Bereich Text.

*bUpdate*<br/>
Bei "true", wird im Bereich ungültig gemacht werden, nachdem der Text festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Nach dem Aufruf von `SetPaneText`, müssen Sie einen UI-Update-Handler zum Anzeigen von des neuen Texts in der Statusleiste hinzufügen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Muster CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC-Beispiel DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl-Klasse](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)
