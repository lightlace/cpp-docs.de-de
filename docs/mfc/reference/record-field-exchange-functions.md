---
title: Funktionen für den Datensatzfeldaustausch
ms.date: 11/04/2016
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions [MFC]
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions [MFC]
- DFX functions [MFC]
- bulk RFX functions [MFC]
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions [MFC]
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
ms.openlocfilehash: 2970a722f79e9707f8721c1c8595bfd1d133f898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525943"
---
# <a name="record-field-exchange-functions"></a>Funktionen für den Datensatzfeldaustausch

Dieses Thema enthält die Datensatzfeldaustausch (RFX, Bulk-RFX und DFX) verwendet, um die Übertragung von Daten zwischen einem Recordset-Objekt und dessen Datenquelle automatisiert und andere Vorgänge auf die Daten aus Funktionen.

Wenn Sie die ODBC-basierten Klassen verwenden und einen Massenzeilenabruf implementiert haben, müssen Sie die `DoBulkFieldExchange` -Memberfunktion des `CRecordset` manuell überschreiben, indem Sie die Bulk-RFX-Funktionen für jedes Datenelement aufrufen, das einer Datenquellspalte entspricht.

Wenn Sie den Massenzeilenabruf in den ODBC-basierten Klassen implementiert haben oder die DAO-basierten Klassen verwenden, dann überschreibt der ClassWizard die `DoFieldExchange` -Memberfunktion von `CRecordset` oder `CDaoRecordset` durch Aufrufen der RFX-Funktionen (für ODBC-Klassen) oder der DFX-Funktionen (für DAO-Klassen) für jedes Felddatenelement im Recordset.

Die Datensatzfeldaustausch-Funktionen übertragen jedes Mal Daten, wenn das Framework `DoFieldExchange` oder `DoBulkFieldExchange`aufruft. Jede Funktion überträgt einen bestimmten Datentyp.

