---
title: CMFCPropertyGridFontProperty-Klasse
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
ms.openlocfilehash: 2ab4f43b2b12dff88148097e2961f235669aaa62
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295668"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty-Klasse

Die `CMFCPropertyGridFileProperty` Klasse unterstützt, einem Eigenschaftenlisten-Steuerelement ein Element, das ein Dialogfeld zur Schriftartauswahl öffnet.

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
|`CMFCPropertyGridFontProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts. (Überschreibt [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Ruft die Schriftfarbe, die der Benutzer im Dialogfeld "Schriftart" auswählt.|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Ruft die Schriftart, die der Benutzer im Dialogfeld "Schriftart" auswählt.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist. (Überschreibt [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertygridctrl.h

##  <a name="cmfcpropertygridfontproperty"></a>  CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty

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
[in] Der Name der Eigenschaft.

*lf*<br/>
[in] Eine logische Schriftart-Struktur, die die Attribute der Schriftart angibt.

*dwFontDialogFlags*<br/>
[in] Formatvorlagen, die auf das Dialogfeld Schriftart angewendet werden, die angezeigt wird, wenn Sie die Eigenschaft Wert Dropdown-Schaltfläche klicken. Der Standardwert ist die bitweise Kombination (OR) von CF_EFFECTS und CF_SCREENFONTS. Weitere Informationen finden Sie unter den *Flags* Parameter, der die [CHOOSEFONT Struktur](/windows/desktop/api/commdlg/ns-commdlg-tagchoosefonta).

*lpszDescr*<br/>
[in] Beschreibung der Font-Eigenschaft. Der Standardwert ist NULL.

*dwData*<br/>
[in] Anwendungsspezifische Daten, z. B. eine ganze Zahl oder ein Zeiger auf andere Daten, die der Eigenschaft zugeordnet ist. Der Standardwert ist 0.

*color*<br/>
[in] Die Farbe der Schriftart. Der Standardwert ist die Standardfarbe.

### <a name="remarks"></a>Hinweise

Ein `CMFCPropertyGridFontProperty` -Objekt stellt eine Font-Eigenschaft im Eigenschaftenraster-Steuerelement eine Schriftart dar.

### <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie erstellen Sie ein Objekt von der `CMFCPropertyGridFontProperty` Klasse. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

##  <a name="getcolor"></a>  CMFCPropertyGridFontProperty::GetColor

Ruft die Schriftfarbe, die der Benutzer im Dialogfeld "Schriftart" auswählt.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Farbwert, der die Farbe der ausgewählten Schriftart darstellt.

### <a name="remarks"></a>Hinweise

##  <a name="getlogfont"></a>  CMFCPropertyGridFontProperty::GetLogFont

Ruft die Schriftart, die der Benutzer im Dialogfeld "Schriftart" auswählt.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur, die die ausgewählte Schriftart beschreibt.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)
