---
title: CMFCRibbonFontComboBox-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50094e9caaf712588c12a259f4886360374e430e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376783"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox-Klasse

Implementiert ein Kombinationsfeld, das eine Liste von Schriftarten enthält. Das Kombinationsfeld kann in einem Menübandbereich platziert werden.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Destruktor.|

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Erstellt und initialisiert ein `CMFCRibbonFontComboBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|
|`CMFCRibbonFontComboBox::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Gibt den angegebenen Zeichensatz zurück.|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.|
|`CMFCRibbonFontComboBox::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des zuvor angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Wählt die angegebene Schriftart im Kombinationsfeld aus.|

## <a name="remarks"></a>Hinweise

Nach der Erstellung einer `CMFCRibbonFontComboBox` Objekt, das durch den Aufruf zum Menübandbereich hinzufügen [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonComboBox.h

##  <a name="buildfonts"></a>  CMFCRibbonFontComboBox::BuildFonts

Füllt das Kombinationsfeld im Menüband mit Schriftarten an.

```
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Parameter

*nFontType*<br/>
[in] Gibt die Schriftart der Schriftarten hinzufügen.

*nCharSet*<br/>
[in] Gibt den Zeichensatz der Schriftarten hinzufügen.

*nPitchAndFamily*<br/>
[in] Gibt die Schriftbreite und Schriftfamilie der Schriftarten hinzufügen.

##  <a name="cmfcribbonfontcombobox"></a>  CMFCRibbonFontComboBox::CMFCRibbonFontComboBox

Erstellt und initialisiert ein [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) Objekt.

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Die Befehls-ID des Befehls, der ausgeführt wird, wenn der Benutzer ein Element aus dem Kombinationsfeld auswählt.

*nFontType*<br/>
[in] Gibt an, welche Schriftart zu Typen, für die im Kombinationsfeld angezeigt. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.

*nCharSet*<br/>
[in] Filtert die Schriftarten in das Kombinationsfeld, mit denen, die den angegebenen Zeichensatz angehören...

*nPitchAndFamily*<br/>
[in] Gibt die Schriftbreite und Schriftfamilie der Schriftarten, die im Kombinationsfeld angezeigt werden.

*nWidth*<br/>
[in] Die Breite angibt in Pixel des Kombinationsfelds.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu möglichen *nFontType* Parameterwerten finden Sie unter [EnumFontFamProc](https://msdn.microsoft.com/library/windows/desktop/dd162621) in der Windows SDK-Dokumentation.

Weitere Informationen zu gültigen Zeichensätzen, die zugewiesen werden können *nCharSet*, und der gültigen Werte, die zugewiesen werden können *nPitchAndFamily*, finden Sie unter ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) in der Windows SDK-Dokumentation.

##  <a name="getfontdesc"></a>  CMFCRibbonFontComboBox::GetFontDesc

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Parameter

[in] *iIndex*

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="rebuildfonts"></a>  CMFCRibbonFontComboBox::RebuildFonts

Füllt das Kombinationsfeld im Menüband mit Schriftarten eines zuvor angegebenen Schriftarttyps, Zeichensatzes, und Pitch und Familie an.

```
void RebuildFonts();
```

### <a name="remarks"></a>Hinweise

Sie können die Schriftart, den Zeichensatz angeben und die Schriftbreite und Schriftfamilie der Schriftarten in das Menüband Schriftarten-Kombinationsfeld eingeschlossen werden sollen, die im Dialogfeld die [Konstruktor](#cmfcribbonfontcombobox) für diese Klasse oder durch Aufrufen von [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).

##  <a name="setfont"></a>  CMFCRibbonFontComboBox::SetFont

Wählt die angegebene Schriftart im Kombinationsfeld aus.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Parameter

' Wert * gibt an, den Namen der Schriftart auswählen.

*nCharSet*<br/>
Gibt den Zeichensatz für die ausgewählte Schriftart an.

*bExact*<br/>
True, um anzugeben, dass der Zeichensatz übereinstimmen muss, wenn Sie eine Schriftart auswählen. "False", um anzugeben, dass der Zeichensatz kann ignoriert werden, wenn Sie eine Schriftart auswählen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die angegebene Schriftart gefunden und aktiviert wurde; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

##  <a name="getcharset"></a>  CMFCRibbonFontComboBox::GetCharSet

Gibt den angegebenen Zeichensatz zurück.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Rückgabewert

Zeichensatz (siehe "LogFont" in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

##  <a name="getfonttype"></a>  CMFCRibbonFontComboBox::GetFontType

Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.

```
int GetFontType() const;
```

### <a name="return-value"></a>Rückgabewert

Schriftarttypen (Siehe EnumFontFamProc in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

##  <a name="getpitchandfamily"></a>  CMFCRibbonFontComboBox::GetPitchAndFamily

Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Rückgabewert

Schriftbreite und Schriftfamilie (siehe "LogFont" in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox-Klasse](../../mfc/reference/cmfcribboncombobox-class.md)
