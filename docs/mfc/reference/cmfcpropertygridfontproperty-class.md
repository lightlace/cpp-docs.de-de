---
title: Cmfcpropertygridfontproperty-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: a3c5b806482a97d64a9ffab92877781cb8778b6b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505114"
---
# <a name="cmfcpropertygridfontproperty-class"></a>Cmfcpropertygridfontproperty-Klasse

Die `CMFCPropertyGridFileProperty` -Klasse unterstützt ein Eigenschaften Listen-Steuerelement, das ein Dialogfeld zur Schriftart Auswahl öffnet.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Erstellt ein `CMFCPropertyGridFontProperty`-Objekt.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts. (Überschreibt [cmfcpropertygridproperty:: formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Ruft die Schriftart Farbe ab, die der Benutzer aus dem Dialogfeld Schriftart auswählt.|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Ruft die Schriftart ab, die der Benutzer aus dem Dialogfeld Schriftart auswählt.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist. (Überschreibt [cmfcpropertygridproperty:: onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertygridctrl. h

##  <a name="cmfcpropertygridfontproperty"></a>Cmfcpropertygridfontproperty:: cmfcpropertygridfontproperty

Erstellt ein `CMFCPropertyGridFontProperty`-Objekt.

```
CMFCPropertyGridFontProperty(
    const CString& strName,
    LOGFONT& lf,
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0,
    COLORREF color = (COLORREF)-1);
```

### <a name="parameters"></a>Parameter

*strName*<br/>
in Der Name der Eigenschaft.

*lf*<br/>
in Eine logische Schriftart Struktur, die die Attribute der Schriftart angibt.

*dwFontDialogFlags*<br/>
in Stile, die auf das Dialogfeld Schriftart angewendet werden, das angezeigt wird, wenn Sie auf die Dropdown Schaltfläche Eigenschafts Wert klicken. Der Standardwert ist die bitweise Kombination (or) von CF_EFFECTS und CF_SCREENFONTS. Weitere Informationen finden Sie unter dem *Flags* -Parameter der [chooonfont-Struktur](/windows/win32/api/commdlg/ns-commdlg-choosefontw).

*lpszDescr*<br/>
in Beschreibung der Schriftart Eigenschaft. Der Standardwert ist NULL.

*dwData*<br/>
in Anwendungsspezifische Daten, z. b. eine ganze Zahl oder ein Zeiger auf andere Daten, die der-Eigenschaft zugeordnet sind. Der Standardwert ist 0.

*Farbe*<br/>
in Die Farbe der Schriftart. Der Standardwert ist die Standardfarbe.

### <a name="remarks"></a>Hinweise

Ein `CMFCPropertyGridFontProperty` -Objekt stellt eine Schriftart Eigenschaft in einem Eigenschaften Raster-Schriftart Steuerelement dar.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt der `CMFCPropertyGridFontProperty` -Klasse erstellt wird. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>Cmfcpropertygridfontproperty:: GetColor

Ruft die Schriftart Farbe ab, die der Benutzer aus dem Dialogfeld Schriftart auswählt.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Farbwert, der die ausgewählte Schriftfarbe darstellt.

### <a name="remarks"></a>Hinweise

##  <a name="getlogfont"></a>Cmfcpropertygridfontproperty:: getlogfont

Ruft die Schriftart ab, die der Benutzer aus dem Dialogfeld Schriftart auswählt.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur, die die ausgewählte Schriftart beschreibt.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)
