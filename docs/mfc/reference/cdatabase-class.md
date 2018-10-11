---
title: CDatabase-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
dev_langs:
- C++
helpviewer_keywords:
- CDatabase [MFC], CDatabase
- CDatabase [MFC], BeginTrans
- CDatabase [MFC], BindParameters
- CDatabase [MFC], Cancel
- CDatabase [MFC], CanTransact
- CDatabase [MFC], CanUpdate
- CDatabase [MFC], Close
- CDatabase [MFC], CommitTrans
- CDatabase [MFC], ExecuteSQL
- CDatabase [MFC], GetBookmarkPersistence
- CDatabase [MFC], GetConnect
- CDatabase [MFC], GetCursorCommitBehavior
- CDatabase [MFC], GetCursorRollbackBehavior
- CDatabase [MFC], GetDatabaseName
- CDatabase [MFC], IsOpen
- CDatabase [MFC], OnSetOptions
- CDatabase [MFC], Open
- CDatabase [MFC], OpenEx
- CDatabase [MFC], Rollback
- CDatabase [MFC], SetLoginTimeout
- CDatabase [MFC], SetQueryTimeout
- CDatabase [MFC], m_hdbc
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1e050baf87374b98d5490ef8a760ca13620e240
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083930"
---
# <a name="cdatabase-class"></a>CDatabase-Klasse

Stellt eine Verbindung mit einer Datenquelle dar, über welche die Datenquelle bearbeitet werden kann.

## <a name="syntax"></a>Syntax

