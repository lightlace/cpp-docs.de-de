---
title: CMF cribbonedit-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: 4f973074fbec3d04b1c1a74852b02ff2564217c1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504950"
---
# <a name="cmfcribbonedit-class"></a>CMF cribbonedit-Klasse

Implementiert ein Bearbeitungs Steuerelement, das sich auf einer Menü Band Leiste befindet.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMF cribbonedit:: CMF cribbonedit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMF cribbonedit:: canbegestreckt](#canbestretched)|Gibt an, ob die Höhe `CMFCRibbonEdit` des Steuer Elements vertikal auf die Höhe einer Menüband-Zeile erhöht werden kann.|
|[CMF cribbonedit:: CMF cribbonedit](#cmfcribbonedit)|Erstellt ein `CMFCRibbonEdit`-Objekt.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Kopiert den Zustand des angegebenen `CMFCRibbonEdit` Objekts in das aktuelle `CMFCRibbonEdit` -Objekt.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|Erstellt ein neues Textfeld für das `CMFCRibbonEdit` -Objekt.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Zerstört das `CMFCRibbonEdit`-Objekt.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Löscht ein Listenfeld.|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Aktiviert und legt den Bereich der Drehfeld Schaltfläche für das Textfeld fest.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Ruft die kompakte Größe des `CFMCRibbonEdit` -Objekts ab.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|Ruft den Text im Textfeld ab.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ruft die zwischen Größe des `CMFCRibbonEdit` -Objekts ab.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Ruft die Ausrichtung des Texts im Textfeld ab.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|Ruft die Breite des `CMFCRibbonEdit` -Steuer Elements in Pixel ab.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gibt an, ob die Anzeige Größe `CMFCRibbonEdit` des Steuer Elements kompakt sein kann.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Gibt an, `CMFCRIbbonEdit` ob das Steuerelement den Fokus besitzt.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gibt an, ob die Anzeige Größe `CMFCRibbonEdit` für das-Steuerelement groß sein kann.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Gibt an, ob das Textfeld über eine Dreh Schaltfläche verfügt.|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Gibt an, `CMFCRibbonEdit` ob das Steuerelement hervorgehoben ist.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Wird von Framework aufgerufen, wenn sich die Abmessungen des Anzeige Rechtecks für das `CMFCRibbonEdit` Steuerelement ändern.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement zu zeichnen.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Wird von Framework aufgerufen, um die Bezeichnung und das Bild für `CMFCRibbonEdit` das Steuerelement zu zeichnen.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Wird von Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement in einem Listenfeld Befehle zu zeichnen.|
|[CMFCRibbonEdit::OnEnable](#onenable)|Wird von Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement zu aktivieren oder zu deaktivieren.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Wird von Framework aufgerufen, wenn der Zeiger in die Begrenzungen des `CMFCRibbonEdit` Steuer Elements eintritt oder diese verlässt.|
|[CMFCRibbonEdit::OnKey](#onkey)|Wird von Framework aufgerufen, wenn der Benutzer einen KeyTip drückt und `CMFCRibbonEdit` das Steuerelement den Fokus besitzt.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Wird von Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement zu aktualisieren, wenn der Benutzer mit der linken Maustaste auf das Steuerelement klickt.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Wird von Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Wird von Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement zu aktualisieren, wenn die Richtung des Layouts geändert wird.|
|[CMFCRibbonEdit::OnShow](#onshow)|Wird von Framework aufgerufen, um das `CMFCRibbonEdit` Steuerelement anzuzeigen oder auszublenden.|
|[CMFCRibbonEdit::Redraw](#redraw)|Aktualisiert die Anzeige des `CMFCRibbonEdit` Steuer Elements.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Legt die Barrierefreiheits Daten für `CMFCRibbonEdit` das-Objekt fest.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|Legt den Text im Textfeld fest.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Legt die Textausrichtung des Textfelds fest.|
|[CMFCRibbonEdit::SetWidth](#setwidth)|Legt die Breite des Textfelds für das `CMFCRibbonEdit` -Steuerelement fest.|

## <a name="remarks"></a>Hinweise

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie `CMFCRibbonEdit` ein-Objekt erstellen, Dreh Schaltflächen neben dem Bearbeitungs Steuerelement anzeigen und den Text des Bearbeitungs Steuer Elements festlegen. Dieser Code Ausschnitt ist Teil des Beispiel- [Demo Beispiels von MS Office 2007](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonedit. h

##  <a name="canbestretched"></a>CMF cribbonedit:: canbegestreckt

Gibt an, ob die Höhe des [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuer Elements vertikal auf die Höhe einer Menüband-Zeile erhöht werden kann.

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer false zurück.

### <a name="remarks"></a>Hinweise

##  <a name="cmfcribbonedit"></a>CMF cribbonedit:: CMF cribbonedit

Erstellt ein [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt.

```
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Parameter

*nID*<br/>
in Befehls-ID für `CMFCRibbonEdit` das Steuerelement.

*nWidth*<br/>
in Die Breite des Textfelds für das `CMFCRibbonEdit` -Steuerelement in Pixel.

*lpszLabel*<br/>
in Die Bezeichnung für das `CMFCRibbonEdit` Steuerelement.

*nImage*<br/>
in Der Index des kleinen Bilds, das für `CMFCRibbonEdit` das Steuerelement verwendet werden soll. Die Auflistung von kleinen Bildern wird von der übergeordneten Menü Band Kategorie verwaltet.

### <a name="remarks"></a>Hinweise

Das `CMFCRibbonEdit` -Steuerelement verwendet kein großes Bild.

##  <a name="copyfrom"></a>CMF cribbonedit:: CopyFrom

Kopiert den Zustand des angegebenen [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekts in das aktuelle [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Das Quell `CMFCRibbonEdit` Objekt.

### <a name="remarks"></a>Hinweise

Der *src* -Parameter muss vom Typ `CMFCRibbonEdit`sein.

##  <a name="createedit"></a>CMF cribbonedit:: kreateedit

Erstellt ein neues Textfeld für das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt.

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf das übergeordnete Fenster des `CMFCRibbonEdit` -Objekts.

*dwEditStyle*<br/>
in Gibt den Stil des Textfelds an. Sie können die im Abschnitt "Hinweise" aufgeführten Fenster Stile mit den [Bearbeitungs Steuerelement Stilen](/windows/win32/Controls/edit-control-styles) kombinieren, die in der Windows SDK beschrieben werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neue Textfeld, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Überschreiben diese Methode in einer abgeleiteten Klasse, um ein benutzerdefiniertes Textfeld zu erstellen.

Sie können die folgenden [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf ein Textfeld anwenden:

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>CMF cribbonedit::D estroyctrl

Zerstört das [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt.

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Hinweise

##  <a name="dropdownlist"></a>CMF cribbonedit::D ropdownlist

Löscht ein Listenfeld.

```
virtual void DropDownList();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion aus. Überschreiben Sie diese Methode, um ein Listenfeld zu löschen.

##  <a name="enablespinbuttons"></a>CMF cribbonedit:: enablespinbuttons

Aktiviert und legt den Bereich der Drehfeld Schaltfläche für das Textfeld fest.

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parameter

*nMin*<br/>
in Der minimale Wert der Drehfeld Schaltfläche.

*nMax*<br/>
in Der maximale Wert der Drehfeld Schaltfläche.

### <a name="remarks"></a>Hinweise

Dreh Schaltflächen zeigen einen Pfeil nach oben und nach unten an und ermöglichen es Benutzern, durch einen festgelegten Satz von Werten zu navigieren.

##  <a name="getcompactsize"></a>CMF cribbonedit:: getcompactsize

Ruft die kompakte Größe des [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekts ab.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Objekt.

### <a name="return-value"></a>Rückgabewert

Die kompakte Größe des `CMFCRibbonEdit` -Objekts.

### <a name="remarks"></a>Hinweise

##  <a name="getedittext"></a>CMF cribbonedit:: getedittext

Ruft den Text im Textfeld ab.

```
CString GetEditText() const;
```

### <a name="return-value"></a>Rückgabewert

Der Text im Textfeld.

### <a name="remarks"></a>Hinweise

##  <a name="getintermediatesize"></a>CMF cribbonedit:: getintermediatesize

Ruft die zwischen Größe des [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekts ab.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Objekt.

### <a name="return-value"></a>Rückgabewert

Die zwischen Größe des `CMFCRibbonEdit` -Objekts.

### <a name="remarks"></a>Hinweise

##  <a name="gettextalign"></a>CMF cribbonedit:: gettextalign

Ruft die Ausrichtung des Texts im Textfeld ab.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Enumerationswert für die Textausrichtung. Mögliche Werte finden Sie im Abschnitt "Hinweise".

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert ist einer der folgenden Bearbeitungs Steuerelement Stile:

- **ES_LEFT** für linke Ausrichtung

- **ES_CENTER** for Center-Ausrichtung

- **ES_RIGHT** für Rechte Ausrichtung

Weitere Informationen zu diesen Stilen finden Sie unter [Edit Control Styles](/windows/win32/Controls/edit-control-styles).

##  <a name="getwidth"></a>CMF cribbonedit:: getWidth

Ruft die Breite des [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuer Elements in Pixel ab.

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Parameter

*bInFloatyMode*<br/>
in TRUE, wenn `CMFCRibbonEdit` sich das Steuerelement im Gleit Komma Modus befindet, andernfalls false.

### <a name="return-value"></a>Rückgabewert

Die Breite des `CMFCRibbonEdit` Steuer Elements in Pixel.

### <a name="remarks"></a>Hinweise

##  <a name="hascompactmode"></a>CMF cribbonedit:: hascompactmode

Gibt an, ob die Anzeige Größe des [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuer Elements kompakt sein kann.

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt immer true zurück.

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode immer true zurück. Überschreiben Sie diese Methode, um anzugeben, ob die Anzeige Größe kompakt sein kann.

##  <a name="hasfocus"></a>CMF cribbonedit:: HasFocus

Gibt an, ob das [cmscribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement den Fokus besitzt.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn `CMFCRibbonEdit` das Steuerelement den Fokus besitzt, andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="haslargemode"></a>CMF cribbonedit:: haslargemode

Gibt an, ob die Anzeige Größe für das [cmscribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement groß sein kann.

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt immer false zurück.

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode immer false zurück. Überschreiben Sie diese Methode, um anzugeben, ob die Anzeige Größe sehr groß sein kann.

##  <a name="hasspinbuttons"></a>CMF cribbonedit:: hasspinbuttons

Gibt an, ob das Textfeld über eine Dreh Schaltfläche verfügt.

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Textfeld eine Dreh Schaltfläche aufweist. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="ishighlighted"></a>CMF cribbonedit:: ishervor gehoben

Gibt an, ob das [cmscribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement hervorgehoben ist.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn `CMFCRibbonEdit` das Steuerelement hervorgehoben wird, andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="onafterchangerect"></a>CMF cribbonedit:: onafterchangerect

Wird von Framework aufgerufen, wenn sich die Abmessungen des Anzeige Rechtecks für das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement ändern.

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Steuerelement.

### <a name="remarks"></a>Hinweise

##  <a name="ondraw"></a>CMF cribbonedit:: OnDraw

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement zu zeichnen.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Steuerelement.

### <a name="remarks"></a>Hinweise

##  <a name="ondrawlabelandimage"></a>CMF cribbonedit:: ondrawlabelandimage

Wird von Framework aufgerufen, um die Bezeichnung und das Bild für das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement zu zeichnen.

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Steuerelement.

### <a name="remarks"></a>Hinweise

##  <a name="ondrawonlist"></a>CMF cribbonedit:: ondrawonlist

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement in einem Befehle-Listenfeld zu zeichnen.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeiger auf einen Gerätekontext für das `CMFCRibbonEdit` -Steuerelement.

*strText*<br/>
[in] Der Anzeigetext der [](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit-Klasse").

*nTextOffset*<br/>
in Abstand (in Pixel) von der linken Seite des Listen Felds bis zum Anzeige Text.

*Rect*<br/>
in Das Anzeige Rechteck für das `CMFCRibbonEdit` -Steuerelement.

*bIsSelected*<br/>
in Dieser Parameter wird nicht verwendet.

*bHighlighted*<br/>
in Dieser Parameter wird nicht verwendet.

### <a name="remarks"></a>Hinweise

Im Listenfeld Befehle werden Menü Band Steuerelemente angezeigt, mit denen Benutzer die Symbolleiste für den schnell Zugriff anpassen können.

##  <a name="onenable"></a>CMF cribbonedit:: onenable

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement zu aktivieren oder zu deaktivieren.

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in TRUE, wenn das Steuerelement aktiviert werden soll. FALSE, um das Steuerelement zu deaktivieren.

### <a name="remarks"></a>Hinweise

##  <a name="onhighlight"></a>CMF cribbonedit:: onhighlight

Wird von Framework aufgerufen, wenn der Zeiger in die Grenzen des [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuer Elements eintritt oder diese verlässt.

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Parameter

*bHighlight*<br/>
in TRUE, wenn sich der Zeiger innerhalb der Begrenzungen des `CMFCRibbonEdit` Steuer Elements befindet, andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="onkey"></a>CMF cribbonedit:: OnKey

Wird von Framework aufgerufen, wenn der Benutzer einen KeyTip drückt und das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement den Fokus besitzt.

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Parameter

*bIsMenuKey*<br/>
in TRUE, wenn der KeyTip ein Popup Menü anzeigt. andernfalls false.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Ereignis behandelt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="onlbuttondown"></a>CMF cribbonedit:: OnLButtonDown

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement zu aktualisieren, wenn der Benutzer mit der linken Maustaste auf das Steuerelement klickt.

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parameter

*point*<br/>
in Dieser Parameter wird nicht verwendet.

### <a name="remarks"></a>Hinweise

##  <a name="onlbuttonup"></a>CMF cribbonedit:: onlbuttonup

Wird von Framework aufgerufen, wenn der Benutzer die linke Maustaste loslässt.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parameter

*point*<br/>
in Dieser Parameter wird nicht verwendet.

### <a name="remarks"></a>Hinweise

##  <a name="onrtlchanged"></a>CMF cribbonedit:: onrtlchanged

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement zu aktualisieren, wenn die Richtung des Layouts geändert wird.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parameter

*bIsRTL*<br/>
in TRUE, wenn das Layout von rechts nach links ist. FALSE, wenn das Layout von links nach rechts ist.

### <a name="remarks"></a>Hinweise

##  <a name="onshow"></a>CMF cribbonedit:: onShow

Wird von Framework aufgerufen, um das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement anzuzeigen oder auszublenden.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
in TRUE, wenn das Steuerelement angezeigt werden soll. FALSE, um das Steuerelement auszublenden.

### <a name="remarks"></a>Hinweise

##  <a name="redraw"></a>CMF cribbonedit:: Redraw

Aktualisiert die Anzeige des [cmscribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuer Elements.

```
virtual void Redraw();
```

### <a name="remarks"></a>Hinweise

Diese Methode zeichnet das Anzeige Rechteck für das `CMFCRibbonEdit` -Objekt neu, indem indirekt [CWnd:: redrawwindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) mit den festgelegten Flags RDW_INVALIDATE, RDW_ERASE und RDW_UPDATENOW aufgerufen wird.

##  <a name="setaccdata"></a>CMF cribbonedit:: setaccdata

Legt die Barrierefreiheits Daten für das [CMF cribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Objekt fest.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
Zeiger auf das übergeordnete Fenster für `CMFCRibbonEdit` das-Objekt.

*data*<br/>
Die Barrierefreiheits Daten für `CMFCRibbonEdit` das-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt immer true zurück.

### <a name="remarks"></a>Hinweise

##  <a name="setedittext"></a>CMF cribbonedit:: Einstellungs Text

Legt den Text im Textfeld fest.

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>Parameter

*strText*<br/>
in Der Text für das Textfeld.

##  <a name="settextalign"></a>CMF cribbonedit:: setTextAlign

Legt die Textausrichtung des Textfelds fest.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parameter

*nAlign*<br/>
in Ein Enumerationswert für die Textausrichtung. Mögliche Werte finden Sie im Abschnitt "Hinweise".

### <a name="remarks"></a>Hinweise

Der Parameter *nalign* ist einer der folgenden Bearbeitungs Steuerelement Stile:

- ES_LEFT für linke Ausrichtung

- ES_CENTER for Center-Ausrichtung

- ES_RIGHT für Rechte Ausrichtung

Weitere Informationen zu diesen Stilen finden Sie unter [Edit Control Styles](/windows/win32/Controls/edit-control-styles).

##  <a name="setwidth"></a>CMF cribbonedit:: festgelegt

Legt die Breite des Textfelds für das [cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md) -Steuerelement fest.

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
in Die Breite des Textfelds in Pixel.

*bInFloatyMode*<br/>
TRUE, um die Breite für den Gleit Komma Modus festzulegen. FALSE, um die Breite für den regulären Modus festzulegen.

### <a name="remarks"></a>Hinweise

Das `CMFCRibbonEdit` -Steuerelement hat abhängig vom Anzeigemodus zwei Breiten: der Gleit Komma Modus und der reguläre Modus.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
