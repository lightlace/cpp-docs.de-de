---
title: CDBVariant-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 48a2e08d056e3bfef8a06b80ae6607947923cbcb
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328947"
---
# <a name="cdbvariant-class"></a>CDBVariant-Klasse

Stellt einen varianten Datentyp für die MFC-ODBC-Klassen dar.

## <a name="syntax"></a>Syntax

```
class CDBVariant
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDBVariant::CDBVariant](#cdbvariant)|Erstellt ein `CDBVariant`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDBVariant::Clear](#clear)|Löscht die `CDBVariant` Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDBVariant::m_dwType](#m_dwtype)|Enthält den Datentyp des aktuell gespeicherten Werts an. Geben Sie `DWORD` ein.|

### <a name="public-union-members"></a>Öffentliche Union-Member

|name|Beschreibung|
|----------|-----------------|
|[CDBVariant::m_boolVal](#m_boolval)|Enthält einen Wert vom Typ **"bool"**.|
|[CDBVariant::m_chVal](#m_chval)|Enthält einen Wert vom Typ **unsigned Char**.|
|[CDBVariant::m_dblVal](#m_dblval)|Enthält einen Wert vom Typ **doppelte**.|
|[CDBVariant::m_fltVal](#m_fltval)|Enthält einen Wert vom Typ **"float"**.|
|[CDBVariant::m_iVal](#m_ival)|Enthält einen Wert vom Typ **kurze**.|
|[CDBVariant::m_lVal](#m_lval)|Enthält einen Wert vom Typ **lange**.|
|[CDBVariant::m_pbinary](#m_pbinary)|Enthält einen Zeiger auf ein Objekt des Typs `CLongBinary`.|
|[CDBVariant::m_pdate](#m_pdate)|Enthält einen Zeiger auf ein Objekt des Typs **TIMESTAMP_STRUCT**.|
|[CDBVariant::m_pstring](#m_pstring)|Enthält einen Zeiger auf ein Objekt des Typs `CString`.|
|[CDBVariant::m_pstringA](#m_pstringa)|Speichert einen Zeiger in einen ASCII- [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.|
|[CDBVariant::m_pstringW](#m_pstringw)|Speichert einen Zeiger auf eine Vielzahl [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.|

## <a name="remarks"></a>Hinweise

`CDBVariant` eine Basisklasse keinen.

`CDBVariant` ist vergleichbar mit [COleVariant](../../mfc/reference/colevariant-class.md)jedoch `CDBVariant` OLE wird nicht verwendet. `CDBVariant` ermöglicht es Ihnen, einen Wert zu speichern, ohne sich Gedanken über den Datentyp des Werts zu. `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.

