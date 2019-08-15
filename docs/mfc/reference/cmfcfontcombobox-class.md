---
title: Cmfcfontcombobox-Klasse
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
ms.openlocfilehash: 69e8f81e7e01d0610f3cbf88ac1725a21d59838f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505296"
---
# <a name="cmfcfontcombobox-class"></a>Cmfcfontcombobox-Klasse

Die `CMFCFontComboBox` -Klasse erstellt ein Kombinations Feld-Steuerelement, das eine Liste von Schriftarten enthält.

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
|`CMFCFontComboBox::CompareItem`|Wird von Framework aufgerufen, um die relative Position eines neuen Elements im sortierten Listenfeld des aktuellen Schriftart-Kombinations Feld-Steuer Elements zu bestimmen. (Überschreibt [CComboBox:: compareitem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Wird von Framework aufgerufen, um ein angegebenes Element im aktuellen Schriftart-Kombinations Feld-Steuerelement zu zeichnen. (Überschreibt [CComboBox::D rawitem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Ruft Informationen zur aktuell ausgewählten Schriftart ab.|
|`CMFCFontComboBox::MeasureItem`|Wird von Framework aufgerufen, um Fenster über die Abmessungen des Listen Felds im aktuellen Schriftart-Kombinations Feld-Steuerelement zu informieren. (Überschreibt [CComboBox:: MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Wählt die Schriftart aus, die den angegebenen Kriterien aus dem Schriftart-Kombinations Feld entspricht.|
|[CMFCFontComboBox::Setup](#setup)|Initialisiert die Liste der Elemente im Kombinations Feld Schriftart.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Gibt für das Framework an, welche Schriftart zum Zeichnen der Element Bezeichnungen im aktuellen Schriftart-Kombinations Feld verwendet werden soll.|

## <a name="remarks"></a>Hinweise

Fügen Sie der `CMFCFontComboBox` Dialogfeld Klasse eine `CMFCFontComboBox` Variable hinzu, um ein-Objekt in einem Dialogfeld zu verwenden. Rufen Sie dann `OnInitDialog` in der-Methode der Dialogfeld Klasse die [cmfcfontcombobox:: Setup](#setup) -Methode auf, um die Liste der Elemente im Kombinations Feld-Steuerelement zu initialisieren.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxfontcombobox. h

##  <a name="cmfcfontcombobox"></a>Cmfcfontcombobox:: cmfcfontcombobox

Erstellt ein `CMFCFontComboBox`-Objekt.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getselfont"></a>Cmfcfontcombobox:: getselfont

Ruft Informationen zur aktuell ausgewählten Schriftart ab.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das [cmfcfontinfo-Klassen](../../mfc/reference/cmfcfontinfo-class.md) Objekt, das eine Schriftart beschreibt. Der Wert kann NULL sein, wenn im Kombinations Feld keine Schriftart ausgewählt ist.

### <a name="remarks"></a>Hinweise

##  <a name="m_bdrawusingfont"></a>Cmfcfontcombobox:: m_bDrawUsingFont

Gibt für das Framework an, welche Schriftart zum Zeichnen der Element Bezeichnungen im aktuellen Schriftart-Kombinations Feld verwendet werden soll.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Hinweise

Legen Sie dieses Element auf "true" fest, um das Framework anzuweisen, die gleiche Schriftart zum Zeichnen der einzelnen Element Bezeichnungen zu verwenden. Legen Sie dieses Element auf false fest, um das Framework so zu leiten, dass jede Element Bezeichnung mit der Schriftart gezeichnet wird, deren Name mit der Bezeichnung identisch ist. Der Standardwert dieses Members ist false.

##  <a name="selectfont"></a>Cmfcfontcombobox:: selectfont

Wählt die Schriftart aus, die den angegebenen Kriterien aus dem Schriftart-Kombinations Feld entspricht.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Parameter

*pDesc*<br/>
in Verweist auf ein Schriftart Beschreibungs Objekt.

*Wert*<br/>
in Gibt einen Schriftart Namen an.

*nCharSet*<br/>
in Gibt einen Zeichensatz an. Der Standardwert ist DEFAULT_CHARSET. Weitere Informationen finden Sie unter dem `lfCharSet` -Member der [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn ein Element im Schriftart Kombinations Feld mit dem angegebenen Schriftart Beschreibungs Objekt, dem angegebenen Schriftart Namen und dem angegebenen Zeichensatz übereinstimmt. andernfalls false.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um das Element im Kombinations Feld Schriftart auszuwählen und zu dem Element zu scrollen, das der angegebenen Schriftart entspricht.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `SelectFont` -Methode in `CMFCFontComboBox` der-Klasse verwendet wird. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>Cmfcfontcombobox:: Setup

Initialisiert die Liste der Elemente im Kombinations Feld Schriftart.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Parameter

*nFontType*<br/>
in Gibt den Typ der Schriftart an. Der Standardwert ist die bitweise Kombination (or) von DEVICE_FONTTYPE, RASTER_FONTTYPE und TRUETYPE_FONTTYPE.

*nCharSet*<br/>
in Gibt den Schriftzeichen Satz an. Der Standardwert ist DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
in Gibt den Schrift Schnitt und die Familie an. Der Standardwert ist DEFAULT_PITCH.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Schriftart Kombinations Feld erfolgreich initialisiert wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode initialisiert das Schriftart-Kombinations Feld, indem die aktuell installierten Schriftarten aufgelistet werden, die den angegebenen Parametern entsprechen, und diese Schriftart Namen in das Kombinations Feld Schriftart eingefügt werden.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Setup` -Methode in `CMFCFontComboBox` der-Klasse verwendet wird. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)