```
class CDatabase : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDatabase::CDatabase](#cdatabase)|Erstellt ein `CDatabase`-Objekt. Sie müssen das Objekt initialisieren, durch den Aufruf `OpenEx` oder `Open`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDatabase::BeginTrans](#begintrans)|Startet eine "Transaktion" – eine Reihe von rückgängig gemacht werden Aufrufe an die `AddNew`, `Edit`, `Delete`, und `Update` Memberfunktionen der Klasse `CRecordset` – auf der verbundenen Datenquelle. Die Datenquelle muss Unterstützung für Transaktionen für `BeginTrans` eine Auswirkung hat.|
|[CDatabase::BindParameters](#bindparameters)|Ermöglicht das Binden von Parametern vor dem Aufruf `CDatabase::ExecuteSQL`.|
|[CDatabase::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess aus einem zweiten Thread ab.|
|[CDatabase::CanTransact](#cantransact)|Gibt, die ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|
|[CDatabase::CanUpdate](#canupdate)|Ungleich NULL zurück, wenn die `CDatabase` Objekt kann aktualisiert werden (nicht schreibgeschützt).|
|[CDatabase::Close](#close)|Schließen die datenquellenverbindung ein.|
|[CDatabase:: CommitTrans](#committrans)|Schließt eine Transaktion gestartet wird, indem `BeginTrans`. Befehle in der Transaktion, ändern die Datenquelle, ausgeführt werden.|
|[CDatabase:: ExecuteSQL aufgerufen](#executesql)|Führt eine SQL­Anweisung. Es werden keine Datensätze zurückgegeben.|
|[CDatabase:: GetBookmarkPersistence](#getbookmarkpersistence)|Identifiziert die Vorgänge, die über denen Lesezeichen auf Recordset-Objekte beibehalten werden.|
|[CDatabase:: Getconnect](#getconnect)|Gibt zurück, die ODBC-Verbindungszeichenfolge, die zur Verbindung der `CDatabase` Objekt mit einer Datenquelle.|
|[GetCursorCommitBehavior](#getcursorcommitbehavior)|Identifiziert die Auswirkungen der Commit einer Transaktion in einem geöffneten Recordsetobjekt.|
|[Rollback](#getcursorrollbackbehavior)|Identifiziert die Auswirkungen des Rollbacks einer Transaktion in einem geöffneten Recordsetobjekt.|
|[CDatabase::GetDatabaseName](#getdatabasename)|Gibt den Namen der Datenbank, die zurzeit verwendeten zurück.|
|[CDatabase::IsOpen](#isopen)|Ungleich NULL zurück, wenn die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.|
|[CDatabase::OnSetOptions](#onsetoptions)|Wird aufgerufen, durch das Festlegen von Verbindungsoptionen für standard-Framework. Die standardmäßige Implementierung legt den Timeoutwert für Abfragen fest. Sie können diese Optionen voraus einrichten, durch den Aufruf `SetQueryTimeout`.|
|[CDatabase:: Open](#open)|Herstellen einer Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|
|[CDatabase:: OpenEx](#openex)|Herstellen einer Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|
|[CDatabase](#rollback)|Kehrt die während der aktuellen Transaktion vorgenommene Änderungen. Gibt die Datenquelle den ursprünglichen Zustand, zur definiert die `BeginTrans` Aufruf unverändert.|
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden nach dem ein Data Source-Verbindungsversuch tritt ein Timeout fest.|
|[CDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge Abfragen tritt ein Timeout. Wirkt sich auf alle nachfolgenden Recordset `Open`, `AddNew`, `Edit`, und `Delete` aufrufen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDatabase:: M_hdbc](#m_hdbc)|Open Database Connectivity (ODBC)-Verbindungshandle mit einer Datenquelle. Typ *HDBC*.|

## <a name="remarks"></a>Hinweise

Eine Datenquelle ist eine bestimmte Instanz der Daten, die von einigen Datenbank-Managementsystem (DBMS) gehostet wird. Beispiele sind Microsoft SQL Server, Microsoft Access, Borland dBASE und xBASE. Sie haben eine oder mehrere `CDatabase` Objekte, die aktiv in Ihrer Anwendung.

> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt mit der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).

Verwenden `CDatabase`, erstellen Sie eine `CDatabase` Objekt, und rufen die `OpenEx` Member-Funktion. Dadurch wird eine Verbindung geöffnet. Wenn Sie sich dann erstellen `CRecordset` Objekte für den Betrieb in der verbundenen Datenquelle, dem recordsetkonstruktor übergeben Sie einen Zeiger auf Ihre `CDatabase` Objekt. Wenn Sie fertig sind, verwenden die Verbindung, rufen Sie die `Close` Member funktioniert und zerstört der `CDatabase` Objekt. `Close` Schließt alle Recordsets, die Sie nicht bereits geschlossen haben.

Weitere Informationen zu `CDatabase`, finden Sie in den Artikeln [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md) und [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

##  <a name="begintrans"></a>  CDatabase::BeginTrans

Rufen Sie diese Memberfunktion zum Starten einer Transaktions mit der verbundenen Datenquelle.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Aufruf erfolgreich war, und Änderungen manuell nur ausgeführt werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Transaktion besteht aus einem oder mehreren Aufrufen an die `AddNew`, `Edit`, `Delete`, und `Update` Memberfunktionen von einem `CRecordset` Objekt. Vor Beginn einer Transaktions, die `CDatabase` Objekt muss bereits angeschlossen wurden mit der Datenquelle durch Aufrufen der `OpenEx` oder `Open` Member-Funktion. Um die Transaktion zu beenden, rufen [CommitTrans](#committrans) akzeptiert alle Änderungen an der Datenquelle (und führen sie Sie), oder rufen Sie [Rollback](#rollback) die gesamte Transaktion abgebrochen. Rufen Sie `BeginTrans` Nachdem Sie alle Recordsets, die an der Transaktion beteiligten öffnen und als in der Nähe des tatsächlichen update-Vorgänge wie möglich.

> [!CAUTION]
>  Je nach ODBC-Treibers zum Öffnen eines Recordsets vor dem Aufruf `BeginTrans` kann Probleme verursachen, beim Aufrufen von `Rollback`. Überprüfen Sie den jeweiligen Treiber, die, den Sie verwenden. Beispielsweise müssen bei Verwendung der Microsoft Access-Treiber, die in der Microsoft ODBC Desktop Driver Pack 3.0 enthalten Sie für die Jet-Datenbank-Engine die Anforderungen berücksichtigen, dass Sie keine Transaktion für eine beliebige Datenbank beginnen sollte, die einen geöffneten Cursor enthält. In den MFC-Datenbankklassen bedeutet ein geöffneten Cursor ein offenes `CRecordset` Objekt. Weitere Informationen finden Sie unter [technischen Hinweis 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).

`BeginTrans` Datensätze können auch auf dem Server, abhängig von der angeforderten Parallelität und die Funktionen von der Datenquelle Sperren werden. Informationen zum Sperren von Daten finden Sie im Artikel [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

Benutzerdefinierte Transaktionen werden in diesem Artikel erläutert [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

`BeginTrans` Legt den Zustand, der die Reihenfolge der Transaktionen kann Rollback (rückgängig gemacht). Übernehmen Sie alle aktuellen Transaktionen, um einen neuen Zustand für Rollbacks einzurichten, rufen Sie anschließend `BeginTrans` erneut aus.

> [!CAUTION]
>  Aufrufen von `BeginTrans` erneut ohne `CommitTrans` oder `Rollback` ein Fehler auftritt.

Rufen Sie die [CanTransact](#cantransact) Memberfunktion, um zu bestimmen, ob der Treiber die Transaktionen für eine bestimmte Datenbank unterstützt. Sie sollten auch aufrufen [GetCursorCommitBehavior](#getcursorcommitbehavior) und [GetCursorRollbackBehavior](#getcursorrollbackbehavior) um zu bestimmen, die Unterstützung für die Beibehaltung von Cursors.

Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Beispiel

  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="bindparameters"></a>  CDatabase::BindParameters

Außer Kraft setzen `BindParameters` müssen Sie die Parameter vor dem Aufruf zu binden [CDatabase:: ExecuteSQL](#executesql).

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>Parameter

*Befehls beschäftigt*<br/>
Das ODBC-Anweisungshandle, der für das Parameter gebunden werden sollen.

### <a name="remarks"></a>Hinweise

Dieser Ansatz ist hilfreich, wenn Sie nicht, dass das Ergebnis benötigen aus einer gespeicherten Prozedur festgelegt.

Rufen Sie in der Außerkraftsetzung `SQLBindParameters` und zugehörigen ODBC-Funktionen, um die Parameter zu binden. MFC Ruf die Außerkraftsetzung vor Ihrem Aufruf an `ExecuteSQL`. Sie müssen nicht aufrufen `SQLPrepare`; `ExecuteSQL` Aufrufe `SQLExecDirect` und zerstört das *Befehls beschäftigt*, die nur einmal verwendet wird.

##  <a name="cancel"></a>  CDatabase::Cancel

Rufen Sie diese Memberfunktion, um anzufordern, dass die Datenquelle entweder ein asynchroner Vorgang ausgeführt wird oder einen Prozess aus einem zweiten Thread abzubrechen.

```
void Cancel();
```

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt die ODBC-API-Funktion aufrufen [SQLSetConnectOption](/previous-versions/windows/desktop/ms713564). Weitere Informationen finden Sie unter [asynchrone Ausführung](/previous-versions/windows/desktop/ms713563) im Windows SDK.

##  <a name="cantransact"></a>  CDatabase::CanTransact

Rufen Sie diese Memberfunktion, um festzustellen, ob der Datenbank Transaktionen zulässig ist.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL Recordsets, die mit diesem `CDatabase` Objekt Transaktionen werden kann, andernfalls 0.

### <a name="remarks"></a>Hinweise

Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>  CDatabase::CanUpdate

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` Objekt lässt Updates zu.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CDatabase` Objekt lässt Updates; andernfalls 0, der angibt, entweder, die Sie übergeben "true" *bReadOnly* beim Öffnen Sie die `CDatabase` Objekt oder die Datenquelle selbst ist schreibgeschützt. Die Datenquelle ist schreibgeschützt, wenn ein Aufruf an die ODBC-API-Funktion `SQLGetInfo` für SQL_DATASOURCE_READ_ONLY "y" zurück.

### <a name="remarks"></a>Hinweise

Nicht alle Treiber unterstützen Updates.

##  <a name="cdatabase"></a>  CDatabase::CDatabase

Erstellt ein `CDatabase`-Objekt.

```
CDatabase();
```

### <a name="remarks"></a>Hinweise

Sie müssen nach dem Erstellen des Objekts aufrufen seiner `OpenEx` oder `Open` Memberfunktion versucht, eine Verbindung mit einer bestimmten Datenquelle herzustellen.

Es können bequem zum Einbetten der `CDatabase` Objekt in der Dokumentklasse.

### <a name="example"></a>Beispiel

In diesem Beispiel wird die Verwendung `CDatabase` in einem `CDocument`-abgeleitete Klasse.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

##  <a name="close"></a>  CDatabase::Close

Rufen Sie diese Memberfunktion auf, wenn Sie aus einer Datenquelle trennen möchten.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Sie müssen alle zugeordneten Recordsets schließen die `CDatabase` Objekt vor dem Aufruf dieser Memberfunktion. Da `Close` nicht zerstört die `CDatabase` Objekt, Sie können das Objekt wiederverwenden, indem Sie eine neue Verbindung mit der gleichen Datenquelle oder eine andere Datenquelle zu öffnen.

Alle ausstehenden `AddNew` oder `Edit` Anweisungen von Recordsets mit der Datenbank werden abgebrochen, und alle ausstehenden Transaktionen ein Rollback. Alle Recordsets, die abhängig von der `CDatabase` Objekt in einem nicht definierten Zustand bleiben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

##  <a name="committrans"></a>  CDatabase:: CommitTrans

Rufen Sie diese Memberfunktion wird nach Abschluss von Transaktionen.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Updates erfolgreich ein Commit ausgeführt wurde; andernfalls 0. Wenn `CommitTrans` ein Fehler auftritt, die der Zustand der Datenquelle ist nicht definiert. Sie müssen die Daten, um zu bestimmen, den Zustand überprüfen.

### <a name="remarks"></a>Hinweise

Eine Transaktion besteht aus einer Reihe von Aufrufen an die `AddNew`, `Edit`, `Delete`, und `Update` Memberfunktionen von einer `CRecordset` -Objekt, das mit einem Aufruf von begann die [BeginTrans](#begintrans) Member-Funktion. `CommitTrans` Führt einen Commit die Transaktion. Standardmäßig werden Updates sofort ein Commit ausgeführt; Aufrufen von `BeginTrans` bewirkt, dass die Verpflichtung von Updates verzögert werden, bis `CommitTrans` aufgerufen wird.

Bis zum Aufruf von `CommitTrans` um eine Transaktion zu beenden, rufen Sie die [Rollback](#rollback) Memberfunktion zum Abbruch der Transaktion und die Datenquelle in den ursprünglichen Zustand belassen. Rufen Sie zunächst eine neue Transaktion `BeginTrans` erneut aus.

Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Beispiel

  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="executesql"></a>  CDatabase:: ExecuteSQL aufgerufen

Rufen Sie diese Memberfunktion auf, wenn Sie einen SQL-Befehl direkt ausführen müssen.

```
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parameter

