---
title: Cmfcribbonfontcombobox-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 186c4bc3e1b26529ed0e000d2893e1b2d81c4304
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504956"
---
# <a name="cmfcribbonfontcombobox-class"></a>Cmfcribbonfontcombobox-Klasse

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
|`CMFCRibbonFontComboBox::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des zuvor angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Wählt die angegebene Schriftart im Kombinationsfeld aus.|

## <a name="remarks"></a>Hinweise

Nachdem Sie ein `CMFCRibbonFontComboBox` -Objekt erstellt haben, fügen Sie es einem Menü Band Bereich hinzu, indem Sie [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribboncombobox. h

##  <a name="buildfonts"></a>Cmfcribbonfontcombobox:: buildfonts

Füllt das Kombinations Feld im Menüband mit Schriftarten auf.

```
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Parameter

*nFontType*<br/>
in Gibt den Schriftart-Typ der hinzu zufügenden Schriftarten an.

*nCharSet*<br/>
in Gibt den Zeichensatz der Schriftarten an, die hinzugefügt werden sollen.

*nPitchAndFamily*<br/>
in Gibt die Schriftarten und die Familie der hinzu zufügenden Schriftarten an.

##  <a name="cmfcribbonfontcombobox"></a>Cmfcribbonfontcombobox:: cmfcribbonfontcombobox

Erstellt und initialisiert ein [cmfcribbonfontcombobox](../../mfc/reference/cmfcribbonfontcombobox-class.md) -Objekt.

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
in Die Befehls-ID des Befehls, der ausgeführt wird, wenn der Benutzer ein Element aus dem Kombinations Feld auswählt.

*nFontType*<br/>
in Gibt an, welche Schriftart Typen im Kombinations Feld angezeigt werden sollen. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.

*nCharSet*<br/>
in Filtert die Schriftarten im Kombinations Feld mit denen, die zum angegebenen Zeichensatz gehören.

*nPitchAndFamily*<br/>
in Gibt die Tonhöhe und die Familie der Schriftarten an, die im Kombinations Feld angezeigt werden.

*nWidth*<br/>
in Gibt die Breite des Kombinations Felds in Pixel an.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu möglichen *nfonttype* -Parameterwerten finden Sie unter [enumfontfamproc](/previous-versions/dd162621\(v=vs.85\)) in der Windows SDK-Dokumentation.

Weitere Informationen zu gültigen Zeichensätzen, die *ncharset*zugewiesen werden können, und zu gültigen Werten, die *npitchandfamily*zugewiesen werden können, finden Sie unter [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) in der Windows SDK-Dokumentation.

##  <a name="getfontdesc"></a>Cmfcribbonfontcombobox:: getfontdebug

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Parameter

in *iIndex*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="rebuildfonts"></a>Cmfcribbonfontcombobox:: rebuildfonts

Füllt das Kombinations Feld auf dem Menüband mit Schriftarten eines zuvor angegebenen Schriftart Typs, Zeichensatzes und einer angegebenen Produktfamilie auf.

```
void RebuildFonts();
```

### <a name="remarks"></a>Hinweise

Sie können den Schriftart-und den Zeichensatz sowie die Schriftarten und die Familie der Schriftarten angeben, die im [Konstruktor](#cmfcribbonfontcombobox) für diese Klasse in das Menü Band Schriftart-Kombinations Feld eingeschlossen werden sollen, oder indem Sie [cmfcribbonfontcombobox:: buildfonts](#buildfonts)aufrufen.

##  <a name="setfont"></a>Cmfcribbonfontcombobox:: SetFont

Wählt die angegebene Schriftart im Kombinationsfeld aus.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Parameter

"lpszname *" gibt den Namen der Schriftart an, die ausgewählt werden soll.

*nCharSet*<br/>
Gibt den Zeichensatz für die ausgewählte Schriftart an.

*bExact*<br/>
TRUE, um anzugeben, dass der Zeichensatz bei der Auswahl einer Schriftart entsprechen muss. FALSE, um anzugeben, dass der Zeichensatz bei der Auswahl einer Schriftart ignoriert werden kann.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die angegebene Schriftart gefunden und ausgewählt wurde. andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

##  <a name="getcharset"></a>Cmfcribbonfontcombobox:: getcharset

Gibt den angegebenen Zeichensatz zurück.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Rückgabewert

Zeichensatz (siehe LogFont in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

##  <a name="getfonttype"></a>Cmfcribbonfontcombobox:: getfonttype

Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.

```
int GetFontType() const;
```

### <a name="return-value"></a>Rückgabewert

Schriftart Typen (siehe "enumfontfamproc" in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

##  <a name="getpitchandfamily"></a>Cmfcribbonfontcombobox:: getpitchandfamily

Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Rückgabewert

Tonhöhe und die-Familie (siehe LogFont in der Windows SDK-Dokumentation).

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox-Klasse](../../mfc/reference/cmfcribboncombobox-class.md)
