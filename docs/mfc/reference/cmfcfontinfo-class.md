---
title: CMFCFontInfo-Klasse
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
ms.openlocfilehash: 930aceb4514195f0e844c35d326b52d9cd8d31fa
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781327"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo-Klasse

Die `CMFCFontInfo` Klasse beschreibt die Namen und andere Attribute einer Schriftart.

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
|[CMFCFontInfo::GetFullName](#getfullname)|Ruft die verketteten Namen einer Schriftart und das Zeichen legen Sie (Skript).|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Ein Wert, der den Zeichensatz (Skript) verknüpft ist, mit der Schriftart angibt.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Ein Wert, der die Schriftbreite und die Familie der Schriftart angibt.|
|[CMFCFontInfo::m_nType](#m_ntype)|Ein Wert, der den Typ der Schriftart angibt.|
|[CMFCFontInfo::m_strName](#m_strname)|Der Name der Schriftart; z. B. **Arial**.|
|[CMFCFontInfo::m_strScript](#m_strscript)|Der Name eines Zeichensatzes (Skript), die die Schriftart zugeordnet werden soll.|

## <a name="remarks"></a>Hinweise

Sie anfügen können eine `CMFCFontInfo` Objekt, das ein Element mit dem [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Klasse. Rufen Sie die [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) Methode zum Abrufen der eines Zeigers auf eine `CMFCFontInfo` Objekt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie verschiedene Mitglieder der `CMFCFontInfo` Klasse. Im Beispiel wird veranschaulicht, wie zum Abrufen einer `CMFCFontInfo` -Objekt aus einem `CMFCRibbonFontComboBox`, und wie Sie ihre lokalen Variablen zugreifen. In diesem Beispiel ist Teil der [MSOffice 2007 Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarfontcombobox.h

##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo

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

*lpszName*<br/>
[in] Der Name der Schriftart. Weitere Informationen finden Sie unter den `lfFaceName` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur.

*lpszScript*<br/>
[in] Der Name des Skripts (Zeichensatz) der Schriftart.

*nCharSet*<br/>
[in] Ein Wert, der den Zeichensatz (Skript) der Schriftart angibt. Weitere Informationen finden Sie unter den `lfCharSet` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur.

*nPitchAndFamily*<br/>
[in] Ein Wert, der die Schriftbreite und die Familie der Schriftart angibt. Weitere Informationen finden Sie unter den `lfPitchAndFamily` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur.

*nType*<br/>
[in] Ein Wert, der die Schriftart angibt. Dieser Parameter kann eine bitweise Kombination (OR) von DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE sein.

*src*<br/>
[in] Eine vorhandene `CMFCFontInfo` , deren Mitglieder werden zum Erstellen dieses, Objekts `CMFCFontInfo` Objekt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

In dieser Dokumentation werden die Begriffe verwendet *Zeichensatz* und *Skript* Synonym verwenden lassen. Ein *Skript*, auch bekannt als ein Schriftsystem, d.h. ist eine Sammlung von Zeichen und Regeln für diese Zeichen in eine oder mehrere Sprachen schreiben. Die Auflistung von Zeichen enthält, die Alphabet und Satzzeichen im Skript verwendet. Lateinischer Schrift wird z. B. für Englisch verwendet, wie es in den Vereinigten Staaten gesprochen wird, und die Buchstaben, die Zeichen von A bis Z enthält. Die `lfCharSet` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur gibt einen Zeichensatz an. Der Wert ANSI_CHARSET gibt beispielsweise die ANSI-Zeichensatz, der des lateinischen Alphabets enthält.

##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName

Ruft die verketteten Namen einer Schriftart und das Zeichen legen Sie (Skript).

```
CString GetFullName() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Zeichenfolge, die den Schriftartnamen und das Skript enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um den vollständigen Namen der Schriftart zu erhalten. Wenn die Schriftart ist z. B. **Arial** und das Schriftartenskript ist **Kyrillisch**, gibt diese Methode "Arial (Kyrillisch)" zurück.

##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet

Ein Wert, der den Zeichensatz (Skript) verknüpft ist, mit der Schriftart angibt.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den *nCharSet* Parameter, der die [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.

##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily

Ein Wert, der die Schriftbreite (Größe) und (z. B. "Serif", "sans-Serif" und "Monospace")-Familie der Schriftart angibt.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den *nPitchAndFamily* Parameter, der die [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.

##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType

Ein Wert, der den Typ der Schriftart angibt.

```
const int m_nType;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den *nType* Parameter, der die [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.

##  <a name="m_strname"></a>  CMFCFontInfo::m_strName

Der Name der Schriftart: z. B. **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den *Wert* Parameter, der die [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.

##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript

Der Name eines Zeichensatzes (Skript), die die Schriftart zugeordnet werden soll.

```
const CString m_strScript;
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den *LpszScript* Parameter, der die [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Konstruktor.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox-Klasse](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
