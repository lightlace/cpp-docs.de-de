---
title: CMFCStatusBar-Klasse
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: c4891c6bb66fe5e4b737ca9b128a01bcedcf39e7
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176574"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar-Klasse

Die `CMFCStatusBar` -Klasse implementiert eine Statusleiste ähnelt der `CStatusBar` Klasse. Die `CMFCStatusBar` -Klasse verfügt jedoch über Funktionen, die von der `CStatusBar` -Klasse nicht bereitgestellt werden. Beispielsweise kann die Klasse Bilder, Animationen und Statusanzeigen anzeigen und auf einen Mausdoppelklick reagieren.

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||
|[CMFCStatusBar::Create](#create)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann. (Überschreibt [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Aktiviert oder deaktiviert, die der Umgang mit der Maus auf der Statusleiste doppelklickt.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Zeigt eine Statusanzeige im angegebenen Bereich.|
|[CMFCStatusBar::GetCount](#getcount)|Gibt die Anzahl der Bereiche auf der Statusleiste zurück.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Gibt den Bereichsformat zurück. (Überschreibt [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Gibt die Breite in Pixel im angegebenen Bereich der Statusleiste zurück.|
|[CMFCStatusBar::GetTipText](#gettiptext)|Gibt den QuickInfo-Text für den angegebenen Bereich der Statusleiste zurück.|
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|Erklärt den angegebenen Bereich und zeichnet den Inhalt.|
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Wird aufgerufen, durch das Framework vor dem Erstellen des Fensters Windows angefügte `CWnd` Objekt. (Überschreibt [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::SetIndicators](#setindicators)||
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Weist eine Animation im angegebenen Bereich.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Legt die Hintergrundfarbe für den angegebenen Bereich der Statusleiste fest.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Legt das Indikatorsymbol für den angegebenen Bereich der Statusleiste fest.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Legt den aktuellen Fortschritt der Statusanzeige für den angegebenen Bereich der Statusleiste fest.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Legt den Stil des Bereichs. (Überschreibt [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Legt die Textfarbe für den angegebenen Bereich der Statusleiste fest.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Legt die Breite in Pixel im angegebenen Bereich der Statusleiste fest.|
|[CMFCStatusBar::SetTipText](#settiptext)|Legt den QuickInfo-Text für den angegebenen Bereich der Statusleiste fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Vom Framework aufgerufen, wenn sie im Bereich der Statusleiste zeichnet.|

## <a name="remarks"></a>Hinweise

Das folgende Diagramm zeigt eine Abbildung der Statusleiste von [Status Leiste Demobeispiel](../../visual-cpp-samples.md) Anwendung.

![Beispiel für CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "Beispiel für CMFCStatusBar")

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die lokalen Variablen, die die Anwendung verwendet, um die verschiedenen Methoden rufen Sie in der `CMFCStatusBar` Klasse. Diese Variablen werden in StatusBarDemoView.h deklariert. Der Hauptframe in "MainFrm.h" deklariert ist, das Dokument in StatusBarDemoDoc.h deklariert wird und die Ansicht in StatusBarDemoView.h deklariert ist. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Abrufen eines Verweises auf `CMFCStatusBar` Objekt durch die Einführung der `GetStatusBar` -Methode in der "MainFrm.h", und klicken Sie dann das Aufrufen dieser Methode aus der `GetStatusBar` -Methode in der StatusBarDemoView.h. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie verschiedene Methoden aufrufen, der `CMFCStatusBar` Klasse in StatusBarDemoView.cpp. Die Konstanten sind in "MainFrm.h" deklariert. Das Beispiel zeigt, wie Sie auf das Symbol, legen Sie den QuickInfo-Text, der dem Statusleistenbereich, eine Statusanzeige im angegebenen Bereich anzuzeigen, weisen Sie eine Animation in den angegebenen Bereich, legen Sie den Text und die Breite der dem Statusleistenbereich und legen Sie die Bearbeitung die aktuellen Statusanzeige für den Statusleistenbereich ESS-Leiste. Dieser Codeausschnitt ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxstatusbar.h

##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Parameter

[in] *nIDFind*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="create"></a>  CMFCStatusBar::Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

[in] *pParentWnd*<br/>
[in] *DwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="createex"></a>  CMFCStatusBar::CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Parameter

[in] *pParentWnd*<br/>
[in] *DwCtrlStyle*<br/>
[in] *DwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick

Aktiviert oder deaktiviert, die der Umgang mit der Maus auf der Statusleiste doppelklickt.

```
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] True gibt an, aktivieren Sie die Verarbeitung der Doppelklick mit der Maus. Andernfalls deaktivieren Sie die Verarbeitung der Doppelklick mit der Maus.

### <a name="remarks"></a>Hinweise

Wenn die Statusleiste Doppelklicks verarbeiten aktiviert ist, sendet Windows die WM_COMMAND-Benachrichtigung zusammen mit einer Ressourcen-ID an den Besitzer der Statusleiste an jedes Mal, die der Benutzer auf den Statusleistenbereich doppelklickt.

##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar

Zeigt eine Statusanzeige im angegebenen Bereich.

```
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt dem Index des Bereichs, dessen Statusanzeige zu aktivieren.

*nGesamte*<br/>
[in] Gibt den maximalen Wert für die Statusanzeige an.

*bDisplayText*<br/>
[in] Gibt an, ob den aktuelle Fortschrittswert die Statusanzeige angezeigt werden soll.

*clrBar*<br/>
[in] Gibt die Hintergrundfarbe der Statusleiste an.

*clrBarDest*<br/>
[in] Gibt die sekundäre Farbe des Befehlsleisten-Hintergrund den Fortschritt an. Verwenden Sie die anderen Wert als *ClrBar* zum Ausfüllen von einer Farbe in einem Farbverlauf gemischt.

*clrProgressText*<br/>
[in] Gibt die Farbe des Texts der Statusanzeige.

### <a name="remarks"></a>Hinweise

Wenn Sie den Fortschritt Leiste Aufruf deaktivieren möchten `EnablePaneProgressBar` mit *nGesamte* auf-1 festgelegt. Standardmäßig *nGesamte* auf 100 festgelegt ist. Aus diesem Grund benötigen Sie keine weiteren Berechnungen durch, um den Status als Prozentsatz angezeigt werden soll.

Übergeben Sie unterschiedliche Werte für *ClrBar* und *ClrBarDest* , damit die Hintergrundfarbe der Statusleiste eine Farbe, die in einem Farbverlauf gemischt angezeigt. sein.

Rufen Sie zum Festlegen des aktuellen Status der [CMFCStatusBar::SetPaneProgress](#setpaneprogress) Methode.

##  <a name="getcount"></a>  CMFCStatusBar::GetCount

Ruft die Anzahl der Bereiche in der Statusleiste ab.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bereiche in der Statusleiste angezeigt.

##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Parameter

[in] *Rect*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *LpRect*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *CxWidth*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText

```
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *s*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth

Ruft die Breite des Bereichs einer Statusleiste ab.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index, der dem Statusleistenbereich.

### <a name="return-value"></a>Rückgabewert

Die Breite der dem Statusleistenbereich, *nIndex* gibt; andernfalls NULL, wenn eine Statusleiste nicht vorhanden ist.

##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText

Rufen Sie den QuickInfo-Text der Statusleiste im Bereich "".

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs für das QuickInfo-Text abzurufen.

### <a name="return-value"></a>Rückgabewert

Der QuickInfo-Text im Bereich mit der Statusleiste, *nIndex* angibt. Andernfalls der leeren Zeichenfolge, wenn Sie ein Statusleistenbereich nicht vorhanden ist, für den angegebenen *nIndex* oder wenn die QuickInfo-Text leer ist.

##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent

Für ungültig erklären Sie die Statusleistenbereich und zeichnen Sie seinen Inhalt neu zu.

```
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs, dessen Inhalt neu gezeichnet und werden für ungültig erklärt wird.

### <a name="remarks"></a>Hinweise

Wenn die Statusleiste ungültig ist, wird er für das Neuzeichnen markiert. Windows zeichnet es neu, wenn die `UpdateWindow` Methode sendet eine WM_PAINT-Nachricht an die `OnPaint` Methode.

##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane

Neu gezeichnet werden im Bereich der Statusleiste.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext zum Zeichnen.

*pPane*<br/>
[in] Ein Zeiger auf eine `CMFCStatusBarPaneInfo` -Struktur, die die Informationen über den Bereich zu zeichnenden enthält.

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `OnDrawPane` zeichnet im Bereich mit den Gerätekontext *pDC* gemäß der Formatvorlage und den Inhalt des Bereichs.

Überschreiben Sie diese Methode in einer `CMFCStatusBar`-abgeleitete Klasse, um die Darstellung eines Bereichs anzupassen.

##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parameter

[in] *Cs*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea

```
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parameter

[in] *bSet*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Parameter

[in] *LpIDArray*<br/>
[in] *nIDCount*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation

Weist eine Animation im angegebenen Bereich.

```
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs, der Sie eine Animation zuweisen möchten.

*hImageList*<br/>
[in] Gibt ein Handle der Bildliste an, die die Frame-Animationen enthält.

*nFrameRate*<br/>
[in] Gibt die Framerate für die Animation in Millisekunden an.

*bUpdate*<br/>
[in] True gibt an, aktualisieren Sie den im Bereich Inhalt sofort. Andernfalls wird der Inhalt im Bereich aktualisiert, wenn sie ungültig wird.

### <a name="remarks"></a>Hinweise

Wenn Sie die aktuelle Animation deaktivieren möchten, rufen Sie `SetPaneAnimation` mit `hImageList` auf NULL festgelegt.

##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor

Legt die Hintergrundfarbe der dem Statusleistenbereich fest.

```
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs für die eine neue Hintergrundfarbe festzulegen.

*clrBackground*<br/>
[in] Die neue Hintergrundfarbe angibt.

*bUpdate*<br/>
[in] True gibt an, aktualisieren Sie den im Bereich Inhalt sofort. Andernfalls werden erst aktualisiert, den im Bereich Inhalt im Bereich von einer anderen Methode ungültig ist.

##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon

Legen Sie das Symbol für den Statusleistenbereich.

```
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs für die das Bild festgelegt.

*hIcon*<br/>
[in] Gibt ein Handle auf das Symbol wie das Bild im Bereich festgelegt werden.

*bUpdate*<br/>
[in] Gibt an, ob den Bereich Inhalt sofort zu aktualisieren.

*hBmp*<br/>
[in] Gibt ein Handle auf die Bitmap als Bild Bereich festgelegt werden.

*clrTransparent*<br/>
[in] Gibt die transparente Farbe der Bitmap, die die *hBmp* angibt.

### <a name="remarks"></a>Hinweise

Sie können entweder HICON oder HBITMAP sowie die transparente Farbe des Bereichs Image festlegen übergeben. Wenn Sie nicht, um das Bild nicht mehr anzuzeigen möchten, übergeben Sie den NULL-Wert als Bild-Handle.

Es ist Animation ausgeführte, die [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) hat festgelegt, wird die Animation beendet werden.

##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *CxWidth*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress

Legen Sie die aktuelle Statusanzeige der Statusanzeige für den angegebenen Bereich.

```
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs für den die Statusanzeige zu aktualisieren.

*nCurr*<br/>
[in] Gibt den aktuellen Wert der Statusanzeige an.

*bUpdate*<br/>
[in] Gibt an, ob der Bereich sofort aktualisiert werden sollen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode auf, wenn die Statusanzeige für die Statusanzeige im angegebenen Bereich aktualisiert werden soll.

Um diese Funktion für den angegebenen Bereich zu verwenden, rufen Sie [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) erste.

##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *nStyle*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Parameter

[in] *nIndex*<br/>
[in] *LpszNewText*<br/>
[in] *bUpdate*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor

Legt die Textfarbe im angegebenen Bereich fest.

```
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Gibt den Index des Bereichs, der Sie eine neue Farbe zuweisen möchten.

*clrText*<br/>
[in] Gibt die Farbe des Textes an.

*bUpdate*<br/>
[in] True gibt an, aktualisieren Sie den im Bereich Inhalt sofort. Andernfalls werden erst aktualisiert, den im Bereich Inhalt im Bereich von einer anderen Methode ungültig ist.

##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth

Festlegen Sie die Breite der dem Statusleistenbereich.

```
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Der Index, der dem Statusleistenbereich für die neue Breite festgelegt werden soll.

*CX*<br/>
[in] Die neue Breite der dem Statusleistenbereich in Pixel.

##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText

Legen Sie den QuickInfo-Text, der einen Statusleistenbereich.

```
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
[in] Der Index des Bereichs, der den QuickInfo-Text zugewiesen werden sollen.

*pszTipText*<br/>
[in] Der neue QuickInfo-Text.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)
