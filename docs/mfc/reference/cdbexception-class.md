---
title: CDBException-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c34c70f1bca3091ba078846b7b94ad947d5f31cb
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083111"
---
# <a name="cdbexception-class"></a>CDBException-Klasse

Stellt eine Ausnahmebedingung dar, die von Datenbankklassen ausgelöst wird.

## <a name="syntax"></a>Syntax

```
class CDBException : public CException
```

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|Enthält einen Rückgabecode des Typs "RETCODE" Open Database Connectivity (ODBC).|
|[CDBException::m_strError](#m_strerror)|Enthält eine Zeichenfolge, die alphanumerische bezüglich der Fehler beschrieben wird.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Enthält eine Zeichenfolge, die Beschreibung des Fehlers in Bezug auf die Fehlercodes, die durch ODBC zurückgegeben wird.|

## <a name="remarks"></a>Hinweise

Die Klasse enthält zwei öffentliche Datenmember, mit denen Sie die Ursache der Ausnahme zu ermitteln oder eine Textnachricht, die Beschreibung der Ausnahme angezeigt. `CDBException` Objekte werden erstellt und von Memberfunktionen von Datenbankklassen ausgelöst.

> [!NOTE]
>  Diese Klasse ist eine der Klassen, MFC Open Database Connectivity (ODBC). Wenn Sie stattdessen die neuere Datenzugriffsobjekte (DAO)-Klassen verwenden, verwenden Sie [CDaoException](../../mfc/reference/cdaoexception-class.md) stattdessen. Alle DAO-Klassennamen ist "CDao" als Präfix. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).

Ausnahmen sind Fälle nicht normale Ausführung, die im Zusammenhang mit Bedingungen, die außerhalb der Steuerung des Programms, wie z. B. Datenquelle oder Netzwerk-e/a-Fehler. Fehler, die Sie möglicherweise während des normalen erwarten für die Ausführung Ihrer Anwendung werden Ausnahmen in der Regel nicht berücksichtigt.

Sie können auf zugreifen, diese Objekte innerhalb des Bereichs einer **CATCH** Ausdruck. Sie können auch auslösen, `CDBException` Objekte über Ihren eigenen Code mit der `AfxThrowDBException` globale Funktion.

Weitere Informationen zur Behandlung von Ausnahmen in allgemeinen oder etwa `CDBException` Objekten finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

##  <a name="m_nretcode"></a>  CDBException::m_nRetCode

Enthält einen ODBC-Fehlercode des Typs "RETCODE", die von einer ODBC-Anwendung programmieren (Interface, API)-Funktion zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Typen fallen breitzeichenliteral mit dem SQL-Codes, die von ODBC definiert und AFX_SQL mit dem Präfix-Codes, die von den Datenbankklassen definiert. Für eine `CDBException`, dieses Element enthält die folgenden Werte:

- AFX_SQL_ERROR_API_CONFORMANCE der Treiber für eine `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC-API-Konformitätsgrad 1 (SQL_OAC_LEVEL1).

- Fehler bei AFX_SQL_ERROR_CONNECT_FAIL-Verbindung mit der Datenquelle. Sie haben einen NULL-Wert übergeben`CDatabase` Zeiger auf Ihre recordsetkonstruktor und dem anschließenden Versuch zum Erstellen einer Verbindung basierend auf `GetDefaultConnect` ist fehlgeschlagen.

- AFX_SQL_ERROR_DATA_TRUNCATED angeforderte mehr Daten als Sie Speicher für angegeben haben. Informationen zum Erhöhen des angegebenen Datenspeicher für `CString` oder `CByteArray` Datentypen finden Sie in der `nMaxLength` Argument für [RFX_Text](record-field-exchange-functions.md#rfx_text) und [RFX_Binary](record-field-exchange-functions.md#rfx_binary) unter "Makros und Globals".

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED ausgelöst ein Aufruf von `CRecordset::Open` anfordern ein Dynaset ist fehlgeschlagen. Dynasets werden vom Treiber nicht unterstützt.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST Sie haben versucht, eine Tabelle zu öffnen (oder was Sie haben nicht gefunden, wie einen Prozeduraufruf oder **wählen** Anweisung), aber es keine Spalten identifiziert Datensatzfeldaustausch Datensatzfeldaustausch (RFX) Funktionsaufrufen in wurden Ihre `DoFieldExchange` außer Kraft setzen.

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH den Typ des einen RFX-Funktion in Ihrer `DoFieldExchange` Außerkraftsetzung ist nicht kompatibel mit den Datentyp der Spalte im Recordset.

- AFX_SQL_ERROR_ILLEGAL_MODE Sie namens `CRecordset::Update` ohne zuvor `CRecordset::AddNew` oder `CRecordset::Edit`.

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED Ihre Anforderung zum Sperren von Datensätzen für das Update konnte nicht ausgeführt werden, weil der ODBC-Treiber Sperren nicht unterstützt.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED Sie namens `CRecordset::Update` oder `Delete` für eine Tabelle ohne eindeutigen Schlüssel und mehrere Datensätze geändert.

- AFX_SQL_ERROR_NO_CURRENT_RECORD Sie versucht, bearbeiten oder Löschen eines zuvor gelöschten Datensatzes. Sie müssen zu einem neuen Datensatz für die aktuelle Scrollen Sie nach dem Löschen.

- Positionierte Updates an AFX_SQL_ERROR_NO_POSITIONED_UPDATES, die Ihre Anforderung für ein Dynaset nicht erfüllt werden konnte, weil der ODBC-Treiber nicht unterstützt.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED Sie namens `CRecordset::Update` oder `Delete`, Beginn des Vorgangs der Datensatz konnte jedoch nicht mehr gefunden werden.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED beim Laden der ODBC. Fehler bei der DLL; Windows konnte nicht gefunden werden oder diese DLL-Datei konnte nicht geladen werden. Dieser Fehler ist schwerwiegend.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED, die Ihre Anforderung für ein Dynaset nicht erfüllt werden konnte, da ein Level 2 konforme ODBC-Treiber erforderlich ist.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY Versuch, einen Bildlauf war nicht erfolgreich, da die Datenquelle Bildlauf rückwärts nicht unterstützt.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED ein Aufruf von `CRecordset::Open` Fehler beim Anfordern einer Momentaufnahme. Momentaufnahmen werden vom Treiber nicht unterstützt. (Dies sollte nur auftreten, wenn die ODBC-Cursorbibliothek ODBCCURS. DLL ist nicht vorhanden.)

- AFX_SQL_ERROR_SQL_CONFORMANCE der Treiber für eine `CDatabase::OpenEx` oder `CDatabase::Open` Aufruf entspricht nicht dem erforderlichen ODBC SQL-Konformitätsgrad "Minimum" (SQL_OSC_MINIMUM).

- AFX_SQL_ERROR_SQL_NO_TOTAL der ODBC-Treiber konnte nicht an die Gesamtgröße des einem `CLongBinary` Datenwert. Vorgangsfehler wahrscheinlich ein globalen Speicherblock nicht vorab zugeordnet werden konnte.

- AFX_SQL_ERROR_RECORDSET_READONLY Sie versucht, ein schreibgeschütztes Recordset zu aktualisieren, oder die Datenquelle ist schreibgeschützt. Keine Updatevorgänge können ausgeführt werden, mit dem Recordset oder `CDatabase` Objekt es zugeordnet ist.

- Fehler bei SQL_ERROR-Funktion. Die Fehlermeldung, die von der ODBC-Funktion zurückgegebene `SQLError` befindet sich in der `m_strError` -Datenmember.

- SQL_INVALID_HANDLE-Funktion, die aufgrund einer ungültigen Umgebungshandle, Verbindungshandle oder Anweisungshandle fehlgeschlagen ist. Dies weist einen Programmierungsfehler hin. Keine zusätzlichen Informationen finden Sie in der ODBC-Funktion `SQLError`.

Die breitzeichenliteral mit dem SQL-Codes werden von ODBC definiert. Die Codes AFX mit dem Präfix sind in AFXDB definiert. H im MFC\INCLUDE gefunden.

##  <a name="m_strerror"></a>  CDBException::m_strError

Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge alphanumerische bezüglich der den Fehler beschreibt. Weitere Informationen und ein Beispiel finden Sie unter `m_strStateNativeOrigin`.

##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin

Enthält eine Zeichenfolge, die Beschreibung des Fehlers, der die Ausnahme verursacht hat.

### <a name="remarks"></a>Hinweise

Die Zeichenfolge weist das Format "Status: % s, Native: % ld, Origin: % s", wobei der Formatcodes, in der Reihenfolge, durch Werte ersetzt werden, in denen beschrieben:

- Der Wert SQLSTATE, eine Null-terminierte Zeichenfolge, die mit einem fünfstelligen Fehlercode zurückgegeben, der *SzSqlState* -Parameter der ODBC-Funktion `SQLError`. SQLSTATE-Werten finden Sie in Anhang A, [ODBC-Fehlercodes](/previous-versions/windows/desktop/ms714687)in die *ODBC Programmer's Reference*. Beispiel: "S0022".

- Der systemeigene Fehlercode für die Datenquelle zurückgegeben wird, der *PfNativeError* Parameter, der die `SQLError` Funktion. Beispiel: 207.

- Der Text der Fehlermeldung zurückgegeben, der *von SQLDiagRec()* Parameter, der die `SQLError` Funktion. Diese Nachricht besteht aus mehreren in Klammern stehenden Namen. Wie Sie ein Fehler aus der Quelle für den Benutzer übergeben wird, fügt jede ODBC-Komponente (Datenquelle, Treiber, Treiber-Manager) einen eigenen Namen an. Diese Informationen helfen, um den Ursprung des Fehlers zu ermitteln. Beispiel: [Microsoft] [ODBC SQL Server-Treiber] [SQLServer]

Das Framework die fehlermeldungs-Zeichenfolge interpretiert und setzt seine Komponenten in `m_strStateNativeOrigin`; Wenn `m_strStateNativeOrigin` enthält Informationen für mehr als einen Fehler, die Fehler werden durch Zeilenumbrüche getrennt. Das Framework legt den alphanumerischen Fehlertext in `m_strError`.

Weitere Informationen zu den Codes verwendet, um diese Zeichenfolge zu erstellen, finden Sie unter den [SQLError](/previous-versions/windows/desktop/ms716312) Funktion in der *ODBC Programmer's Reference*.

### <a name="example"></a>Beispiel

  Aus ODBC: "Status: S0022, Native: 207, Origin: [Microsoft] [ODBC SQL Server Driver] [SQLServer] Ungültiger Spaltenname 'ColName'"

In `m_strStateNativeOrigin`: "Status: S0022, Native: 207, Origin: [Microsoft] [ODBC SQL Server-Treiber] [SQLServer]"

In `m_strError`: "Ungültiger Spaltenname 'ColName'"

## <a name="see-also"></a>Siehe auch

[CException-Klasse](../../mfc/reference/cexception-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange-Klasse](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset:: Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException-Klasse](../../mfc/reference/cexception-class.md)
