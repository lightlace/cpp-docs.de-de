---
title: CDynamicAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- GetColumnFlags
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
ms.openlocfilehash: 12953da220016c7f66e9a2f01b4b8860d2e508b8
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51557023"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor-Klasse

Können Sie eine Datenquelle zugreifen, wenn Sie keine Kenntnisse über das Datenbankschema (die zugrunde liegende Struktur) verfügen.

## <a name="syntax"></a>Syntax

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>Anforderungen

**Header**: atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[AddBindEntry](#addbindentry)|Fügt einen Eintrag für die Bindung den Ausgabespalten an, beim Überschreiben des Standard-Accessors.|
|[CDynamicAccessor](#cdynamicaccessor)|Instanziiert und initialisiert die `CDynamicAccessor` Objekt.|
|[Schließen](#close)|Hebt die Bindung auf alle Spalten, die den zugeordneten Arbeitsspeicher frei und gibt die [IAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719672(v=vs.85)) Schnittstellenzeiger in der Klasse.|
|[GetBlobHandling](#getblobhandling)|Ruft ab, das BLOB mit dem Wert für die aktuelle Zeile zu verarbeiten.|
|[GetBlobSizeLimit](#getblobsizelimit)|Ruft die maximale BLOB-Größe in Bytes ab.|
|[GetBookmark](#getbookmark)|Ruft das Lesezeichen für die aktuelle Zeile.|
|[GetColumnCount](#getcolumncount)|Ruft die Anzahl der Spalten im Rowset ab.|
|[GetColumnFlags](#getcolumnflags)|Ruft die Spalteneigenschaften ab.|
|[GetColumnInfo](#getcolumninfo)|Ruft die Metadaten ab.|
|[GetColumnName](#getcolumnname)|Ruft den Namen einer angegebenen Spalte ab.|
|[GetColumnType](#getcolumntype)|Ruft den Datentyp einer angegebenen Spalte ab.|
|[GetLength](#getlength)|Ruft die maximal mögliche Länge einer Spalte in Bytes ab.|
|[GetOrdinal](#getordinal)|Ruft den Spaltenindex erhält einen Spaltennamen ab.|
|[GetStatus](#getstatus)|Ruft den Status einer angegebenen Spalte ab.|
|[GetValue](#getvalue)|Ruft die Daten aus dem Puffer ab.|
|[SetBlobHandling](#setblobhandling)|Legt fest, das BLOB mit dem Wert für die aktuelle Zeile zu verarbeiten.|
|[SetBlobSizeLimit](#setblobsizelimit)|Legt die maximale blobgröße in Bytes fest.|
|[SetLength](#setlength)|Legt die Länge der Spalte in Bytes fest.|
|[SetStatus](#setstatus)|Setzt den Status einer angegebenen Spalte.|
|[SetValue](#setvalue)|Speichert die Daten in den Puffer.|

## <a name="remarks"></a>Hinweise

Verwendung `CDynamicAccessor` Methoden zum Abrufen von Informationen wie z. B. Spaltennamen, Spaltenanzahl, Datentyp und So weiter. Können Sie dann diese Spalteninformationen um einen Accessor dynamisch zur Laufzeit zu erstellen.

Die Spalteninformationen wird in einem Puffer gespeichert, die erstellt und verwaltet wird, die von dieser Klasse. Abrufen von Daten aus dem Puffer mithilfe ["GetValue"](../../data/oledb/cdynamicaccessor-getvalue.md).

Ausführliche Informationen und Beispiele für die Verwendung der dynamischen Accessorklassen, finden Sie unter [mithilfe von dynamischen Zugriffsmethoden](../../data/oledb/using-dynamic-accessors.md).

## <a name="addbindentry"></a> CDynamicAccessor:: AddBindEntry

Fügt eine Bindung für den Ausgabespalten.

### <a name="syntax"></a>Syntax

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>Parameter

*Info*<br/>
[in] Ein `DBCOLUMNINFO` Struktur, die Informationen enthält. Finden Sie unter "DBCOLUMNINFO-Strukturen" in [IColumnsInfo:: GetColumnInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms722704(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode beim Überschreiben des Standard-Accessors mit erstellt `CDynamicAccessor` (finden Sie unter [Abrufen von Daten?](../../data/oledb/fetching-data.md)).

## <a name="cdynamicaccessor"></a> CDynamicAccessor:: CDynamicAccessor

Instanziiert und initialisiert die `CDynamicAccessor` Objekt.

### <a name="syntax"></a>Syntax

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>Parameter

*eBlobHandling*<br/>
Gibt an, wie die Daten binary large Object (BLOB) behandelt werden. Der Standardwert ist DBBLOBHANDLING_DEFAULT. Finden Sie unter [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) eine Beschreibung der DBBLOBHANDLINGENUM Werte.

*nBlobSize*<br/>
Die maximale BLOB-Größe in Byte; Spaltendaten über diesen Wert werden als BLOB behandelt. Der Standardwert ist 8000. Finden Sie unter [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Details.

### <a name="remarks"></a>Hinweise

Bei Verwendung den Konstruktor initialisiert die `CDynamicAccessor` Objekt ist, können Sie angeben, wie sie BLOBs gebunden wird. BLOBs können Binärdaten wie Grafiken, Klänge oder kompilierten Code enthalten. Das Standardverhalten ist Spalten mehr als 8.000 Byte als BLOBs behandelt, und versuchen, die sie binden ein `ISequentialStream` Objekt. Allerdings können Sie einen anderen Wert als die BLOB-Größe angeben.

Sie können auch angeben, wie `CDynamicAccessor` verarbeitet die Daten der Spalte, die als BLOB-Daten qualifiziert: kann er auf die Standardweise BLOB-Daten verarbeiten, kann es zu überspringen (nicht gebunden) BLOB-Daten, oder sie können BLOB-Daten im Anbieter reservierten Arbeitsspeicher binden.

## <a name="close"></a> CDynamicAccessor:: Close

Hebt die Bindung auf alle Spalten, die den zugeordneten Arbeitsspeicher frei und gibt die [IAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719672(v=vs.85)) Schnittstellenzeiger in der Klasse.

### <a name="syntax"></a>Syntax

```cpp
void Close() throw();
```

## <a name="getblobhandling"></a> CDynamicAccessor:: Getblobhandling

Ruft ab, das BLOB mit dem Wert für die aktuelle Zeile zu verarbeiten.

### <a name="syntax"></a>Syntax

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>Hinweise

Gibt die BLOB-Wert behandeln *eBlobHandling* entsprechend der Festlegung durch [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md).

## <a name="getblobsizelimit"></a> CDynamicAccessor:: Getblobsizelimit

Ruft die maximale BLOB-Größe in Bytes ab.

### <a name="syntax"></a>Syntax

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>Hinweise

Gibt die BLOB-Wert behandeln *nBlobSize* entsprechend der Festlegung durch [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).

## <a name="getbookmark"></a> CDynamicAccessor:: GetBookmark

Ruft das Lesezeichen für die aktuelle Zeile.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>Parameter

*pBookmark*<br/>
[out] Ein Zeiger auf die [CBookmark](../../data/oledb/cbookmark-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Sie müssen festlegen `DBPROP_IRowsetLocate` auf VARIANT_TRUE fest, um ein Lesezeichen abzurufen.

## <a name="getcolumncount"></a> CDynamicAccessor:: getColumnCount

Ruft die Anzahl der Spalten ab.

### <a name="syntax"></a>Syntax

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Spalten abgerufen werden.

## <a name="getcolumnflags"></a> CDynamicAccessor:: Getcolumnflags

Ruft die Spalteneigenschaften ab.

### <a name="syntax"></a>Syntax

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pFlags*<br/>
[out] Ein Zeiger auf eine Bitmaske, die Spaltenmerkmale beschreibt. Siehe "DBCOLUMNFLAGS Enumerated Type", [IColumnsInfo:: GetColumnInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms722704(v=vs.85)) in die *OLE DB-Programmierreferenz*.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** , wenn die Spalteneigenschaften erfolgreich abgerufen werden. Andernfalls wird **false**zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Nummer der Spalte, die von einem versetzt wird. Die Spalte 0 (null) ist ein Sonderfall; Es ist das Lesezeichen, falls verfügbar.

## <a name="getcolumninfo"></a> CDynamicAccessor:: GetColumnInfo

Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.

### <a name="syntax"></a>Syntax

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>Parameter

*pRowset*<br/>
[in] Ein Zeiger auf die [IRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms720986(v=vs.85)) Schnittstelle.

*pColumns*<br/>
[out] Ein Zeiger auf Speicher, in dem die Anzahl der Spalten im Rowset zurückgegeben werden soll; Diese Anzahl schließt die Lesezeichenspalte ein, sofern vorhanden.

*ppColumnInfo*<br/>
[out] Ein Zeiger auf den Speicher für die Rückgabe ein Array von `DBCOLUMNINFO` Strukturen. Finden Sie unter "DBCOLUMNINFO-Strukturen" in [IColumnsInfo:: GetColumnInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms722704(v=vs.85)) in die *OLE DB-Programmierreferenz*.

*ppStringsBuffer*<br/>
[out] Ein Zeiger auf Speicher, in dem einen Zeiger auf den Speicher für alle Zeichenfolgenwerte zurückgegeben (Namen verwendet, entweder innerhalb *Columnid* oder *PwszName*) innerhalb eines einzelnen zuordnungsblocks.

### <a name="return-value"></a>Rückgabewert

Einer der standardmäßigen HRESULT-Werte.

### <a name="remarks"></a>Hinweise

Finden Sie unter [IColumnsInfo:: GetColumnInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms722704(v=vs.85)) in die *OLE DB-Programmierreferenz* Informationen zu den Datentypen `DBORDINAL`, `DBCOLUMNINFO`, und `OLECHAR`.

## <a name="getcolumnname"></a> CDynamicAccessor:: GetColumnName

Ruft den Namen der angegebenen Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

### <a name="return-value"></a>Rückgabewert

Der Name der angegebenen Spalte.

## <a name="getcolumntype"></a> CDynamicAccessor:: GetColumnType

Ruft den Datentyp einer angegebenen Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*PGeben*<br/>
[out] Ein Zeiger auf den Datentyp der angegebenen Spalte.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.

## <a name="getlength"></a> CDynamicAccessor:: GetLength

Ruft die Länge der angegebenen Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
bool GetLength(DBORDINAL nColumn,
   DBLENGTH* pLength) const throw();

bool GetLength(const CHAR* pColumnName,
   DBLENGTH* pLength) const throw();

bool GetLength(const WCHAR* pColumnName,
   DBLENGTH* pLength) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

*pLength*<br/>
[out] Ein Zeiger auf die ganze Zahl, die die Länge der Spalte in Bytes enthält.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn die angegebene Spalte gefunden wird. Andernfalls, gibt diese Funktion **"false"**.

### <a name="remarks"></a>Hinweise

Beim ersten überschreiben, wird die Nummer der Spalte, und die zweiten und dritten Außerkraftsetzungen werden den Namen der Spalte bzw. im ANSI- oder Unicode-Format.

## <a name="getordinal"></a> CDynamicAccessor:: GetOrdinal

Ruft die Nummer der Spalte erhält einen Spaltennamen ab.

### <a name="syntax"></a>Syntax

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>Parameter

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

*pOrdinal*<br/>
[out] Ein Zeiger auf die Nummer der Spalte.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn eine Spalte mit dem angegebenen Namen gefunden wird. Andernfalls, gibt diese Funktion **"false"**.

## <a name="getstatus"></a> CDynamicAccessor:: GetStatus

Ruft den Status der angegebenen Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
bool GetStatus(DBORDINAL nColumn,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const CHAR* pColumnName,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const WCHAR* pColumnName,
   DBSTATUS* pStatus) const throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

*pStatus*<br/>
[out] Ein Zeiger auf die Variable, die den Status der Spalte enthält. Finden Sie unter [DBSTATUS](https://docs.microsoft.com/previous-versions/windows/desktop/ms722617(v=vs.85)) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn die angegebene Spalte gefunden wird. Andernfalls, gibt diese Funktion **"false"**.

## <a name="getvalue"></a> CDynamicAccessor:: GetValue

Ruft die Daten für eine angegebene Spalte ab.

### <a name="syntax"></a>Syntax

```cpp
void* GetValue(DBORDINAL nColumn) const throw();

void* GetValue(const CHAR* pColumnName) const throw();

void* GetValue(const WCHAR* pColumnName) const throw();

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();

template < class ctype >
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();

template < class ctype >
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();
```

#### <a name="parameters"></a>Parameter

*ctype*<br/>
[in] Auf Vorlagen basierenden Parameter, die einen beliebigen Datentyp aufweisen, mit Ausnahme von Zeichenfolgentypen behandelt (`CHAR*`, `WCHAR*`), die eine spezielle Verarbeitung erfordert. `GetValue` verwendet den entsprechenden Datentyp, der basierend auf was Sie hier angeben.

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*pColumnName*<br/>
[in] Name der Spalte.

*pData*<br/>
[out] Der Zeiger auf den Inhalt der angegebenen Spalte.

### <a name="return-value"></a>Rückgabewert

Wenn Zeichenfolgendaten übergeben werden sollen, verwenden Sie nicht auf Vorlagen basierende Versionen `GetValue`. Die auf Vorlagen basierende Versionen dieser Methode zurückgeben `void*`, das zeigt, der Teil des Puffers, der die angegebene Spaltendaten enthält. Gibt NULL zurück, wenn die Spalte nicht gefunden wird.

Für alle anderen Datentypen, es ist einfacher, die auf Vorlagen basierende Versionen verwenden `GetValue`. Die auf Vorlagen basierende Versionen zurückgeben **"true"** bei Erfolg oder **"false"** bei einem Fehler.

### <a name="remarks"></a>Hinweise

Verwenden Sie nicht auf Vorlagen basierende Versionen, um Spalten zurückzugeben, die Zeichenfolgen und die auf Vorlagen basierende Versionen für Spalten mit anderen Datentypen enthalten.

Im Debugmodus befindet, erhalten Sie eine Assertion, wenn die Größe des *pData* entspricht die Größe der Spalte, die auf den er verweist.

## <a name="setblobhandling"></a> CDynamicAccessor:: Setblobhandling

Legt fest, das BLOB mit dem Wert für die aktuelle Zeile zu verarbeiten.

### <a name="syntax"></a>Syntax

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>Parameter

*eBlobHandling*<br/>
Gibt an, wie die BLOB-Daten behandelt werden. Sie können die folgenden Werte annehmen:

- DBBLOBHANDLING_DEFAULT: Verarbeiten der Spaltendaten ist größer als *nBlobSize* (entsprechend der Festlegung durch `SetBlobSizeLimit`) als BLOB-Daten, und rufen Sie sie über eine `ISequentialStream` oder `IStream` Objekt. Diese Option wird versucht, jede Spalte mit Daten, die größer als binden *nBlobSize* oder als DBTYPE_IUNKNOWN als BLOB-Daten aufgeführt.

- DBBLOBHANDLING_NOSTREAMS: Verarbeiten der Spaltendaten ist größer als *nBlobSize* (entsprechend der Festlegung durch `SetBlobSizeLimit`) als BLOB-Daten und über die Referenz im Anbieter zugeordnet, die Consumer-eigenen Arbeitsspeicher abrufen. Diese Option ist nützlich für Tabellen mit mehr als ein BLOB-Spalte, und der Anbieter unterstützt nur eine `ISequentialStream` Objekt pro Accessor.

- DBBLOBHANDLING_SKIP: Überspringen Sie (nicht gebunden) Spalten, die qualifizierenden BLOBs enthält (der Accessor wird nicht binden oder rufen Sie den Spaltenwert, aber es werden immer noch den Status in der Spalte und die Länge abgerufen).

### <a name="remarks"></a>Hinweise

Sie sollten `SetBlobHandling` vor `Open` aufrufen.

Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt das BLOB mit dem Wert, der DBBLOBHANDLING_DEFAULT behandeln.

## <a name="setblobsizelimit"></a> CDynamicAccessor:: Setblobsizelimit

Legt die maximale blobgröße in Bytes fest.

### <a name="syntax"></a>Syntax

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>Parameter

*nBlobSize*<br/>
Gibt den Grenzwert für die BLOBs an.

### <a name="remarks"></a>Hinweise

Legt die maximale BLOB-Größe in Byte; die Daten der Spalte ist größer als dieser Wert werden als BLOB behandelt. Einige Anbieter bieten extrem große Größen für Spalten (z. B. 2 GB). Anstatt zu versuchen, das belegen von Arbeitsspeicher für eine Spalte dieser Größe, würde in der Regel versucht, diese Spalten als BLOBs zu binden. In auf diese Weise müssen Sie keinen gesamten Arbeitsspeicher zu belegen, aber Sie können weiterhin alle Daten ohne Angst vor der Kürzung lesen. Es gibt jedoch einige Fälle, in dem Sie erzwingen, dass möchten `CDynamicAccessor` große Spalten in deren systemeigenen Datentypen zu binden. Zu diesem Zweck rufen `SetBlobSizeLimit` vor dem Aufruf `Open`.

Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt die maximale BLOB-Größe auf einen Standardwert von 8.000 Bytes.

## <a name="setlength"></a> CDynamicAccessor:: SetLength

Legt die Länge der angegebenen Spalte fest.

### <a name="syntax"></a>Syntax

```cpp
bool SetLength(DBORDINAL nColumn,
   DBLENGTH nLength)throw();

bool SetLength(const CHAR* pColumnName,
   DBLENGTH nLength) throw();

bool SetLength(const WCHAR* pColumnName,
   DBLENGTH nLength) throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*nLength*<br/>
[in] Die Länge der Spalte in Bytes.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn die Länge der angegebenen Spalte erfolgreich festgelegt wurde. Andernfalls, gibt diese Funktion **"false"**.

## <a name="setstatus"></a> CDynamicAccessor:: SetStatus

Setzt den Status der angegebenen Spalte.

### <a name="syntax"></a>Syntax

```cpp
bool SetStatus(DBORDINAL nColumn,
   DBSTATUS status)throw();

bool SetStatus(const CHAR* pColumnName,
   DBSTATUS status) throw();

bool SetStatus(const WCHAR* pColumnName,
   DBSTATUS status) throw();
```

#### <a name="parameters"></a>Parameter

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

*Status*<br/>
[in] Folgender Spaltenstatus. Finden Sie unter [DBSTATUS](https://docs.microsoft.com/previous-versions/windows/desktop/ms722617(v=vs.85)) in die *OLE DB-Programmierreferenz* für Weitere Informationen.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

### <a name="return-value"></a>Rückgabewert

Gibt **"true"** Wenn der Status der angegebenen Spalte erfolgreich festgelegt wurde. Andernfalls, gibt diese Funktion **"false"**.

## <a name="setvalue"></a> CDynamicAccessor:: SetValue

Speichert Daten in einer angegebenen Spalte an.

### <a name="syntax"></a>Syntax

```cpp
template <class ctype>
bool SetValue(
   DBORDINAL nColumn,
   constctype& data) throw( );

template <class ctype> 
bool SetValue(
   const CHAR * pColumnName,
   const ctype& data) throw( );

template <class ctype>
bool SetValue(
   const WCHAR *pColumnName,
   const ctype& data) throw( );
```

#### <a name="parameters"></a>Parameter

*ctype*<br/>
[in] Auf Vorlagen basierenden Parameter, die einen beliebigen Datentyp aufweisen, mit Ausnahme von Zeichenfolgentypen behandelt (`CHAR*`, `WCHAR*`), die eine spezielle Verarbeitung erfordert. `GetValue` verwendet den entsprechenden Datentyp, der basierend auf was Sie hier angeben.

*pColumnName*<br/>
[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.

*data*<br/>
[in] Der Zeiger auf den Arbeitsspeicher, die die Daten enthält.

*nColumn*<br/>
[in] Die Nummer der Spalte. Spaltennummern beginnen bei 1. Ein Wert von 0 verweist auf die Lesezeichenspalte, sofern vorhanden.

### <a name="return-value"></a>Rückgabewert

Wenn Sie die Zeichenfolgendaten festlegen möchten, verwenden Sie nicht auf Vorlagen basierende Versionen `GetValue`. Die auf Vorlagen basierende Versionen dieser Methode zurückgeben `void*`, das zeigt, der Teil des Puffers, der die angegebene Spaltendaten enthält. Gibt NULL zurück, wenn die Spalte nicht gefunden wird.

Für alle anderen Datentypen, es ist einfacher, die auf Vorlagen basierende Versionen verwenden `GetValue`. Die auf Vorlagen basierende Versionen zurückgeben **"true"** bei Erfolg oder **"false"** bei einem Fehler.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor-Klasse](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)