*lpszSQL*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, die mit einem gültigen SQL‑Befehl ausgeführt. Sie können übergeben eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Hinweise

Erstellen Sie den Befehl als eine Null-terminierte Zeichenfolge an. `ExecuteSQL` gibt keine Datensätze zurück. Wenn Sie Datensätze verarbeiten möchten, verwenden Sie stattdessen ein Recordset-Objekt.

Durch Recordset-Objekte, die Befehle für die Auswahl von Daten, neue Datensätze einfügen, Löschen von Datensätzen und Bearbeiten von Datensätzen zu unterstützen, werden die meisten Befehle für eine Datenquelle ausgegeben. Nicht alle ODBC-Funktionalität wird jedoch direkt unterstützt von den Datenbankklassen, daher müssen Sie möglicherweise gelegentlich stellen einen direkte SQL-Aufruf mit `ExecuteSQL`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

##  <a name="getbookmarkpersistence"></a>  CDatabase:: GetBookmarkPersistence

Rufen Sie diese Member-Funktion auf, um die Beibehaltung von Lesezeichen auf einem recordset-Objekt nach bestimmten Vorgängen festzulegen.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Bitmaske, die die Vorgänge identifiziert, mit denen Lesezeichen auf einem recordset-Objekt beibehalten werden. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Wenn Sie beispielsweise `CRecordset::GetBookmark` und dann `CRecordset::Requery` aufrufen, ist das Lesezeichen von `GetBookmark` womöglich nicht mehr gültig. Sie sollten `GetBookmarkPersistence` vor `CRecordset::SetBookmark` aufrufen.

