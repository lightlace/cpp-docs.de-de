---
title: Cmfcfontinfo-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: a27606b494b13cd7b50f01b38fa95a918bacc7aa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505279"
---
# <a name="cmfcfontinfo-class"></a>Cmfcfontinfo-Klasse

Die `CMFCFontInfo` -Klasse beschreibt den Namen und andere Attribute einer Schriftart.

## <a name="syntax"></a>Syntax

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCFontInfo`|Erstellt ein `CMFCFontInfo`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|Ruft die verketteten Namen einer Schriftart und des zugehörigen Zeichensatzes (Skript) ab.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Ein-Wert, der den der Schriftart zugeordneten Zeichensatz (Skript) angibt.|
|[Cmfcfontinfo:: m_nPitchAndFamily](#m_npitchandfamily)|Ein-Wert, der die Schrift Breite und die Familie der Schriftart angibt.|
|[CMFCFontInfo::m_nType](#m_ntype)|Ein-Wert, der den Typ der Schriftart angibt.|
|[Cmfcfontinfo:: m_strName](#m_strname)|Der Name der Schriftart. beispielsweise **Arial**.|
|[Cmfcfontinfo:: m_strScript](#m_strscript)|Der Name eines Zeichensatzes (Skript), der der Schriftart zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Sie können ein `CMFCFontInfo` -Objekt an ein Element der [cmfctoolbarfontcombobox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md) -Klasse anfügen. Rufen Sie die [cmfctoolbarfontcombobox:: getfontdesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) -Methode auf, um einen `CMFCFontInfo` Zeiger auf ein-Objekt abzurufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie verschiedene Member der `CMFCFontInfo` -Klasse verwendet werden. Das Beispiel veranschaulicht, wie Sie ein `CMFCFontInfo` -Objekt aus `CMFCRibbonFontComboBox`einem abrufen und auf seine lokalen Variablen zugreifen. Dieses Beispiel ist Teil des [MSOffice 2007-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarfontcombobox. h

##  <a name="cmfcfontinfo"></a>Cmfcfontinfo:: cmfcfontinfo

Erstellt ein `CMFCFontInfo`-Objekt.

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
in Der Name der Schriftart. Weitere Informationen finden Sie unter dem `lfFaceName` -Member der [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur.

*lpszScript*<br/>
in Der Name des Skripts (Zeichensatz) der Schriftart.

*nCharSet*<br/>
in Ein-Wert, der den Zeichensatz (Skript) der Schriftart angibt. Weitere Informationen finden Sie unter dem `lfCharSet` -Member der [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur.

*nPitchAndFamily*<br/>
in Ein-Wert, der die Schrift Breite und die Familie der Schriftart angibt. Weitere Informationen finden Sie unter dem `lfPitchAndFamily` -Member der [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur.

*nType*<br/>
in Ein-Wert, der den Schriftart-Typ angibt. Dieser Parameter kann eine bitweise Kombination (or) von DEVICE_FONTTYPE, RASTER_FONTTYPE und TRUETYPE_FONTTYPE sein.

*src*<br/>
in Ein vorhandenes `CMFCFontInfo` -Objekt, dessen Member zum Erstellen `CMFCFontInfo` dieses-Objekts verwendet werden.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

In dieser Dokumentation werden die Begriffe " *Zeichensatz* " und " *Skript* austauschbar" verwendet. Ein *Skript*, das auch als Schreibsystem bezeichnet wird, ist eine Sammlung von Zeichen und Regeln zum Schreiben dieser Zeichen in einer oder mehreren Sprachen. Die Zeichen Auflistung schließt das in diesem Skript verwendete Alphabet und Interpunktions Zeichen ein. Das lateinische Skript wird z. b. für Englisch verwendet, da es im USA gesprochen wird, und sein Alphabet enthält die Zeichen von A bis Z. Der `lfCharSet` -Member der [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) -Struktur gibt einen Zeichensatz an. Der Wert ANSI_CHARSET gibt z. b. den ANSI-Zeichensatz an, der das Alphabet des lateinischen Skripts enthält.

##  <a name="getfullname"></a>Cmfcfontinfo:: getfullname

Ruft die verketteten Namen einer Schriftart und des zugehörigen Zeichensatzes (Skript) ab.

```
CString GetFullName() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die den Schriftart Namen und das Skript enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um den vollständigen Namen der Schriftart abzurufen. Wenn der Schriftart Name beispielsweise **Arial** lautet und das Schriftart Skript **Kyrillisch**ist, gibt diese Methode "Arial (Kyrillisch)" zurück.

##  <a name="m_ncharset"></a>Cmfcfontinfo:: m_nCharSet

Ein-Wert, der den der Schriftart zugeordneten Zeichensatz (Skript) angibt.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem *ncharset* -Parameter des [cmfcfontinfo:: cmfcfontinfo](#cmfcfontinfo) -Konstruktors.

##  <a name="m_npitchandfamily"></a>Cmfcfontinfo:: m_nPitchAndFamily

Ein-Wert, der die Tonhöhe (Punktgröße) und die Familie (z. b. Serif, Sans-Serif und Monospace) der Schriftart angibt.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem *npitchandfamily* -Parameter des [cmfcfontinfo:: cmfcfontinfo](#cmfcfontinfo) -Konstruktors.

##  <a name="m_ntype"></a>Cmfcfontinfo:: m_nType

Ein-Wert, der den Typ der Schriftart angibt.

```
const int m_nType;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem *nType* -Parameter des [cmfcfontinfo:: cmfcfontinfo](#cmfcfontinfo) -Konstruktors.

##  <a name="m_strname"></a>Cmfcfontinfo:: m_strName

Der Name der Schriftart, z. b. **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem *lpszname* -Parameter des [cmfcfontinfo:: cmfcfontinfo](#cmfcfontinfo) -Konstruktors.

##  <a name="m_strscript"></a>Cmfcfontinfo:: m_strScript

Der Name eines Zeichensatzes (Skript), der der Schriftart zugeordnet ist.

```
const CString m_strScript;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem *lpszscript* -Parameter des [cmfcfontinfo:: cmfcfontinfo](#cmfcfontinfo) -Konstruktors.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox-Klasse](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
