---
title: COleVariant-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: 2b2d0935380caed8ad9d6741b9107a5f879f7903
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268059"
---
# <a name="colevariant-class"></a>COleVariant-Klasse

Kapselt den Datentyp [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) .

## <a name="syntax"></a>Syntax

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleVariant::COleVariant](#colevariant)|Erstellt ein `COleVariant`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleVariant::Attach](#attach)|Fügt eine Variante an ein `COleVariant`.|
|[COleVariant::ChangeType](#changetype)|Ändert den variant-Typ dieses `COleVariant` Objekt.|
|[COleVariant::Clear](#clear)|Löscht dieses `COleVariant` Objekt.|
|[COleVariant::Detach](#detach)|Trennt eine Variante von einem `COleVariant` und gibt die Variante.|
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Ruft ein Bytearray aus einem vorhandenen variant-Array ab.|
|[COleVariant::SetString](#setstring)|Legt die Zeichenfolge auf einen bestimmten Typ, in der Regel die ANSI fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Konvertiert eine `COleVariant` -Wert in eine `LPCVARIANT`.|
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Konvertiert eine `COleVariant` -Objekt in ein `LPVARIANT`.|
|[COleVariant::operator =](#operator_eq)|Kopiert ein `COleVariant` Wert.|
|[COleVariant::operator ==](#operator_eq_eq)|Vergleicht zwei `COleVariant` Werte.|
|[COleVariant::operator &lt;&lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|Ausgaben eine `COleVariant` Wert `CArchive` oder `CDumpContext` und gibt eine `COleVariant` -Sitzungsobjekts `CArchive`.|

## <a name="remarks"></a>Hinweise

Dieser Datentyp wird in OLE-Automatisierung verwendet. Insbesondere die [DISPPARAMS](/windows/desktop/api/oaidl/ns-oaidl-tagdispparams) Struktur enthält einen Zeiger auf ein Array von VARIANT-Strukturen. Ein `DISPPARAMS` Struktur wird verwendet, um zum Übergeben von Parametern [IDispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

> [!NOTE]
> Diese Klasse ist abgeleitet von der `VARIANT` Struktur. Dies bedeutet, Sie können übergeben eine `COleVariant` in einem Parameter, der für eine `VARIANT` und Datenmember der der `VARIANT` Struktur werden die zugänglichen Datenmember `COleVariant`.

Die beiden MFC-Klassen beziehen [COleCurrency](../../mfc/reference/colecurrency-class.md) und [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) kapseln die Währung des variant-Datentypen ( `VT_CY`) und das Datum ( `VT_DATE`). Die `COleVariant` -Klasse wird häufig in den DAO-Klassen verwendet, finden Sie diese Klassen für die typische Verwendung dieser Klasse, z. B. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) und [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy), [DISPPARAMS](/windows/desktop/api/oaidl/ns-oaidl-tagdispparams), und [IDispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Einträge in das Windows SDK.

Weitere Informationen zu den `COleVariant` -Klasse und deren Verwendung in OLE-Automatisierung, finden Sie unter "Übergeben von Parametern in OLE Automation" im Artikel [Automation](../../mfc/automation.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="attach"></a>  COleVariant::Attach

Rufen Sie diese Funktion zum Anfügen der angegebenen [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) -Objekt mit dem aktuellen `COleVariant` Objekt.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
Eine vorhandene `VARIANT` Objekt, das dem aktuellen angefügt werden `COleVariant` Objekt.

### <a name="remarks"></a>Hinweise

Diese Funktion legt VARTYPE des *VarSrc* auf VT_EMPTY.

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) und [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Einträge in das Windows SDK.

##  <a name="colevariant"></a>  COleVariant::COleVariant

Erstellt ein `COleVariant`-Objekt.

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
Eine vorhandene `COleVariant` oder `VARIANT` Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*pSrc*<br/>
Ein Zeiger auf eine `VARIANT` -Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*lpszSrc*<br/>
Eine mit Null endende Zeichenfolge, die in die neue kopiert werden `COleVariant` Objekt.

*vtSrc*<br/>
Die `VARTYPE` für das neue `COleVariant` Objekt.

*strSrc*<br/>
Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*nSrc*, *lSrc* einen numerischen Wert in die neue kopiert werden `COleVariant` Objekt.

*vtSrc*<br/>
Die `VARTYPE` für das neue `COleVariant` Objekt.

*curSrc*<br/>
Ein [COleCurrency](../../mfc/reference/colecurrency-class.md) Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*fltSrc*, *dblSrc*<br/>
Ein in das neue `COleVariant`-Objekt zu kopierender numerischer Wert.

*timeSrc*<br/>
Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*arrSrc*<br/>
Ein [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*lbSrc*<br/>
Ein [CLongBinary](../../mfc/reference/clongbinary-class.md) Objekt, das in die neue kopiert werden `COleVariant` Objekt.

*pidl*<br/>
Ein Zeiger auf eine [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) Struktur in die neue kopiert werden `COleVariant` Objekt.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleVariant` Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt.

- **COleVariant ()** erstellt ein leeres `COleVariant` Objekt VT_EMPTY.

- **COleVariant (** *VarSrc* **)** kopiert eine vorhandene `VARIANT` oder `COleVariant` Objekt. Der Varianttyp wird beibehalten.

- **COleVariant (** *pSrc* **)** kopiert eine vorhandene `VARIANT` oder `COleVariant` Objekt. Der Varianttyp wird beibehalten.

- **COleVariant (** *LpszSrc* **)** kopiert eine Zeichenfolge in das neue Objekt, VT_BSTR (UNICODE).

- **COleVariant (** *LpszSrc* **,** *VtSrc* **)** kopiert eine Zeichenfolge in das neue Objekt. Der Parameter *VtSrc* VT_BSTR (UNICODE) oder VT_BSTRT (ANSI) sein muss.

- **COleVariant (** *StrSrc* **)** kopiert eine Zeichenfolge in das neue Objekt, VT_BSTR (UNICODE).

- **COleVariant (** *nSrc* **)** 8-Bit-Ganzzahl in das neue Objekt, VT_UI1 kopiert.

- **COleVariant (** *nSrc* **,** *VtSrc* **)** eine 16-Bit-Ganzzahl (oder ein boolescher Wert) in das neue Objekt kopiert. Der Parameter *VtSrc* VT_I2 oder VT_BOOL sein muss.

- **COleVariant (** *lSrc* **,** *VtSrc* **)** eine 32-Bit-Ganzzahl (oder SCODE-Wert) in das neue Objekt kopiert. Der Parameter *VtSrc* VT_I4, VT_BOOL oder VT_ERROR werden muss.

- **COleVariant (** *CurSrc* **)** Kopien einer `COleCurrency` Wert in das neue Objekt, VT_CY.

- **COleVariant (** *FltSrc* **)** einen 32-Bit-Gleitkommawert in das neue Objekt, VT_R4 kopiert.

- **COleVariant (** *DblSrc* **)** einen 64-Bit-Gleitkommawert in das neue Objekt, VT_R8 kopiert.

- **COleVariant (** *TimeSrc* **)** Kopien einer `COleDateTime` Wert in das neue Objekt, VT_DATE.

- **COleVariant (** *ArrSrc* **)** Kopien einer `CByteArray` Objekt in das neue Objekt, VT_EMPTY.

- **COleVariant (** *LbSrc* **)** Kopien einer `CLongBinary` Objekt in das neue Objekt, VT_EMPTY.

Weitere Informationen zu SCODE, finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes) im Windows SDK.

##  <a name="changetype"></a>  COleVariant::ChangeType

Konvertiert den Typ des variant-Wert in diesem `COleVariant` Objekt.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Parameter

*vartype*<br/>
Für diese VARTYPE `COleVariant` Objekt.

*pSrc*<br/>
Ein Zeiger auf die [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) zu konvertierenden Objekts. Wenn dieser Wert NULL aufweist, ist dies `COleVariant` Objekt als Quelle für die Konvertierung verwendet wird.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), und [VariantChangeType](/windows/desktop/api/oleauto/nf-oleauto-variantchangetype) Einträge in das Windows SDK.

##  <a name="clear"></a>  COleVariant::Clear

Löscht die `VARIANT`.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Hiermit werden die VARTYPE für dieses Objekt auf VT_EMPTY. Die `COleVariant` Destruktor ruft diese Funktion.

Weitere Informationen finden Sie unter den `VARIANT`, VARTYPE, und `VariantClear` Einträge in das Windows SDK.

##  <a name="detach"></a>  COleVariant::Detach

Trennt die zugrunde liegende [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) -Objekt aus diesem `COleVariant` Objekt.

```
VARIANT Detach();
```

### <a name="remarks"></a>Hinweise

Diese Funktion legt die VARTYPE für diesen `COleVariant` Objekt auf VT_EMPTY.

> [!NOTE]
>  Nach dem Aufruf `Detach`, es ist der Verantwortung des Aufrufers Aufrufen `VariantClear` für das resultierende `VARIANT` Struktur.

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), und [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear) Einträge in das Windows SDK.

##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray

Ruft ein Bytearray aus einem vorhandenen variant-array

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parameter

*bytes*<br/>
Ein Verweis auf einen vorhandenen [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.

##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT

Dieser Umwandlungsoperator gibt eine `VARIANT` -Struktur, deren Wert wird aus dieser kopiert `COleVariant` Objekt.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Hinweise

##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT

Rufen Sie diese Umwandlungsoperator für den Zugriff auf die zugrunde liegende `VARIANT` Struktur für diese `COleVariant` Objekt.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Hinweise

> [!CAUTION]
> Ändern des Werts in der `VARIANT` Struktur, die Zugriff auf die von dieser Funktion zurückgegebenen Zeiger ändert sich den Wert dieser `COleVariant` Objekt.

##  <a name="operator_eq"></a>  COleVariant::operator =

Diese überladenen Zuweisungsoperatoren kopieren Sie den Wert des in dieser `COleVariant` Objekt.

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>Hinweise

Es folgt eine kurze Beschreibung der einzelnen Operatoren:

- **Operator = (** *VarSrc* **)** kopiert eine vorhandene Variante oder `COleVariant` Objekt in dieses Objekt.

- **Operator = (** *pSrc* **)** kopiert das VARIANT-Objekt zugegriffen *pSrc* in dieses Objekt.

- **Operator = (** *LpszSrc* **)** eine Null-terminierte Zeichenfolge in dieses Objekt kopiert und VARTYPE auf VT_BSTR.

- **Operator = (** *StrSrc* **)** Kopien einer [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekts in dieses Objekt und legt den VARTYPE auf VT_BSTR.

- **Operator = (** *nSrc* **)** 8 oder 16-Bit-Ganzzahlwert in dieses Objekt kopiert. Wenn *nSrc* ist ein 8-Bit-Wert, VARTYPE dieses auf VT_UI1 festgelegt ist. Wenn *nSrc* ist ein 16-Bit-Wert und VARTYPE dieser lautet VT_BOOL, sie wird beibehalten; andernfalls, VT_I2 festgelegt ist.

- **Operator = (** *lSrc* **)** kopiert einen 32-Bit-Ganzzahl-Wert in dieses Objekt. Wenn dieses VARTYPE VT_ERROR ist, bleibt es; Andernfalls wird es auf VT_I4 festgelegt.

- **Operator = (** *CurSrc* **)** Kopien einer [COleCurrency](../../mfc/reference/colecurrency-class.md) -Objekts in dieses Objekt und legt den VARTYPE zu VT_CY.

- **Operator = (** *FltSrc* **)** einen 32-Bit-Gleitkommawert in dieses Objekt kopiert und VARTYPE auf VT_R4.

- **Operator = (** *DblSrc* **)** einen 64-Bit-Gleitkommawert in dieses Objekt kopiert und VARTYPE auf VT_R8.

- **Operator = (** *DateSrc* **)** Kopien einer [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekts in dieses Objekt und legt den VARTYPE, VT_DATE.

- **Operator = (** *ArrSrc* **)** Kopien einer [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt in diese `COleVariant` Objekt.

- **Operator = (** *LbSrc* **)** Kopien einer [CLongBinary](../../mfc/reference/clongbinary-class.md) Objekt in diese `COleVariant` Objekt.

Weitere Informationen finden Sie unter den [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) und [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Einträge in das Windows SDK.

##  <a name="operator_eq_eq"></a>  COleVariant::operator ==

Dieser Operator vergleicht zwei Variante-Werten und gibt ungleich NULL, wenn sie gleich sind; andernfalls 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;, &gt;&gt;

Ausgaben eine `COleVariant` Wert `CArchive` oder `CdumpContext` und gibt eine `COleVariant` -Sitzungsobjekts `CArchive`.

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>Hinweise

Die `COleVariant` einfügen (**\<\<**) Operator unterstützt diagnostic Dump-Sicherungen und in ein Archiv speichern. Die Extraktion (**>>**) Operator unterstützt das Laden aus einem Archiv.

##  <a name="setstring"></a>  COleVariant::SetString

Legt die Zeichenfolge in einen bestimmten Typ fest.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Parameter

*lpszSrc*<br/>
Eine mit Null endende Zeichenfolge, die in die neue kopiert werden `COleVariant` Objekt.

*VtSrc*<br/>
Für die neue VARTYPE `COleVariant` Objekt.

### <a name="remarks"></a>Hinweise

Der Parameter *VtSrc* VT_BSTR (UNICODE) oder VT_BSTRT (ANSI) sein muss. `SetString` dient normalerweise zum Festlegen von Zeichenfolgen in ANSI, seit der Standardwert für die [COleVariant::COleVariant](#colevariant) Konstruktor mit einer Zeichenfolge oder Zeichenfolgenzeiger-Parameter und keine VARTYPE ist UNICODE.

DAO-Recordsets in ein nicht-UNICODE-Build erwartet, dass Zeichenfolgen ANSI sein. Daher für DAO-Funktionen mit `COleVariant` Objekte, wenn Sie ein UNICODE-Recordset nicht erstellen, müssen Sie verwenden die **COleVariant::COleVariant (** *LpszSrc* **,** *VtSrc* **)** Form des Konstruktors mit *VtSrc* festgelegt, die VT_BSTRT (ANSI), oder verwenden Sie `SetString` mit *VtSrc* VT festgelegt _BSTRT zu ANSI-Zeichenfolgen. Z. B. die `CDaoRecordset` Funktionen [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) und [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) verwenden `COleVariant` Objekte als Parameter. Diese Objekte müssen ANSI sein, wenn die DAO-Recordsets ist nicht UNICODE.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
