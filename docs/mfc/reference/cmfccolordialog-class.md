---
title: Cmfccolordialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 9e018c122cded09e5366c3b349525fa7cc004897
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505341"
---
# <a name="cmfccolordialog-class"></a>Cmfccolordialog-Klasse

Die `CMFCColorDialog` -Klasse stellt ein Farbauswahl Dialogfeld dar.

## <a name="syntax"></a>Syntax

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Erstellt ein `CMFCColorDialog`-Objekt.|
|`CMFCColorDialog::~CMFCColorDialog`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorDialog::GetColor](#getcolor)|Gibt die aktuell ausgewählte Farbe zurück.|
|[CMFCColorDialog::GetPalette](#getpalette)|Gibt die Palette der Farbe zurück.|
|`CMFCColorDialog::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. Syntax und weitere Informationen finden Sie unter [CWnd::P retranslatemess Age](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CDialogEx::PreTranslateMessage`.)|
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Leitet eine Palette von der Systempalette ab.|
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Legt die aktuell ausgewählte Farbe fest.|
|[Cmfccolordialog:: setnewcolor](#setnewcolor)|Legt die Farbe fest, die einem angegebenen RGB-Wert am meisten entspricht.|
|[CMFCColorDialog::SetPageOne](#setpageone)|Wählt einen RGB-Wert für die erste Eigenschaften Seite aus.|
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Wählt einen RGB-Wert für die zweite Eigenschaften Seite aus.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|`m_bIsMyPalette`|TRUE, wenn das Dialogfeld für die Farbauswahl eine eigene Farbpalette verwendet, oder false, wenn das Dialogfeld eine im `CMFCColorDialog` Konstruktor angegebene Palette verwendet.|
|`m_bPickerMode`|TRUE, wenn der Benutzer eine Farbe aus dem Auswahl Dialogfeld auswählt. andernfalls false.|
|`m_btnColorSelect`|Die Farb Schaltfläche, die der Benutzer ausgewählt hat.|
|`m_CurrentColor`|Die aktuell ausgewählte Farbe.|
|`m_hcurPicker`|Der Cursor, der verwendet wird, um eine Farbe auszuwählen.|
|`m_NewColor`|Die mögliche ausgewählte Farbe, die dauerhaft ausgewählt oder auf die ursprüngliche Farbe zurückgesetzt werden kann.|
|`m_pColourSheetOne`|Ein Zeiger auf die erste Eigenschaften Seite des Farbauswahl-Eigenschaften Blatts.|
|`m_pColourSheetTwo`|Ein Zeiger auf die zweite Eigenschaften Seite des Farbauswahl-Eigenschaften Blatts.|
|`m_pPalette`|Die aktuelle logische Palette.|
|`m_pPropSheet`|Ein Zeiger auf das Eigenschaften Blatt für das Dialogfeld zur Farbauswahl.|
|`m_wndColors`|Ein Farbauswahl-Steuerelement Objekt.|
|`m_wndStaticPlaceHolder`|Ein statisches Steuerelement, das ein Platzhalter für das Eigenschaften Blatt der Farbauswahl ist.|

## <a name="remarks"></a>Hinweise

Das Dialogfeld Farbauswahl wird als Eigenschaften Blatt mit zwei Seiten angezeigt. Auf der ersten Seite Wählen Sie aus der Systempalette eine Standardfarbe aus. auf der zweiten Seite Wählen Sie eine benutzerdefinierte Farbe aus.

Sie können ein `CMFCColorDialog` -Objekt auf dem Stapel erstellen und dann `DoModal`aufrufen, indem Sie die anfängliche Farbe als Parameter an `CMFCColorDialog` den-Konstruktor übergeben. Im Dialogfeld Farbauswahl werden dann mehrere [cmfccolorpickerctrl-Klassen](../../mfc/reference/cmfccolorpickerctrl-class.md) Objekte erstellt, um jede Farbpalette zu verarbeiten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Farb Dialogfeld mithilfe verschiedener Methoden in `CMFCColorDialog` der-Klasse konfiguriert wird. Das Beispiel zeigt, wie die aktuelle und die neue Farbe des Dialog Felds festgelegt werden und wie die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf den beiden Eigenschaften Seiten des Farb Dialogfelds festgelegt werden. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxcolordialog. h

##  <a name="cmfccolordialog"></a>Cmfccolordialog:: cmfccolordialog

Erstellt ein `CMFCColorDialog`-Objekt.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>Parameter

*clrInit*<br/>
in Die Standard Farbauswahl. Wenn kein Wert angegeben wird, ist der Standardwert RGB (0, 0, 0) (schwarz).

*dwFlags*<br/>
[in] Reserviert.

*pParentWnd*<br/>
in Ein Zeiger auf das übergeordnete oder Besitzer Fenster des Dialog Felds.

*hPal*<br/>
in Ein Handle für eine Farbpalette.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getcolor"></a>Cmfccolordialog:: GetColor

Ruft die Farbe ab, die der Benutzer aus dem Farb Dialogfeld auswählt.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/win32/gdi/colorref) -Wert, der die RGB-Informationen für die im Dialogfeld Farbe ausgewählte Farbe enthält.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, nachdem Sie `DoModal` die-Methode aufgerufen haben.

##  <a name="getpalette"></a>Cmfccolordialog:: getpalette

Ruft die Farbpalette ab, die im aktuellen Farb Dialogfeld verfügbar ist.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `CPalette` Objekt, das `CMFCColorDialog` im Konstruktor angegeben wurde.

### <a name="remarks"></a>Hinweise

Die Farbpalette gibt die Farben an, die der Benutzer auswählen kann.

##  <a name="rebuildpalette"></a>Cmfccolordialog:: rebuildpalette

Leitet eine Palette von der Systempalette ab.

```
void RebuildPalette();
```

##  <a name="setcurrentcolor"></a>Cmfccolordialog:: setcurrentcolor

Legt die aktuelle Farbe des Dialog Felds fest.

```
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>Parameter

*rgb*<br/>
in Ein RGB-Farbwert

### <a name="remarks"></a>Hinweise

##  <a name="setnewcolor"></a>Cmfccolordialog:: setnewcolor

Legt die aktuelle Farbe auf die Farbe in der aktuellen Palette fest, die am ähnlichsten ist.

```
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>Parameter

*rgb*<br/>
in Ein [COLORREF](/windows/win32/gdi/colorref) -Wert, der eine RGB-Farbe angibt.

### <a name="remarks"></a>Hinweise

##  <a name="setpageone"></a>Cmfccolordialog:: setpageone

Gibt die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf der ersten Eigenschaften Seite eines Farb Dialogfelds explizit an.

```
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parameter

*R*<br/>
in Gibt die rote Komponente des RGB-Werts an.

*G*<br/>
in Gibt die grüne Komponente des RGB-Werts an.

*B*<br/>
in Gibt die blaue Komponente des RGB-Werts an.

### <a name="remarks"></a>Hinweise

##  <a name="setpagetwo"></a>Cmfccolordialog:: setpagetwo

Gibt die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf der zweiten Eigenschaften Seite eines Farb Dialogfelds explizit an.

```
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parameter

*R*<br/>
in Gibt eine rote Komponente des RGB-Werts an.

*G*<br/>
in Gibt eine grüne Komponente eines RGB-Werts an.

*B*<br/>
in Gibt eine blaue Komponente eines RGB-Werts an.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md)