Klasse [CRecordset](../../mfc/reference/crecordset-class.md) nutzt `CDBVariant` Objekte in drei Memberfunktionen: `GetFieldValue`, `GetBookmark`, und `SetBookmark`. Z. B. `GetFieldValue` ermöglicht es Ihnen, Daten in einer Spalte dynamisch abzurufen. Da der Datentyp der Spalte nicht zur Laufzeit bekannt werden möglicherweise `GetFieldValue` verwendet eine `CDBVariant` Objekt, das die Daten der Spalte gespeichert.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CDBVariant`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant

Erstellt ein NULL-Wert `CDBVariant` Objekt.

```
CDBVariant();
```

### <a name="remarks"></a>Hinweise

Legt die [M_dwType](#m_dwtype) Datenmember, DBVT_NULL.

##  <a name="clear"></a>  CDBVariant::Clear

Rufen Sie diese Memberfunktion zum Löschen der `CDBVariant` Objekt.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Wenn der Wert des der [M_dwType](#m_dwtype) -Datenmember ist DBVT_DATE, DBVT_STRING oder DBVT_BINARY, `Clear` der Zeigermember der union zugeordneten Arbeitsspeicher frei. `Clear` Legt `m_dwType` zu DBVT_NULL.

Die `CDBVariant` Destruktoraufrufe `Clear`.

##  <a name="m_boolval"></a>  CDBVariant::m_boolVal

Speichert einen Wert vom Typ "bool".

### <a name="remarks"></a>Hinweise

Die `m_boolVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_boolVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_BOOL, klicken Sie dann `m_boolVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_boolVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_chval"></a>  CDBVariant::m_chVal

Speichert einen Wert vom Typ **unsigned Char**.

### <a name="remarks"></a>Hinweise

Die `m_chVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_chVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_UCHAR, klicken Sie dann `m_chVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_chVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_dblval"></a>  CDBVariant::m_dblVal

Speichert einen Wert vom Typ **doppelte**.

### <a name="remarks"></a>Hinweise

Die `m_dblVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_dblVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_DOUBLE, klicken Sie dann `m_dblVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_dblVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_dwtype"></a>  CDBVariant::m_dwType

Dieses Datenelement enthält den Datentyp für den Wert, der derzeit im gespeichert ist die `CDBVariant` union Datenmember des Objekts.

### <a name="remarks"></a>Hinweise

Vor dem Zugriff auf diese Union, überprüfen Sie den Wert der `m_dwType` um zu ermitteln, welche union-Datenmember auf. Die folgende Tabelle enthält die möglichen Werte für `m_dwType` und die entsprechenden Member der union-Daten.

|m_dwType|Union-Datenmember|
|---------------|-----------------------|
|DBVT_NULL|Keine union-Member ist gültig, für den Zugriff.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

##  <a name="m_fltval"></a>  CDBVariant::m_fltVal

Speichert einen Wert vom Typ **"float"**.

### <a name="remarks"></a>Hinweise

Die `m_fltVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_fltVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_SINGLE, klicken Sie dann `m_fltVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_fltVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_ival"></a>  CDBVariant::m_iVal

Speichert einen Wert vom Typ **kurze**.

### <a name="remarks"></a>Hinweise

Die `m_iVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_iVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_SHORT, klicken Sie dann `m_iVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_iVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_lval"></a>  CDBVariant::m_lVal

Speichert einen Wert vom Typ **lange**.

### <a name="remarks"></a>Hinweise

Die `m_lVal` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_lVal`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_LONG, klicken Sie dann `m_lVal` einen gültigen Wert enthält; andernfalls den Zugriff auf `m_lVal` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary

Speichert einen Zeiger auf ein Objekt des Typs [CLongBinary](../../mfc/reference/clongbinary-class.md).

### <a name="remarks"></a>Hinweise

Die `m_pbinary` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_pbinary`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_BINARY, klicken Sie dann `m_pbinary` enthält einen gültigen Zeiger; andernfalls den Zugriff auf `m_pbinary` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_pdate"></a>  CDBVariant::m_pdate

Ein Zeiger auf ein Objekt des Typs TIMESTAMP_STRUCT gespeichert.

### <a name="remarks"></a>Hinweise

Die `m_pdate` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_pdate`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_DATE, klicken Sie dann `m_pdate` enthält einen gültigen Zeiger; andernfalls den Zugriff auf `m_pdate` wird zu unzuverlässige Ergebnissen führen.

Weitere Informationen zu den TIMESTAMP_STRUCT-Datentyp, finden Sie im Thema [C-Datentypen](/sql/odbc/reference/appendixes/c-data-types) in Anhang D des der *ODBC Programmer's Reference* im Windows SDK.

##  <a name="m_pstring"></a>  CDBVariant::m_pstring

Speichert einen Zeiger auf ein Objekt des Typs [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Hinweise

Die `m_pstring` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_pstring`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_STRING, klicken Sie dann `m_pstring` enthält einen gültigen Zeiger; andernfalls den Zugriff auf `m_pstring` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA

Speichert einen Zeiger in einen ASCII- [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die `m_pstringA` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_pstringA`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_ASTRING, klicken Sie dann `m_pstringA` enthält einen gültigen Zeiger; andernfalls den Zugriff auf `m_pstringA` wird zu unzuverlässige Ergebnissen führen.

##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW

Speichert einen Zeiger auf eine Vielzahl [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die `m_pstringW` -Datenmember auf eine Union gehört. Vor dem Zugriff auf `m_pstringW`, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` nastaven NA hodnotu DBVT_WSTRING, klicken Sie dann `m_pstringW` enthält einen gültigen Zeiger; andernfalls den Zugriff auf `m_pstringW` wird zu unzuverlässige Ergebnissen führen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
