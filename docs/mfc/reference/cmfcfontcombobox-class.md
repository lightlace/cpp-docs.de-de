---
title: CMFCFontComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: 6d0b2fc22d1d0779db17e970118694270a206439
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272671"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox-Klasse

Die `CMFCFontComboBox` Klasse erstellt ein Kombinationsfeld-Steuerelement, das eine Liste von Schriftarten enthält.

## <a name="syntax"></a>Syntax

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Erstellt ein `CMFCFontComboBox`-Objekt.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Wird aufgerufen, durch das Framework, um die relative Position eines neuen Elements in das Feld sortierte Liste der aktuellen Schriftart Kombinationsfeld-Steuerelements zu bestimmen. (Überschreibt [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Wird aufgerufen, durch das Framework um ein angegebenes Element in der aktuellen Schriftart Kombinationsfeld-Steuerelement zu zeichnen. (Überschreibt [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Ruft Informationen zu den aktuell ausgewählten Schriftart ab.|
|`CMFCFontComboBox::MeasureItem`|Wird aufgerufen, durch das Framework, Windows, der die Dimensionen des ListBox-Felds in der aktuellen Schriftart Kombinationsfeld-Steuerelement zu informieren. (Überschreibt [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Wählt die Schriftart, die den angegebenen Kriterien aus der Schriftarten-Kombinationsfeld entspricht.|
|[CMFCFontComboBox::Setup](#setup)|Initialisiert die Liste der Elemente in der Schriftarten-Kombinationsfeld.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Gibt an, das Framework welche Schriftart zu verwenden, um die Bezeichnungsfelder der Elemente in der aktuellen Schriftarten-Kombinationsfeld zu zeichnen.|

## <a name="remarks"></a>Hinweise

Verwenden einer `CMFCFontComboBox` Objekt in einem Dialogfeld, fügen Sie eine `CMFCFontComboBox` -Variable auf die Dialogfeldklasse. Klicken Sie dann in der `OnInitDialog` -Methode der Dialogfeldklasse Aufruf der [CMFCFontComboBox::Setup](#setup) Methode, um die Liste der Elemente in das Kombinationsfeld-Steuerelement zu initialisieren.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxfontcombobox.h

##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox

Erstellt ein `CMFCFontComboBox`-Objekt.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

Ruft Informationen zu den aktuell ausgewählten Schriftart ab.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md) Objekt, das eine Schriftart beschreibt. Es kann NULL sein, wenn keine Schriftart im Kombinationsfeld ausgewählt ist.

### <a name="remarks"></a>Hinweise

##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont

Gibt an, das Framework welche Schriftart zu verwenden, um die Bezeichnungsfelder der Elemente in der aktuellen Schriftarten-Kombinationsfeld zu zeichnen.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Hinweise

Stellen Sie dieses Element auf "true", um das Framework dieselbe Schriftart verwendet wird, um jede elementbezeichnung zeichnen weiterzuleiten. Stellen Sie dieses Element auf "false", leiten Sie das Framework um jede elementbezeichnung in der Schriftart zu zeichnen, deren Name die Bezeichnung identisch ist. Der Standardwert des Elements ist "false".

##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont

Wählt die Schriftart, die den angegebenen Kriterien aus der Schriftarten-Kombinationsfeld entspricht.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Parameter

*pDesc*<br/>
[in] Verweist auf ein Schriftartobjekt-Beschreibung.

*Wert*<br/>
[in] Gibt den Namen einer Schriftart an.

*nCharSet*<br/>
[in] Gibt einen Zeichensatz. Der Standardwert ist DEFAULT_CHARSET. Weitere Informationen finden Sie unter den `lfCharSet` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur.

### <a name="return-value"></a>Rückgabewert

True, wenn ein Element in der Schriftarten-Kombinationsfeld die angegebene Schriftart-Beschreibungsobjekt oder Schriftartname und Zeichensatz übereinstimmt. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um auszuwählen, und führen Sie einen Bildlauf zum Element in der Schriftarten-Kombinationsfeld, das die angegebene Schriftart entspricht.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `SelectFont` -Methode in der die `CMFCFontComboBox` Klasse. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>  CMFCFontComboBox::Setup

Initialisiert die Liste der Elemente in der Schriftarten-Kombinationsfeld.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Parameter

*nFontType*<br/>
[in] Gibt die Schriftart an. Der Standardwert ist die bitweise Kombination (OR) DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE.

*nCharSet*<br/>
[in] Gibt den Zeichensatz der Schriftart an. Der Standardwert ist DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
[in] Gibt die Schriftbreite der Schriftart und -Familie. Der Standardwert ist DEFAULT_PITCH.

### <a name="return-value"></a>Rückgabewert

True, wenn das Schriftarten-Kombinationsfeld erfolgreich initialisiert wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode initialisiert die Schriftarten-Kombinationsfeld durch Aufzählen der derzeit installierten Schriftarten, die mit die angegebenen Parametern übereinstimmen und die Namen von Schriftarten in das Schriftarten-Kombinationsfeld eingefügt.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Setup` -Methode in der die `CMFCFontComboBox` Klasse. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)