Die folgende Tabelle enthält die Bitmaskenwerten, die für den Rückgabewert von `GetBookmarkPersistence` kombiniert werden können.

|Bitmaskenwert|Lesezeichenbeibehaltung|
|-------------------|--------------------------|
|SQL_BP_CLOSE|Lesezeichen sind gültig, nachdem eine `Requery` Vorgang.|
|SQL_BP_DELETE|Das Lesezeichen für eine Zeile ist gültig, nachdem eine `Delete` -Vorgang in dieser Zeile.|
|SQL_BP_DROP|Lesezeichen sind gültig, nachdem eine `Close` Vorgang.|
|SQL_BP_SCROLL|Lesezeichen sind nach einer beliebigen gültigen `Move` Vorgang. Damit wird mühelos identifiziert, ob Lesezeichen im Datensatz unterstützt werden, wie von `CRecordset::CanBookmark` zurückgegeben.|
|SQL_BP_TRANSACTION|Lesezeichen sind gültig, nachdem eine Transaktion übernommen oder zurückgesetzt wurde.|
|SQL_BP_UPDATE|Das Lesezeichen für eine Zeile ist gültig, nachdem ein `Update` -Vorgang in dieser Zeile.|
|SQL_BP_OTHER_HSTMT|Lesezeichen, die mit einem recordset-Objekt verbunden sind, sind in einem zweiten Datensatz gültig.|

Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion `SQLGetInfo` im Windows SDK. Weitere Informationen über Lesezeichen finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="getconnect"></a>  CDatabase:: Getconnect

Rufen Sie diese Memberfunktion auf, um die während des Aufrufs von `OpenEx` oder `Open` verwendete Verbindungszeichenfolge abzurufen, die das `CDatabase`-Objekt mit einer Datenquelle verbunden hat.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Rückgabewert

