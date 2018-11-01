---
title: Standardroutinen zur Validierung der Dialogfelddaten
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: b5813600bbf8eb2a7b25992b3e1b020fcf8dfa02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513944"
---
# <a name="standard-dialog-data-validation-routines"></a>Standardroutinen zur Validierung der Dialogfelddaten

Dieses Thema enthält das Standarddialogfeld (DDV) datenvalidierungsroutine für allgemeine MFC-Dialogfeld-Steuerelemente verwendet werden.

> [!NOTE]
>  Der standard dialogdatenaustauschroutinen werden in den Header-Datei afxdd_.h definiert. Allerdings sollten Anwendungen afxwin.h enthalten.

### <a name="ddv-functions"></a>DDV-Funktionen

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|Überprüft, ob die Anzahl der Zeichen in einem bestimmten Steuerelement nicht über eine festgelegte maximale überschreitet.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **BYTE** Bereich.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Überprüft, ob ein bestimmtes Steuerelement-Wert ein angegebenen Zeitbereichs nicht überschreitet.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **doppelte** Bereich.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **DWORD** Bereich.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **"float"** Bereich.|
|[DDV_MinMaxInt](#ddv_minmaxint)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **Int** Bereich.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **lange** Bereich.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **LONGLONG** Bereich.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Überprüft, ob ein bestimmtes Steuerelementwert nicht mit einen bestimmten Zeitraum überschreitet.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **kurze** Bereich.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Überprüft, ob ein Wert des angegebenen Schieberegler-Steuerelements innerhalb des angegebenen Bereichs liegt.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **UINT** Bereich.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|Überprüft, ob ein bestimmtes Steuerelement-Wert zwischen zwei angegebenen Werten liegt.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Überprüft, ob ein bestimmtes Steuerelementwert nicht überschreitet einen bestimmten **ULONGLONG** Bereich.|

##  <a name="ddv_maxchars"></a>  DDV_MaxChars

Rufen Sie `DDV_MaxChars` um sicherzustellen, dass die Menge der Zeichen in dem Steuerelement zugeordnete *Wert* nicht überschreitet *nChars*.

```
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*nChars*<br/>
Maximale Anzahl zulässiger Zeichen.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxbyte"></a>  DDV_MinMaxByte

Rufen Sie `DDV_MinMaxByte` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
(Vom Typ BYTE) zulässigen Mindestwert.

*maxVal*<br/>
(Vom Typ BYTE) zulässigen Höchstwert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxdatetime"></a>  DDV_MinMaxDateTime

Rufen Sie `DDV_MinMaxDateTime` , stellen Sie sicher, dass der Datum/Uhrzeit-Wert in der Datums- / Zeitauswahl-Steuerelement ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) zugeordneten *RefValue* liegt zwischen *RefMinRange*und *RefMaxRange*.

```
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung. Sie müssen nicht das Objekt gelöscht werden.

*refValue*<br/>
Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts zugeordnet. Dieses Objekt enthält die Daten überprüft werden.

*refMinRange*<br/>
Minimale Datum/Uhrzeit-Wert zulässig.

*refMaxRange*<br/>
Zulässige maximale Datum/Uhrzeit-Wert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxdouble"></a>  DDV_MinMaxDouble

Rufen Sie `DDV_MinMaxDouble` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **doppelte**) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **doppelte**) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxdword"></a>  DDV_MinMaxDWord

Rufen Sie `DDV_MinMaxDWord` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
(Vom Typ DWORD) zulässigen Mindestwert.

*maxVal*<br/>
(Vom Typ DWORD) zulässigen Höchstwert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxfloat"></a>  DDV_MinMaxFloat

Rufen Sie `DDV_MinMaxFloat` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **"float"**) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **"float"**) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxint"></a>  DDV_MinMaxInt

Rufen Sie `DDV_MinMaxInt` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **Int**) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **Int**) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxlong"></a>  DDV_MinMaxLong

Rufen Sie `DDV_MinMaxLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **lange**) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **lange**) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxlonglong"></a>  DDV_MinMaxLongLong

Rufen Sie `DDV_MinMaxLongLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
(Vom Typ LONGLONG) zulässigen Mindestwert.

*maxVal*<br/>
Maximale Wert (vom Typ LONGLONG), die zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxmonth"></a>  DDV_MinMaxMonth

Rufen Sie `DDV_MinMaxMonth` , stellen Sie sicher, dass der Datum/Uhrzeit-Wert im Monatskalender-Steuerelement ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) zugeordneten *RefValue* liegt zwischen *RefMinRange* und *RefMaxRange*.

```
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*refValue*<br/>
Ein Verweis auf ein Objekt des Typs `CTime` oder `COleDateTime` zugeordnet sind, mit der eine Membervariable des Dialogfelds, Formularansicht oder Objekt zu steuern. Dieses Objekt enthält die Daten überprüft werden. MFC-übergibt den this-Verweis beim `DDV_MinMaxMonth` aufgerufen wird.

*refMinRange*<br/>
Minimale Datum/Uhrzeit-Wert zulässig.

*refMaxRange*<br/>
Zulässige maximale Datum/Uhrzeit-Wert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxshort"></a>  DDV_MinMaxShort

Rufen Sie `DDV_MinMaxShort` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **kurze**) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **kurze**) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxslider"></a>  DDV_MinMaxSlider

Rufen Sie `DDV_MinMaxSlider` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf das zu überprüfende Wert. Dieser Parameter enthält, oder legt das Schieberegler-Steuerelement aktuelle Thumb-Steuerelementposition fest.

*minVal*<br/>
Minimal zulässige Wert.

*maxVal*<br/>
Maximal zulässige Wert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Weitere Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../../mfc/using-csliderctrl.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxuint"></a>  DDV_MinMaxUInt

Rufen Sie `DDV_MinMaxUInt` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
(Vom Typ "uint") zulässigen Mindestwert.

*maxVal*<br/>
Maximale Wert (vom Typ "uint"), die zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

##  <a name="ddv_minmaxulonglong"></a>  DDV_MinMaxULongLong

Rufen Sie `DDV_MinMaxULongLong` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

```
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
(Vom Typ ULONGLONG) zulässigen Mindestwert.

*maxVal*<br/>
(Vom Typ ULONGLONG) zulässigen Höchstwert.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdd_.h

## <a name="see-also"></a>Siehe auch

[Standard-Dialogdatenaustauschroutinen](../../mfc/reference/standard-dialog-data-exchange-routines.md)<br/>
[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned

Rufen Sie `DDV_MinMaxUnsigned` um sicherzustellen, dass der Wert im Steuerelement zugeordnete *Wert* liegt zwischen *MinVal* und *MaxVal*.

### <a name="syntax"></a>Syntax

```
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>Parameter

*pDX*<br/>
Ein Zeiger auf ein `CDataExchange` -Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit denen Daten überprüft werden.

*minVal*<br/>
Mindestwert (des Typs **ohne Vorzeichen** ) zulässig.

*maxVal*<br/>
Maximale Wert (vom Typ **ohne Vorzeichen** ) zulässig.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu DDV, finden Sie unter [Dialogdatenaustausch und Validierung](../dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

**Header:** afxdd_.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[DDX_Slider](#ddx_slider)<br/>
[DDX_FieldSlider](#ddx_fieldslider)