Weitere Informationen über die Verwendung dieser Funktionen finden Sie in den Artikeln [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Für Datenspalten, die Sie dynamisch binden, können Sie auch die RFX- oder DFX-Funktionen selbst aufrufen, wie in den Artikeln [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)beschrieben. Darüber hinaus können Sie Ihre eigenen benutzerdefinierten RFX- oder DFX-Routinen schreiben, wie im technischen Hinweis [43](../../mfc/tn043-rfx-routines.md) (für ODBC) und im technischen Hinweis [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (für DAO) erläutert.

Für ein Beispiel für RFX und Bulk-RFX-Funktionen wie in der `DoFieldExchange` und `DoBulkFieldExchange` -Funktionen finden Sie unter [RFX_Text](#rfx_text) und die #Rfx_text_bulk [RFX_Text_Bulk]). DFX-Funktionen sind den RFX-Funktionen sehr ähnlich.

### <a name="rfx-functions-odbc"></a>RFX-Funktionen (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|Überträgt Byte-Arrays vom Typ [CByteArray](cbytearray-class.md).|
|[RFX_Bool](#rfx_bool)|Überträgt boolesche Daten.|
|[RFX_Byte](#rfx_byte)|Überträgt ein einzelnes Byte an Daten.|
|[RFX_Date](#rfx_date)|Überträgt Uhrzeit- und Datumsdaten mit [CTime](../../atl-mfc-shared/reference/ctime-class.md) oder TIMESTAMP_STRUCT.|
|[RFX_Double](#rfx_double)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|
|[RFX_Int](#rfx_int)|Überträgt Ganzzahldaten.|
|[RFX_Long](#rfx_long)|Überträgt lange Ganzzahldaten.|
|[RFX_LongBinary](#rfx_longbinary)|Überträgt BLOB-Daten (Binary Large Object) mit einem Objekt der [CLongBinary](clongbinary-class.md) Klasse.|
|[RFX_Single](#rfx_single)|Überträgt Gleitkommadaten.|
|[RFX_Text](#rfx_text)|Überträgt Zeichenfolgendaten.|

### <a name="bulk-rfx-functions-odbc"></a>Bulk-RFX-Funktionen (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Überträgt Arrays von Bytedaten.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Überträgt Arrays von booleschen Daten.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Überträgt Arrays von Einzelbytes.|
|[RFX_Date_Bulk](#rfx_date_bulk)|Überträgt Arrays von Daten des Typs TIMESTAMP_STRUCT.|
|[RFX_Double_Bulk](#rfx_double_bulk)|Überträgt Arrays von Gleitkommadaten mit doppelter Genauigkeit.|
|[RFX_Int_Bulk](#rfx_int_bulk)|Überträgt Arrays von Ganzzahldaten.|
|[RFX_Long_Bulk](#rfx_long_bulk)|Überträgt Arrays von langen Ganzzahldaten.|
|[RFX_Single_Bulk](#rfx_single_bulk)|Überträgt Arrays von Gleitkommadaten.|
|[RFX_Text_Bulk](#rfx_text_bulk)|Überträgt Arrays von Daten des Typs LPSTR.|

### <a name="dfx-functions-dao"></a>DFX-Funktionen (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|Überträgt Byte-Arrays vom Typ [CByteArray](cbytearray-class.md).|
|[DFX_Bool](#dfx_bool)|Überträgt boolesche Daten.|
|[DFX_Byte](#dfx_byte)|Überträgt ein einzelnes Byte an Daten.|
|[DFX_Currency](#dfx_currency)|Überträgt Währungsdaten vom Typ [COleCurrency](colecurrency-class.md).|
|[DFX_DateTime](#dfx_datetime)|Überträgt Datums- und Uhrzeitdaten vom Typ [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|
|[DFX_Double](#dfx_double)|Überträgt Gleitkommazahl mit doppelter Genauigkeit.|
|[DFX_Long](#dfx_long)|Überträgt lange Ganzzahldaten.|
|[DFX_LongBinary](#dfx_longbinary)|Überträgt BLOB-Daten (Binary Large Object) mit einem Objekt der `CLongBinary` -Klasse. Bei DAO wird empfohlen, dass Sie stattdessen [DFX_Binary](#dfx_binary) verwenden.|
|[DFX_Short](#dfx_short)|Überträgt kurze Ganzzahldaten.|
|[DFX_Single](#dfx_single)|Überträgt Gleitkommadaten.|
|[DFX_Text](#dfx_text)|Überträgt Zeichenfolgendaten.|

=============================================

## <a name="rfx_binary"></a>  RFX_Binary

Überträgt Arrays von Bytes zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_BINARY, SQL_VARBINARY oder SQL_LONGVARBINARY.

### <a name="syntax"></a>Syntax

```
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*nMaxLength*<br/>
Die maximal zulässige Länge der Zeichenfolge oder Array übertragen werden. Der Standardwert von *nMaxLength* ist 255. Zulässige Werte sind 1 bis INT_MAX. Das Framework ordnet diese Menge an Speicherplatz für die Daten an. Übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, für eine optimale Leistung.

### <a name="remarks"></a>Hinweise

Daten in die Datenquelle dieser Typen zugeordnet ist, und vom Typ `CByteArray` im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_bool"></a>  RFX_Bool

Überträgt boolesche Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_BIT.

### <a name="syntax"></a>Syntax

```
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für eine Übertragung vom Recordset die Datenquelle wird der Wert vom Typ "bool", den angegebenen Datenmember entnommen. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_byte"></a>  RFX_Byte

Übertragungen einmaliges Bytes zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_TINYINT.

### <a name="syntax"></a>Syntax

```
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für eine Übertragung vom Recordset die Datenquelle wird der Wert, der Typ "BYTE", den angegebenen Datenmember entnommen. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_date"></a>  RFX_Date

Übertragungen `CTime` oder TIMESTAMP_STRUCT Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle von ODBC zu geben, SQL_DATE, SQL_TIME oder SQL_TIMESTAMP.

### <a name="syntax"></a>Syntax

```
void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   CTime& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   TIMESTAMP_STRUCT& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   COleDateTime& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Der Wert, der in den angegebenen Datenmember gespeichert; der Wert, der übertragen werden. Die verschiedenen Versionen der Funktion führen Sie unterschiedliche Datentypen für Wert:

Die erste Version der Funktion akzeptiert einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt. Für eine Übertragung vom Recordset die Datenquelle wird der Wert aus den angegebenen Datenmember verwendet. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

Die zweite Version der Funktion akzeptiert einen Verweis auf eine `TIMESTAMP_STRUCT` Struktur. Sie müssen diese Struktur selbst vor dem Aufruf einrichten. Unterstützt weder Dialogdatenaustausch (DDX) und Code-Assistenten-Unterstützung ist für diese Version verfügbar. Die dritte Version der Funktion funktioniert ähnlich wie auf die erste Version, außer dass es sich um einen Verweis auf verwendet eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die `CTime` Version der Funktion erzwingt den Aufwand für fortgeschrittene verarbeitet und umfasst maximal begrenzt. Wenn Sie eine der folgenden Faktoren ab, zu beschränken finden, verwenden Sie die zweite Version der Funktion. Beachten Sie jedoch das Fehlen des Code-Assistenten und DDX-Unterstützung und die Anforderung, die Sie der Struktur selbst eingerichtet.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_double"></a>  RFX_Double

Übertragungen **vom Typ double Float** Daten zwischen den Felddatenmembern eine `CRecordset` Geben Sie-Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC SQL_DOUBLE.

### <a name="syntax"></a>Syntax

```
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_int"></a>  RFX_Int

Überträgt Ganzzahldaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_SMALLINT.

### <a name="syntax"></a>Syntax

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **Int**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_long"></a>  RFX_Long

Überträgt long integer-Wert-Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_INTEGER.

### <a name="syntax"></a>Syntax

```
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **lange**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_longbinary"></a>  RFX_LongBinary

Überträgt Daten binary large Object (BLOB), die mit Klasse [CLongBinary](clongbinary-class.md) zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle von ODBC, geben Sie SQL_LONGVARBINARY oder SQL_LONGVARCHAR.

### <a name="syntax"></a>Syntax

```
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs `CLongBinary`, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_single"></a>  RFX_Single

Überträgt Gleitkommadaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_REAL.

### <a name="syntax"></a>Syntax

```
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **"float"**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_text"></a>  RFX_Text

Übertragungen `CString` Daten zwischen den Felddatenmembern eine `CRecordset` -Objekt und Spalten eines Datensatzes für die Datenquelle von ODBC zu geben, SQL_LONGVARCHAR SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL oder SQL_NUMERIC.

### <a name="syntax"></a>Syntax

```
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse `CFieldExchange`. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs `CString`, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*nMaxLength*<br/>
Die maximal zulässige Länge der Zeichenfolge oder Array übertragen werden. Der Standardwert von *nMaxLength* ist 255. Zulässige Werte sind 1 bis INT_MAX). Das Framework ordnet diese Menge an Speicherplatz für die Daten an. Übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, für eine optimale Leistung.

*nColumnType*<br/>
Wird hauptsächlich für Parameter verwendet. Eine ganze Zahl, die den Datentyp des Parameters angibt. Der Typ ist ein ODBC-Datentyp des Formulars **SQL_XXX**.

*nScale*<br/>
Gibt die Dezimalstellen für Werte vom ODBC-Typ SQL_DECIMAL oder SQL_NUMERIC an. *nScale* ist nur nützlich, wenn Parameterwerte festlegen. Weitere Informationen finden Sie im Thema "Genauigkeit, Dezimalstellen, Länge und Größe" in Anhang D des der *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Daten in der Datenquelle für alle diese Typen zugeordnet ist, in und aus `CString` im Recordset.

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt mehrere Aufrufe `RFX_Text`. Beachten Sie auch die beiden Aufrufe von `CFieldExchange::SetFieldType`. Für Parameter müssen Sie den Aufruf schreiben `SetFieldType` und den RFX-Aufruf abgeschlossen. Der Aufruf der Ausgabe-Spalte und die zugehörigen RFX-Aufrufe werden normalerweise von einem Code-Assistenten geschrieben.

```cpp
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_binary_bulk"></a>  RFX_Binary_Bulk

Überträgt Sie mehrere Zeilen mit Byte-Daten aus einer Spalte mit einer ODBC-Datenquelle an einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgByteVals*<br/>
Ein Zeiger auf ein Array von Bytewerten. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgByteVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

*nMaxLength*<br/>
Die maximal zulässige Länge der Werte im Array verweist gespeicherten *PrgByteVals*. Übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, um sicherzustellen dass Daten nicht abgeschnitten werden.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte haben einen ODBC-Typ SQL_BINARY, SQL_VARBINARY oder SQL_LONGVARBINARY. Das Recordset muss einen Feld-Datenmember des Typs Zeiger auf BYTE definieren.

Wenn Sie initialisieren *PrgByteVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk

Mehrere Zeilen von booleschen Daten aus einer Spalte mit einer ODBC-Datenquelle übertragen, um einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgBoolVals*<br/>
Ein Zeiger auf ein Array von Werten für "bool". Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgBoolVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte muss einen ODBC-Typ SQL_BIT haben. Das Recordset muss einen Feld-Datenmember des Typs Zeiger in einen booleschen Wert definieren.

Wenn Sie initialisieren *PrgBoolVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk

Mehrere Zeilen von einzelbytes aus einer Spalte mit einer ODBC-Datenquelle übertragen, um einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgByteVals*<br/>
Ein Zeiger auf ein Array von Bytewerten. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgByteVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte muss einen ODBC-Typ SQL_TINYINT haben. Das Recordset muss einen Feld-Datenmember des Typs Zeiger auf BYTE definieren.

Wenn Sie initialisieren *PrgByteVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk

Übertragen mehrerer TIMESTAMP_STRUCT Datenzeilen aus einer Spalte mit einer ODBC-Datenquelle in einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgTSVals*<br/>
Ein Zeiger auf ein Array von TIMESTAMP_STRUCT-Werten. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen. Weitere Informationen zu den TIMESTAMP_STRUCT-Datentyp, finden Sie im Thema "C-Datentypen" in Anhang D des der *ODBC SDK-Programmierreferenz*.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgTSVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte haben einen ODBC-Datentyp, SQL_DATE, SQL_TIME oder SQL_TIMESTAMP. Das Recordset muss einen Feld-Datenmember des Typs Zeiger zu TIMESTAMP_STRUCT definieren.

Wenn Sie initialisieren *PrgTSVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk

Übertragen mehrerer Datenzeilen mit doppelter Genauigkeit, Gleitkomma aus einer Spalte mit einer ODBC-Datenquelle in einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgDblVals*<br/>
Ein Zeiger auf ein Array von **doppelte** Werte. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgDblVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte muss einen Typ ODBC SQL_DOUBLE haben. Das Recordset muss einen Feld-Datenmember des Typs Zeiger zu definieren **doppelte**.

Wenn Sie initialisieren *PrgDblVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_int_bulk"></a>  RFX_Int_Bulk

Überträgt Ganzzahldaten zwischen den Felddatenmembern eine `CRecordset` -Objekt und die Spalten eines Datensatzes für die Datenquelle des ODBC-Typ SQL_SMALLINT.

### <a name="syntax"></a>Syntax

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CFieldExchange](cfieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen zu den Vorgängen eine `CFieldExchange` Objekt angeben kann, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **Int**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text](#rfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk

Übertragen mehrerer Datenzeilen long integer-Wert aus einer Spalte mit einer ODBC-Datenquelle in einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgLongVals*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgLongVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte muss einen ODBC-Typ SQL_INTEGER haben. Das Recordset muss einen Feld-Datenmember des Typs Zeiger zu definieren **lange**.

Wenn Sie initialisieren *PrgLongVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk

Übertragen mehrerer Gleitkomma Datenzeilen aus einer Spalte mit einer ODBC-Datenquelle in einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgFltVals*<br/>
Ein Zeiger auf ein Array von **"float"** Werte. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgFltVals*. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte muss einen ODBC-Typ SQL_REAL haben. Das Recordset muss einen Feld-Datenmember des Typs Zeiger zu definieren **"float"**.

Wenn Sie initialisieren *PrgFltVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Finden Sie unter [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk

Überträgt Sie mehrere Zeilen mit Daten aus einer Spalte mit einer ODBC-Datenquelle an einen entsprechenden Array in eine `CRecordset`-abgeleitetes Objekt.

### <a name="syntax"></a>Syntax

```
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](cfieldexchange-class.md) Objekt. Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren. Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Der Name einer Datenspalte.

*prgStrVals*<br/>
Ein Zeiger auf ein Array von LPSTR-Werten. Dieses Array speichert die Daten aus der Datenquelle, die auf das Recordset übertragen werden sollen. Beachten Sie, dass mit der aktuellen Version von ODBC, diese Werte nicht Unicode.

*prgLengths*<br/>
Ein Zeiger auf ein Array von langen ganzen Zahlen. Dieses Array speichert die Länge in Bytes der jeden Wert in das Array verweist *PrgStrVals*. Diese Länge schließt abschließendes null-Zeichen. Beachten Sie, dass der Wert SQL_NULL_DATA gespeichert, wenn das entsprechende Datenelement einen Nullwert enthält. Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLBindCol` in die *ODBC SDK-Programmierreferenz*.

*nMaxLength*<br/>
Die maximal zulässige Länge der Werte im Array verweist gespeicherten *PrgStrVals*, einschließlich des Zeichens null-Terminierung. Übergeben Sie einen Wert, der groß genug für das größte Datenelement, die, das Sie erwarten, um sicherzustellen dass Daten nicht abgeschnitten werden.

### <a name="remarks"></a>Hinweise

Die Datenquellenspalte haben einen ODBC-Datentyp SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL oder SQL_NUMERIC. Das Recordset muss es sich um ein Feld-Datenmember vom Typ LPSTR definieren.

Wenn Sie initialisieren *PrgStrVals* und *PrgLengths* auf NULL, und klicken Sie dann die Arrays, die beide zeigen auf Größen entspricht der Rowsetgröße automatisch zugeordnet werden.

> [!NOTE]
>  Massenaustausch überträgt Daten aus der Datenquelle nur zum Recordset-Objekt. Um das Recordset aktualisierbar zu machen, müssen Sie mithilfe der ODBC-API-Funktion `SQLSetPos`.

Weitere Informationen finden Sie in den Artikeln [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Beispiel

Sie müssen manuell Aufrufe schreiben, Ihre `DoBulkFieldExchange` außer Kraft setzen. Dieses Beispiel zeigt einen Aufruf von `RFX_Text_Bulk`, sowie der Aufruf von `RFX_Long_Bulk`, für die Datenübertragung. Diese Aufrufe werden durch einen Aufruf von vorangestellt [CFieldExchange::](CFieldExchange::SetFieldType.md). Beachten Sie, dass für Parameter, die RFX-Funktionen, anstatt die Bulk-RFX-Funktionen aufgerufen werden muss.

```cpp
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

## <a name="dfx_binary"></a>  DFX_Binary

Überträgt Arrays von Bytes zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs [CByteArray](cbytearray-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*nPreAllocSize*<br/>
Das Framework belegt Systemspeicher. Wenn Ihre Daten größer ist, wird das Framework mit dem mehr Speicherplatz nach Bedarf zugeordnet. Legen Sie diese Größe auf einen Wert, der groß genug, um zu verhindern, dass neuzuordnungen, zur Verbesserung der Leistung. Die Standardgröße ist in der AFXDAO definiert. H-Datei als AFX_DAO_BINARY_DEFAULT_SIZE.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Die Standardeinstellung AFX_DAO_DISABLE_FIELD_CACHE, verwendet nicht die doppelte Pufferung, und rufen Sie [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst. Der andere mögliche Wert, AFX_DAO_ENABLE_FIELD_CACHE, verwendet die doppelte Pufferung, und Sie müssen keine zusätzliche Arbeit, um Felder zu kennzeichnen sind geändert oder "Null". Vermeiden Sie für Gründen der Leistung und Arbeitsspeicher diesen Wert, es sei denn, Ihre binäre Daten relativ klein ist.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte wird durch die Einstellung für alle Felder standardmäßig gepuffert [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_BYTES über DAO und Typ zugeordnet [CByteArray](cbytearray-class.md) im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_bool"></a>  DFX_Bool

Überträgt boolesche Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für eine Übertragung vom Recordset die Datenquelle wird der Wert vom Typ "bool", den angegebenen Datenmember entnommen. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_BOOL über DAO und Typ "bool" im Recordset zugeordnet.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_byte"></a>  DFX_Byte

Übertragungen einmaliges Bytes zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für eine Übertragung vom Recordset die Datenquelle wird der Wert, der Typ "BYTE", den angegebenen Datenmember entnommen. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_BYTES über DAO und Typ BYTE im Recordset zugeordnet.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_currency"></a>  DFX_Currency

Überträgt Währungsdaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Dieser Wert stammt für eine Übertragung vom Recordset die Datenquelle, aus den angegebenen Datenmember vom Typ [COleCurrency](colecurrency-class.md). Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_CURRENCY über DAO und Typ zugeordnet [COleCurrency](colecurrency-class.md) im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_datetime"></a>  DFX_DateTime

Überträgt Datums- und Uhrzeitdaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Die Funktion akzeptiert einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt. Für eine Übertragung vom Recordset die Datenquelle wird der Wert aus den angegebenen Datenmember verwendet. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_DATE über DAO und Typ zugeordnet [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) im Recordset.

> [!NOTE]
>  `COleDateTime` ersetzt [CTime](../../atl-mfc-shared/reference/ctime-class.md) und TIMESTAMP_STRUCT zu diesem Zweck in den DAO-Klassen. `CTime` und TIMESTAMP_STRUCT weiterhin für die ODBC-basierten Data Access-Klassen verwendet werden.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_double"></a>  DFX_Double

Übertragungen **vom Typ double Float** Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **doppelte**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_R8 über DAO und Typ zugeordnet **vom Typ double Float** im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_long"></a>  DFX_Long

Überträgt long integer-Wert-Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **lange**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_I4 über DAO und Typ zugeordnet **lange** im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_longbinary"></a>  DFX_LongBinary

**Wichtige** es wird empfohlen, die Verwendung von [DFX_Binary](#dfx_binary) anstatt dieser Funktion.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs [CLongBinary](clongbinary-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwPreAllocSize*<br/>
Das Framework belegt Systemspeicher. Wenn Ihre Daten größer ist, wird das Framework mit dem mehr Speicherplatz nach Bedarf zugeordnet. Legen Sie diese Größe auf einen Wert, der groß genug, um zu verhindern, dass neuzuordnungen, zur Verbesserung der Leistung.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Der Standardwert, AFX_DISABLE_FIELD_CACHE, die doppelte Pufferung wird nicht verwendet werden. Der andere mögliche Wert ist AFX_DAO_ENABLE_FIELD_CACHE. Verwendet doppelte Pufferung, und Sie müssen keine ist zusätzlichen Schritte, um Felder kennzeichnen, geändert oder "Null". Vermeiden Sie für Gründen der Leistung und Arbeitsspeicher diesen Wert, es sei denn, Ihre binäre Daten relativ klein ist.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

`DFX_LongBinary` wird für die Kompatibilität mit den MFC-ODBC-Klassen bereitgestellt werden. Die `DFX_LongBinary` Funktion überträgt, binary large-Object (BLOB)-Daten mithilfe der Klasse `CLongBinary` zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle. Daten werden zwischen DAO_BYTES über DAO und Typ zugeordnet [CLongBinary](clongbinary-class.md) im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_short"></a>  DFX_Short

Überträgt kurze Ganzzahldaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **kurze**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_I2 über DAO und Typ zugeordnet **kurze** im Recordset.

> [!NOTE]
>  `DFX_Short` entspricht dem [RFX_Int](#rfx_int) für die ODBC-basierten Klassen.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_single"></a>  DFX_Single

Überträgt Gleitkommadaten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und die Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs **"float"**, stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen DAO_R4 über DAO und Typ zugeordnet **"float"** im Recordset.

### <a name="example"></a>Beispiel

Finden Sie unter [DFX_Text](#dfx_text).

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="dfx_text"></a>  DFX_Text

Übertragungen `CString` Daten zwischen den Felddatenmembern eine [CDaoRecordset](cdaorecordset-class.md) -Objekt und Spalten eines Datensatzes in der Datenquelle.

### <a name="syntax"></a>Syntax

```
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf ein Objekt der Klasse [CDaoFieldExchange](cdaofieldexchange-class.md). Dieses Objekt enthält Informationen, die den Kontext für jeden Aufruf der Funktion definieren.

*szName*<br/>
Der Name einer Datenspalte.

*Wert*<br/>
Die in den angegebenen Datenmember gespeicherten Wert, der Wert, der übertragen werden. Für die Übertragung vom Recordset zu Datenquelle, die den Wert des Typs [CString](../../atl-mfc-shared/reference/cstringt-class.md), stammt aus den angegebenen Datenmember. Für die Übertragung aus der Datenquelle zum Recordset wird der Wert in den angegebenen Datenmember gespeichert.

*nPreAllocSize*<br/>
Das Framework belegt Systemspeicher. Wenn Ihre Daten größer ist, wird das Framework mit dem mehr Speicherplatz nach Bedarf zugeordnet. Legen Sie diese Größe auf einen Wert, der groß genug, um zu verhindern, dass neuzuordnungen, zur Verbesserung der Leistung.

*dwBindOptions*<br/>
Eine Option, mit der Sie profitieren Sie von MFC doppelte Pufferung Mechanismus zum Erkennen von Recordset-Feldern, die geändert wurden. Standard, AFX_DAO_ENABLE_FIELD_CACHE, wird die doppelte Pufferung verwendet. Der andere mögliche Wert ist AFX_DAO_DISABLE_FIELD_CACHE. Wenn Sie diesen Wert angeben, wird MFC keine Überprüfung für dieses Feld. Rufen Sie [SetFieldDirty](cdaorecordset-class.md#setfielddirty) und [SetFieldNull](cdaorecordset-class.md#setfieldnull) selbst.

> [!NOTE]
>  Sie können steuern, ob Daten doppelte standardmäßig gepuffert werden wird, durch Festlegen von [CDaoRecordset:: M_bcheckcachefordirtyfields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Hinweise

Daten werden zwischen den DAO_CHAR in-DAO-zugeordnet (oder, wenn _UNICODE definiert wird, DAO_WCHAR aus), und geben [CString](../../atl-mfc-shared/reference/cstringt-class.md) im Recordset.  n

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt mehrere Aufrufe `DFX_Text`. Beachten Sie auch die beiden Aufrufe von [CDaoFieldExchange:: SetFieldType](cdaofieldexchange-class.md#setfieldtype). Sie müssen der erste Aufruf schreiben `SetFieldType` und die zugehörige **DFX** aufrufen. Der zweite Aufruf und die zugehörigen **DFX** Aufrufe werden normalerweise durch den Code-Assistenten, die die Klasse generiert geschrieben.

```cpp
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[CRecordset:: DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset:: DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