Ein **const**[CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die Verbindungszeichenfolge, wenn `OpenEx` oder `Open` war aufgerufen wird, andernfalls eine leere Zeichenfolge.

### <a name="remarks"></a>Hinweise

Finden Sie unter [CDatabase:: Open](#open) eine Beschreibung, wie die Verbindungszeichenfolge erstellt wird.

##  <a name="getcursorcommitbehavior"></a>  GetCursorCommitBehavior

Rufen Sie diese Memberfunktion, um zu bestimmen, wie eine [CommitTrans](#committrans) Vorgang wirkt sich auf die Cursor bei geöffneten Recordset-Objekte.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der angibt, der Auswirkungen von Transaktionen auf dem geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Die folgende Tabelle enthält die möglichen Rückgabewerte für `GetCursorCommitBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.

|Rückgabewert|Auswirkung auf die CRecordset-Objekte|
|------------------|----------------------------------|
|SQL_CB_CLOSE|Rufen Sie `CRecordset::Requery` unmittelbar nach dem Transaktionscommit.|
|SQL_CB_DELETE|Rufen Sie `CRecordset::Close` unmittelbar nach dem Transaktionscommit.|
|SQL_CB_PRESERVE|Normal fort `CRecordset` Vorgänge.|

Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion `SQLGetInfo` im Windows SDK. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getcursorrollbackbehavior"></a>  Rollback

Rufen Sie diese Memberfunktion, um zu bestimmen, wie eine [Rollback](#rollback) Vorgang wirkt sich auf die Cursor bei geöffneten Recordset-Objekte.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der angibt, der Auswirkungen von Transaktionen auf dem geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Die folgende Tabelle enthält die möglichen Rückgabewerte für `GetCursorRollbackBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.

|Rückgabewert|Auswirkung auf die CRecordset-Objekte|
|------------------|----------------------------------|
|SQL_CB_CLOSE|Rufen Sie `CRecordset::Requery` unmittelbar nach dem Transaktionsrollback.|
|SQL_CB_DELETE|Rufen Sie `CRecordset::Close` unmittelbar nach dem Transaktionsrollback.|
|SQL_CB_PRESERVE|Normal fort `CRecordset` Vorgänge.|

Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion `SQLGetInfo` im Windows SDK. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getdatabasename"></a>  CDatabase::GetDatabaseName

Rufen Sie diese Memberfunktion um den Namen der derzeit verbundenen Datenbank abzurufen (vorausgesetzt, dass die Datenquelle ein benanntes Objekt, das Namen "Database" definiert).

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält der Name der Datenbank, wenn erfolgreich; andernfalls, eine leere `CString`.

### <a name="remarks"></a>Hinweise

Dies ist nicht identisch mit der Datenquellenname (DSN) angegeben, der `OpenEx` oder `Open` aufrufen. Was `GetDatabaseName` gibt, hängt von ODBC. Im Allgemeinen ist eine Datenbank einer Auflistung von Tabellen. Wenn diese Entität einen Namen hat, `GetDatabaseName` gibt es zurück.

Sie könnten z. B. diesen Namen in einer Überschrift anzuzeigen. Bei einem beim Abrufen des Namens von ODBC Fehler, `GetDatabaseName` gibt eine leere `CString`.

##  <a name="isopen"></a>  CDatabase::IsOpen

Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CDatabase` Objekt aktuell verbunden ist; andernfalls 0.

##  <a name="m_hdbc"></a>  CDatabase:: M_hdbc

Ein public-Handle für eine ODBC-datenquellenverbindung enthält – ein "Verbindungshandle".

### <a name="remarks"></a>Hinweise

In der Regel müssen Sie nicht erforderlich, diese Membervariable direkt zugreifen. Stattdessen ordnet das Framework das Handle beim Aufrufen `OpenEx` oder `Open`. Das Framework wird das Handle beim Aufrufen der **löschen** Operators für die `CDatabase` Objekt. Beachten Sie, dass die `Close` Memberfunktion nicht das Handle freizugeben.

Unter bestimmten Umständen allerdings müssen Sie das Handle direkt verwenden. Wenn Sie ODBC API-Funktionen direkt statt über Klasse aufrufen müssen z. B. `CDatabase`, sollten Sie ein Verbindungshandle als Parameter übergeben. Im folgenden Codebeispiel wird angezeigt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

##  <a name="onsetoptions"></a>  CDatabase::OnSetOptions

Das Framework ruft diese Memberfunktion auf, für die Ausführung direkt eine SQL­Anweisung mit der `ExecuteSQL` Member-Funktion.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parameter

*Befehls beschäftigt*<br/>
Der ODBC-Anweisungshandle, der für das Optionen festgelegt werden.

### <a name="remarks"></a>Hinweise

`CRecordset::OnSetOptions` Außerdem ruft diese Memberfunktion auf.

`OnSetOptions` Legt den Wert für das Anmeldungstimeout fest. Wenn frühere Aufrufe wurden die `SetQueryTimeout` und Member-Funktion `OnSetOptions` gibt die aktuellen Werte; andernfalls legt Standardwerte fest.

> [!NOTE]
>  Vor MFC 4.2 `OnSetOptions` Verarbeitungsmodus auch festlegen, um entweder Snychronous oder asynchron. Ab MFC 4.2 können sind alle Vorgänge synchron. Um einen asynchronen Vorgang ausführen zu können, müssen Sie einen direkten Aufruf der ODBC-API-Funktion, `SQLSetPos`.

Sie müssen nicht außer Kraft setzen `OnSetOptions` so ändern Sie den Timeoutwert. Rufen Sie stattdessen zum Anpassen der Timeoutwert für Abfragen `SetQueryTimeout` vor dem Erstellen einer Datensatzgruppe; `OnSetOptions` der neuen Wert verwendet. Die festgelegten Werte gelten für nachfolgende Vorgänge auf allen Recordsets oder direkte SQL-Aufrufe.

Außer Kraft setzen `OnSetOptions` sollten Sie zusätzliche Optionen festzulegen. Die Außerkraftsetzung muss der Basisklasse aufrufen `OnSetOptions` entweder vor oder nach dem Aufrufen der ODBC-API-Funktion `SQLSetStmtOption`. Führen Sie die Methode, die in die Framework Standardimplementierung von dargestellt `OnSetOptions`.

##  <a name="open"></a>  CDatabase:: Open

Rufen Sie diese Memberfunktion zum Initialisieren Sie ein neu erstelltes `CDatabase` Objekt.

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>Parameter

*lpszDSN*<br/>
Gibt an, einen Datenquellennamen, einen Namen, die mit dem ODBC-registriert ist, über die ODBC-Administrator-Anwendung. Wenn in ein DSN-Wert angegeben ist *LpszConnect* (im Format "DSN =\<Datenquelle >"), müssen nicht erneut in angegeben werden *LpszDSN*. In diesem Fall *LpszDSN* sollte NULL sein. Andernfalls können Sie NULL übergeben, sollten Sie dem Benutzer ein Dialogfeld für die Datenquelle anzuzeigen, in dem der Benutzer eine Datenquelle auswählen kann. Weitere Informationen finden Sie unter "Hinweise".

*bExclusive*<br/>
In dieser Version der Klassenbibliothek unterstützt nicht. Momentan kann eine Assertion, wenn dieser Parameter auf "true" ist. Die Datenquelle wird immer geöffnet, wie (nicht exklusiv) freigegeben.

*bReadOnly*<br/>
TRUE, wenn Sie die Verbindung schreibgeschützt ist und Aktualisierungen der Datenquelle nicht zulassen möchten. Alle abhängigen Recordsets erben dieses Attribut. Der Standardwert ist "false".

*lpszConnect*<br/>
Gibt eine Verbindungszeichenfolge an. Die Verbindungszeichenfolge verkettet Informationen, einschließlich möglicherweise einen Datenquellennamen ein, eine Benutzer-ID gültig auf die Datenquelle, eine Benutzer-Authentifizierung-Zeichenfolge (Kennwort, wenn die Datenquelle eine erforderlich ist) und andere Informationen. Die gesamte Verbindungszeichenfolge muss durch die Zeichenfolge "ODBC;" vorangestellt werden. (Großbuchstabe oder Kleinbuchstabe). Die "ODBC"; Diese Zeichenfolge wird verwendet, um anzugeben, dass die Verbindung mit einer ODBC-Datenquelle; Dies ist für die Aufwärtskompatibilität, wenn zukünftige Versionen von der Klassenbibliothek-ODBC-Datenquellen unterstützen können.

*bUseCursorLib*<br/>
TRUE, wenn Sie die ODBC Cursor Library-DLL geladen werden soll. Die Cursorbibliothek maskiert einige Funktionen des zugrunde liegenden ODBC-Treibers, effektiv verhindert, dass Dynasets (wenn der Treiber unterstützt). Die nur Cursor unterstützt, wenn die Cursorbibliothek geladen ist, sind statische Momentaufnahmen und Vorwärtscursor. Der Standardwert ist "true". Wenn Sie planen, erstellen ein Recordsetobjekt direkt vom `CRecordset` ohne abgeleitet wird, sollten Sie nicht die Cursorbibliothek geladen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; 0, wenn der Benutzer andernfalls Abbrechen, wenn ein Dialogfeld gefragt, weitere Verbindungsinformationen angezeigt. Das Framework wird in allen anderen Fällen eine Ausnahme ausgelöst.

### <a name="remarks"></a>Hinweise

Ihr Database-Objekt muss initialisiert werden, bevor Sie es verwenden können, um einem Recordset-Objekt zu erstellen.

> [!NOTE]
>  Aufrufen der [OpenEx](#openex) Memberfunktion ist die bevorzugte Methode zum Verbinden mit einer Datenquelle, und Ihr Database-Objekt zu initialisieren.

Wenn die Parameter in Ihre `Open` Aufruf enthalten keine ausreichende Informationen zum Herstellen die Verbindung, die der ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf `Open`, Ihre Verbindungszeichenfolge *LpszConnect*, befindet sich im privaten der `CDatabase` Objekt und verfügbar ist, durch den Aufruf der [GetConnect](#getconnect) Member-Funktion.

Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf `Open` zum Abrufen von Informationen aus der Benutzer, z. B. ein Kennwort, klicken Sie dann auf die Verbindungszeichenfolge, die Sie, um übergeben diese Informationen hinzufügen `Open`. Oder Sie können die Verbindungszeichenfolge, die Sie übergeben, sodass Sie es das nächste wiederverwenden können ruft Ihre Anwendung bei Zeit zu sparen `Open` auf eine `CDatabase` Objekt.

Können Sie auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für einen anderen `CDatabase` Objekt) oder andere Daten datenquellenspezifische Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 5 im Windows SDK.

Es ist möglich, dass ein Verbindungsversuch zu einem Timeout, wenn Sie z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, `Open` löst eine `CDBException`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

##  <a name="openex"></a>  CDatabase:: OpenEx

Rufen Sie diese Memberfunktion zum Initialisieren Sie ein neu erstelltes `CDatabase` Objekt.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>Parameter

*lpszConnectString*<br/>
Gibt eine ODBC-Verbindungszeichenfolge an. Dazu gehören der Name der Datenquelle als auch für andere optionale Informationen, wie Benutzer-ID und Kennwort. Z. B. "DSN = SQLServer_Source; UID = SA; PWD "abc123" = "ist eine mögliche Verbindungszeichenfolge. Beachten Sie, dass, wenn Sie NULL, für die übergeben *LpszConnectString*, ein Dialogfeld für die Datenquelle wird der Benutzer aufgefordert, eine Datenquelle auswählen.

*dwOptions*<br/>
Eine Bitmaske, die eine Kombination der folgenden Werte gibt. Der Standardwert ist 0 (null) bedeutet, dass die Datenbank als geöffnet wird mit Schreibzugriff freigegeben, die ODBC Cursor Library-DLL wird nicht geladen werden, und das Dialogfeld des ODBC-Verbindung wird nur dann, wenn es nicht genügend Informationen zum Herstellen die Verbindung stehen angezeigt.

- `CDatabase::openExclusive` In dieser Version der Klassenbibliothek unterstützt nicht. Eine Datenquelle wird immer geöffnet, wie (nicht exklusiv) freigegeben. Momentan kann eine Assertion, wenn Sie diese Option angeben.

- `CDatabase::openReadOnly` Öffnen Sie die Datenquelle als schreibgeschützt.

- `CDatabase::useCursorLib` Die ODBC-Cursorbibliothek DLL zu laden. Die Cursorbibliothek maskiert einige Funktionen des zugrunde liegenden ODBC-Treibers, effektiv verhindert, dass Dynasets (wenn der Treiber unterstützt). Die nur Cursor unterstützt, wenn die Cursorbibliothek geladen ist, sind statische Momentaufnahmen und Vorwärtscursor. Wenn Sie planen, erstellen ein Recordsetobjekt direkt vom `CRecordset` ohne abgeleitet wird, sollten Sie nicht die Cursorbibliothek geladen.

- `CDatabase::noOdbcDialog` Zeigen Sie nicht die ODBC-Verbindungsdialogfeld, unabhängig davon, ob genügend Informationen zur Verbindung bereitgestellt wird.

- `CDatabase::forceOdbcDialog` Immer zeigen Sie im Dialogfeld ODBC-Verbindung an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; 0, wenn der Benutzer andernfalls Abbrechen, wenn ein Dialogfeld gefragt, weitere Verbindungsinformationen angezeigt. Das Framework wird in allen anderen Fällen eine Ausnahme ausgelöst.

### <a name="remarks"></a>Hinweise

Ihr Database-Objekt muss initialisiert werden, bevor Sie es verwenden können, um einem Recordset-Objekt zu erstellen.

Wenn die *LpszConnectString* Parameter in Ihre `OpenEx` Aufruf nicht genügend Informationen zum Herstellen die Verbindung enthält, wird der ODBC-Treiber öffnet ein Dialogfeld den Benutzer, die erforderlichen Informationen abrufen aus, sofern Sie keine Legen Sie `CDatabase::noOdbcDialog` oder `CDatabase::forceOdbcDialog` in die *DwOptions* Parameter. Beim Aufruf `OpenEx`, Ihre Verbindungszeichenfolge *LpszConnectString*, befindet sich im privaten der `CDatabase` Objekt und verfügbar ist, durch den Aufruf der [GetConnect](#getconnect) Member-Funktion.

Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf `OpenEx` zum Abrufen von Informationen des Benutzers, z. B. ein Kennwort, und fügen Sie diese Information klicken Sie dann auf die Verbindungszeichenfolge, die Sie, um übergeben `OpenEx`. Oder Sie können die Verbindungszeichenfolge, die Sie übergeben, sodass Sie es das nächste wiederverwenden können ruft Ihre Anwendung bei Zeit zu sparen `OpenEx` auf eine `CDatabase` Objekt.

Können Sie auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für einen anderen `CDatabase` Objekt) oder andere Daten datenquellenspezifische Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 6 in der *ODBC Programmer's Reference*.

Es ist möglich, dass ein Verbindungsversuch zu einem Timeout, wenn Sie z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, `OpenEx` löst eine `CDBException`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

##  <a name="rollback"></a>  CDatabase

Rufen Sie diese Memberfunktion, um die während einer Transaktion vorgenommenen Änderungen umzukehren.

```
BOOL Rollback();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Transaktion erfolgreich rückgängig gemacht wurde, andernfalls 0. Wenn eine `Rollback` Aufruf ein Fehler auftritt, der Datenquelle und die Transaktionsprotokolldateien Zustände sind nicht definiert. Wenn `Rollback` gibt 0 zurück, Sie müssen überprüfen, dass die Datenquelle aus, um seinen Status zu bestimmen.

### <a name="remarks"></a>Hinweise

Alle `CRecordset` `AddNew`, `Edit`, `Delete`, und `Update` Aufrufe, die seit der letzten Ausführung [BeginTrans](#begintrans) Rollback in den Zustand, die zum Zeitpunkt dieses Aufrufs vorhanden waren.

Nach einem Aufruf von `Rollback`, die Transaktion über, und rufen Sie `BeginTrans` für eine andere Transaktion erneut aus. Der Datensatz, den aktuellen, bevor Sie aufgerufen wurde `BeginTrans` wird der aktuelle Datensatz erneut nach `Rollback`.

Nach einem Rollback bleibt der Datensatz, der vor dem Rollback war aktuell. Weitere Informationen über den Status des Recordsets und der Datenquelle nach einem Rollback finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Beispiel

  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="setlogintimeout"></a>  CDatabase::SetLoginTimeout

Rufen Sie diese Memberfunktion – vor dem Aufruf `OpenEx` oder `Open` – überschreiben Sie die Standardanzahl von Sekunden zulässig sind, bevor ein Versuch der quellverbindung Timeout.

```
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parameter

*dwSeconds*<br/>
Timeout bei die Anzahl der Sekunden, bevor ein Verbindungsversuch Gerätedaten.

### <a name="remarks"></a>Hinweise

Ein Verbindungsversuch kann einen Timeout beendet, wenn Sie z. B. das DBMS nicht verfügbar ist. Rufen Sie `SetLoginTimeout` Nachdem Sie den nicht initialisierten konstruiert `CDatabase` Objekt jedoch vor dem Aufrufen `OpenEx` oder `Open`.

Der Standardwert für die Anmeldung Timeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Timeoutwert für die Anmeldung anzugeben. Wenn die Datenquelle keine Timeouts unterstützt, erhalten Sie Ablaufverfolgungsausgabe jedoch keine Ausnahme. Ein Wert von 0 bedeutet "unendliche".

##  <a name="setquerytimeout"></a>  CDatabase::SetQueryTimeout

Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in der verbundenen Datenquelle Timeout Gerätedaten zu überschreiben.

```
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parameter

*dwSeconds*<br/>
Die Anzahl der Sekunden, bevor der abfrageversuch einer ist ein Timeout aufgetreten.

### <a name="remarks"></a>Hinweise

Ein Vorgang kann aufgrund von Netzwerkproblemen für den Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen des Recordsets `AddNew`, `Update` oder `Delete` Memberfunktionen, wenn Sie den Timeoutwert für Abfragen ändern möchten. Die Einstellung wirkt sich auf alle nachfolgenden `Open`, `AddNew`, `Update`, und `Delete` Aufrufe an alle zugeordneten Recordsets `CDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset aus. Beispielsweise wird bei nachfolgenden `Move` Vorgänge verwenden Sie den neuen Wert nicht.

Der Standardwert für die Abfragetimeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, erfolgt kein timeout die Kommunikation mit der Datenquelle reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein. Wenn die Datenquelle keine Timeouts unterstützt, erhalten Sie Ablaufverfolgungsausgabe jedoch keine Ausnahme.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
