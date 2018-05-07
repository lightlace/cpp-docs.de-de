---
title: CDatabase-Klasse | Microsoft Docs
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
ms.openlocfilehash: cb71b31fa3133b4e1b93564ef0b530cb20bb3dfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
|[CDatabase::CDatabase](#cdatabase)|Erstellt ein `CDatabase`-Objekt. Initialisieren Sie das Objekt, durch den Aufruf `OpenEx` oder **öffnen**.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|Startet eine "Transaktion" – eine Reihe von umkehrbare Aufrufe an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen der Klasse `CRecordset` – auf die verbundene Datenquelle. Die Datenquelle muss die Unterstützung von Transaktionen für **BeginTrans** wirkt sich nur.|  
|[CDatabase::BindParameters](#bindparameters)|Ermöglicht Ihnen, Binden von Parametern vor dem Aufruf `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess aus ein zweiter Thread ab.|  
|[CDatabase::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDatabase::CanUpdate](#canupdate)|Gibt NULL zurück, wenn die `CDatabase` Objekt ist aktualisierbar (schreibgeschützt).|  
|[CDatabase::Close](#close)|Schließt die Verbindung mit der Datenquelle.|  
|[CDatabase:: CommitTrans](#committrans)|Schließt eine Transaktion begonnen, indem **BeginTrans**. Befehle in der Transaktion, die die Datenquelle ändern, werden durchgeführt.|  
|[CDatabase:: ExecuteSQL](#executesql)|Führt eine SQL­Anweisung. Es werden keine Datensätze zurückgegeben.|  
|[CDatabase:: GetBookmarkPersistence](#getbookmarkpersistence)|Identifiziert die Vorgänge, die über denen Lesezeichen Recordset-Objekte beibehalten werden.|  
|[CDatabase::GetConnect](#getconnect)|Gibt die ODBC-Verbindungszeichenfolge zur Verbindung der `CDatabase` Objekt mit einer Datenquelle.|  
|[GetCursorCommitBehavior](#getcursorcommitbehavior)|Identifiziert die Auswirkung der Commit einer Transaktion in einem geöffneten Recordset-Objekt.|  
|[Rollback](#getcursorrollbackbehavior)|Identifiziert die Auswirkung von Rollback einer Transaktion in einem geöffneten Recordset-Objekt.|  
|[CDatabase::GetDatabaseName](#getdatabasename)|Gibt den Namen der Datenbank, die derzeit in Verwendung zurück.|  
|[CDatabase::IsOpen](#isopen)|Gibt NULL zurück, wenn die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.|  
|[CDatabase::OnSetOptions](#onsetoptions)|Wird aufgerufen, durch das Framework standard Verbindungsoptionen festlegen. Die standardmäßige Implementierung legt den Timeoutwert für Abfragen. Sie können diese Optionen voraus einrichten, durch den Aufruf `SetQueryTimeout`.|  
|[CDatabase:: Open](#open)|Herstellen einer Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|  
|[CDatabase:: OpenEx](#openex)|Herstellen einer Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|  
|[CDatabase](#rollback)|Kehrt die während der aktuellen Transaktion vorgenommenen Änderungen. Gibt die Datenquelle den ursprünglichen Zustand zur definiert die **BeginTrans** Aufruf unverändert.|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden, nach dem ein Data Source-Verbindungsversuch einen Timeout beendet wird.|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge Abfragen durch einen Timeout beendet. Wirkt sich auf alle nachfolgenden Recordset **öffnen**, `AddNew`, **bearbeiten**, und **löschen** aufrufen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDatabase:: M_hdbc](#m_hdbc)|Open Database Connectivity (ODBC)-Verbindungshandle mit einer Datenquelle. Typ **HDBC**.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Datenquelle ist eine bestimmte Instanz von Daten, die von einigen Datenbank-Managementsystem (DBMS) gehostet wird. Beispiele für sind Microsoft SQL Server, Microsoft Access Borland dBASE und xBASE. Sie haben eine oder mehrere `CDatabase` Objekte, die aktiv zu einem Zeitpunkt in der Anwendung.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Mit `CDatabase`, erstellen eine `CDatabase` Objekt, und rufen die `OpenEx` Memberfunktion. Dadurch wird eine Verbindung geöffnet. Wenn Sie erstellen dann `CRecordset` Objekte für Vorgänge für die verbundene Datenquelle dem recordsetkonstruktor übergeben, einen Zeiger auf die `CDatabase` Objekt. Aufrufen, wenn Sie fertig sind, verwenden die Verbindung, die **schließen** Member-Funktion und zerstört der `CDatabase` Objekt. **Schließen** schließt alle Recordsets, die Sie zuvor nicht geschlossen.  
  
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
 Wert ungleich NULL, wenn der Aufruf erfolgreich war, und Änderungen manuell nur ein Commit ausgeführt wurde sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einem oder mehreren Aufrufen an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen von einem `CRecordset` Objekt. Vor Beginn einer Transaktions die `CDatabase` Objekt muss bereits angeschlossen wurden mit der Datenquelle durch Aufrufen seiner `OpenEx` oder **öffnen** Memberfunktion. Um die Transaktion zu beenden, rufen [CommitTrans](#committrans) akzeptieren alle Änderungen an der Datenquelle (und sie ausführt), oder rufen Sie [Rollback](#rollback) die gesamte Transaktion abgebrochen. Rufen Sie **BeginTrans** nach jeder der Transaktion beteiligten Recordsets öffnen und als in der Nähe des tatsächlichen update-Vorgänge wie möglich.  
  
> [!CAUTION]
>  Je nach ODBC-Treibers zum Öffnen eines Recordsets vor dem Aufruf **BeginTrans** kann Probleme verursachen, beim Aufrufen von **Rollback**. Überprüfen Sie die bestimmten Treiber, den Sie verwenden. Beispielsweise müssen bei Verwendung der Microsoft Access-Treiber, die in der Microsoft ODBC Desktop Driver Pack 3.0 enthalten Sie Jet-Datenbankmodul-Anforderung zu berücksichtigen, dass Sie keine Transaktion für eine beliebige Datenbank beginnen soll, die einen geöffneten Cursor hat. In den MFC-Datenbankklassen bedeutet ein geöffneten Cursor ein offenes `CRecordset` Objekt. Weitere Informationen finden Sie unter [technischen Hinweis 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).  
  
 **BeginTrans** auch Sperren unter Umständen von Datensätzen auf dem Server, abhängig von der angeforderten Parallelität und die Funktionen der Datenquelle. Informationen zum Sperren von Daten, finden Sie im Artikel [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
 Benutzerdefinierte Transaktionen werden in diesem Artikel erläutert [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
 **BeginTrans** richtet den Zustand, der die Reihenfolge der Transaktionen kann Rollback (rückgängig gemacht). Um einen neuen Zustand für Rollbacks einzurichten, übernehmen alle aktuellen Transaktionen, rufen Sie anschließend **BeginTrans** erneut aus.  
  
> [!CAUTION]
>  Aufrufen von **BeginTrans** erneut ohne Aufruf **CommitTrans** oder **Rollback** ist ein Fehler.  
  
 Rufen Sie die [CanTransact](#cantransact) Member-Funktion, um zu bestimmen, ob der Treiber für eine bestimmte Datenbank Transaktionen unterstützt. Sie sollten auch aufrufen, [GetCursorCommitBehavior](#getcursorcommitbehavior) und [GetCursorRollbackBehavior](#getcursorrollbackbehavior) um die Unterstützung für die Beibehaltung der Cursor zu bestimmen.  
  
 Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="bindparameters"></a>  CDatabase::BindParameters  
 Überschreiben Sie `BindParameters` müssen Sie Parameter vor dem Aufruf binden [CDatabase:: ExecuteSQL](#executesql).  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Das Handle der ODBC-Anweisung für das Parameter gebunden werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ansatz ist nützlich, wenn Sie nicht, dass das Ergebnis benötigen von einer gespeicherten Prozedur festgelegt.  
  
 Rufen Sie in der Außerkraftsetzung **SQLBindParameters** und zugehörigen ODBC-Funktionen, um die Parameter zu binden. MFC Ruf die Außerkraftsetzung vor dem Aufruf von `ExecuteSQL`. Sie müssen nicht aufrufen **SQLPrepare**; `ExecuteSQL` Aufrufe **SQLExecDirect** und zerstört der **Befehls beschäftigt**, der nur einmal verwendet wird.  
  
##  <a name="cancel"></a>  CDatabase::Cancel  
 Rufen Sie diese Memberfunktion zum anfordern, dass die Datenquelle eines asynchronen Vorgangs oder eines Prozesses aus ein zweiter Thread "Abbrechen".  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt aufrufen die ODBC-API-Funktion [SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx). Weitere Informationen finden Sie unter [asynchrone Ausführung](https://msdn.microsoft.com/library/ms713563.aspx) im Windows SDK.  
  
##  <a name="cantransact"></a>  CDatabase::CanTransact  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Datenbank Transaktionen zulässt.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL Recordsets, die mit diesem `CDatabase` Transaktionen werden kann, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>  CDatabase::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` Objekt lässt Updates.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDatabase` Objekt lässt Updates; andernfalls 0, der angibt, entweder, den Sie übergeben **"true"** in `bReadOnly` beim Öffnen Sie die `CDatabase` Objekt oder die Datenquelle selbst ist schreibgeschützt. Die Datenquelle ist schreibgeschützt, wenn ein Aufruf an die ODBC-API-Funktion **SQLGetInfo** für **SQL_DATASOURCE_READ_ONLY** gibt "y" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nicht alle Treiber unterstützen Updates.  
  
##  <a name="cdatabase"></a>  CDatabase::CDatabase  
 Erstellt ein `CDatabase`-Objekt.  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die `OpenEx` oder **öffnen** Memberfunktion versucht, eine Verbindung mit einer bestimmten Datenquelle herzustellen.  
  
 Sie könnten praktischerweise So betten Sie ein die `CDatabase` Objekt in Ihrem Dokumentklasse.  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Verwendung `CDatabase` in einem `CDocument`-Klasse.  
  
 [!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="close"></a>  CDatabase::Close  
 Rufen Sie diese Memberfunktion auf, wenn aus einer Datenquelle getrennt werden soll.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen alle zugeordneten Recordsets schließen die `CDatabase` -Objekt, bevor Sie diese Memberfunktion aufrufen. Da **schließen** nicht zerstört die `CDatabase` -Objekt, Sie können jedoch stattdessen das wiederverwenden, indem Sie eine neue Verbindung mit derselben Datenquelle oder eine andere Datenquelle zu öffnen.  
  
 Alle ausstehenden `AddNew` oder **bearbeiten** -Anweisungen des Recordsets mit der Datenbank abgebrochen, und alle anstehenden Transaktionen zurückgesetzt. Alle Recordsets abhängig von der `CDatabase` Objekt befinden sich in einem nicht definierten Zustand versetzt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="committrans"></a>  CDatabase:: CommitTrans  
 Rufen Sie diese Memberfunktion nach Abschluss von Transaktionen.  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Updates erfolgreich ein Commit ausgeführt wurde; andernfalls 0. Wenn **CommitTrans** ein Fehler auftritt, der der Zustand der Datenquelle ist nicht definiert. Überprüfen Sie die Daten, um dessen Status zu bestimmen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einer Reihe von Aufrufen an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen von einer `CRecordset` -Objekt, das mit begann ein aufrufen, um die [BeginTrans](#begintrans) Memberfunktion. **CommitTrans** führt einen Commit der Transaktion. Standardmäßig werden Updates sofort ein Commit ausgeführt wurde; Aufrufen von **BeginTrans** Verpflichtung Updates bis verzögert wird bewirkt, dass **CommitTrans** aufgerufen wird.  
  
 Bis zum Aufruf von **CommitTrans** um eine Transaktion zu beenden, rufen Sie die [Rollback](#rollback) Memberfunktion versucht, die Transaktion abzubrechen und die Datenquelle in den ursprünglichen Zustand belassen. Um eine neue Transaktion zu starten, rufen **BeginTrans** erneut aus.  
  
 Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="executesql"></a>  CDatabase:: ExecuteSQL  
 Rufen Sie diese Memberfunktion auf, wenn einen SQL-Befehl direkt ausgeführt werden müssen.  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit einem gültigen SQL‑Befehl ausführen. Sie können übergeben, eine [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie den Befehl als eine Null-terminierte Zeichenfolge an. `ExecuteSQL` gibt keine Datensätze zurück. Wenn Sie Datensätze arbeiten möchten, verwenden Sie stattdessen ein Recordset-Objekt.  
  
 Über Recordset-Objekte, die Befehle für die Daten auswählen, Einfügen neuer Datensätze, Löschen von Datensätzen und Bearbeiten von Datensätzen zu unterstützen, werden die meisten Befehle für eine Datenquelle ausgegeben. Nicht alle ODBC-Funktionalität wird jedoch direkt unterstützt von den Datenbankklassen, daher müssen Sie möglicherweise gelegentlich stellen einen direkte SQL-Aufruf mit `ExecuteSQL`.  
  
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
|`SQL_BP_CLOSE`|Lesezeichen sind gültig, nachdem ein **Requery** Vorgang.|  
|`SQL_BP_DELETE`|Das Lesezeichen für eine Zeile ist gültig, nachdem ein **löschen** -Vorgang in dieser Zeile.|  
|`SQL_BP_DROP`|Lesezeichen sind gültig, nachdem ein **schließen** Vorgang.|  
|`SQL_BP_SCROLL`|Lesezeichen sind nach einem beliebigen gültigen **verschieben** Vorgang. Damit wird mühelos identifiziert, ob Lesezeichen im Datensatz unterstützt werden, wie von `CRecordset::CanBookmark` zurückgegeben.|  
|`SQL_BP_TRANSACTION`|Lesezeichen sind gültig, nachdem eine Transaktion übernommen oder zurückgesetzt wurde.|  
|`SQL_BP_UPDATE`|Das Lesezeichen für eine Zeile ist gültig, nachdem ein **Update** -Vorgang in dieser Zeile.|  
|`SQL_BP_OTHER_HSTMT`|Lesezeichen, die mit einem recordset-Objekt verbunden sind, sind in einem zweiten Datensatz gültig.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** im Windows SDK. Weitere Informationen zu Lesezeichen, finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="getconnect"></a>  CDatabase::GetConnect  
 Rufen Sie diese Memberfunktion auf, um die während des Aufrufs von `OpenEx` oder `Open` verwendete Verbindungszeichenfolge abzurufen, die das `CDatabase`-Objekt mit einer Datenquelle verbunden hat.  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die Verbindungszeichenfolge, wenn `OpenEx` oder `Open` wurde aufgerufen wurde, andernfalls eine leere Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CDatabase:: Open](#open) eine Beschreibung, wie die Verbindungszeichenfolge erstellt wird.  
  
##  <a name="getcursorcommitbehavior"></a>  GetCursorCommitBehavior  
 Rufen Sie diese Memberfunktion, um zu bestimmen, wie eine [CommitTrans](#committrans) Vorgang wirkt sich auf die Cursor bei geöffneten Recordset-Objekte.  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, der Auswirkungen von Transaktionen auf geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle listet die möglichen Rückgabewerte für `GetCursorCommitBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.  
  
|Rückgabewert|Auswirkung auf die CRecordset-Objekte|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Rufen Sie `CRecordset::Requery` unmittelbar nach dem Transaktionscommit.|  
|`SQL_CB_DELETE`|Rufen Sie `CRecordset::Close` unmittelbar nach dem Transaktionscommit.|  
|`SQL_CB_PRESERVE`|Normal fort `CRecordset` Vorgänge.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** im Windows SDK. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="getcursorrollbackbehavior"></a>  Rollback  
 Rufen Sie diese Memberfunktion, um zu bestimmen, wie eine [Rollback](#rollback) Vorgang wirkt sich auf die Cursor bei geöffneten Recordset-Objekte.  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, der Auswirkungen von Transaktionen auf geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle listet die möglichen Rückgabewerte für `GetCursorRollbackBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.  
  
|Rückgabewert|Auswirkung auf die CRecordset-Objekte|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Rufen Sie `CRecordset::Requery` unmittelbar nach dem Transaktionsrollback.|  
|`SQL_CB_DELETE`|Rufen Sie `CRecordset::Close` unmittelbar nach dem Transaktionsrollback.|  
|`SQL_CB_PRESERVE`|Normal fort `CRecordset` Vorgänge.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** im Windows SDK. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="getdatabasename"></a>  CDatabase::GetDatabaseName  
 Rufen Sie diese Memberfunktion um den Namen der derzeit verbundenen Datenbank abgerufen werden (vorausgesetzt, dass die Datenquelle ein benanntes Objekt mit dem Namen "Datenbank" definiert).  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , den Datenbanknamen enthält, wenn erfolgreich; andernfalls, eine leere `CString`.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nicht identisch mit der Datenquellenname (DSN), angegeben der `OpenEx` oder **öffnen** aufrufen. Was `GetDatabaseName` gibt hängt von ODBC. Im Allgemeinen ist eine Datenbank, eine Auflistung von Tabellen. Wenn diese Entität einen Namen besitzt, `GetDatabaseName` wird zurückgegeben.  
  
 Sie sollten z. B. diesen Namen in einer Überschrift anzuzeigen. Bei einem beim Abrufen des Namens von ODBC Fehler, `GetDatabaseName` gibt ein leeres **Cstring**.  
  
##  <a name="isopen"></a>  CDatabase::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDatabase` Objekt ist momentan verbunden; andernfalls 0.  
  
##  <a name="m_hdbc"></a>  CDatabase:: M_hdbc  
 Ein öffentlicher Handle für eine ODBC-datenquellenverbindung enthält – ein "Verbindungshandle".  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise müssen Sie keine auf diese Membervariable direkt zugegriffen werden muss. Stattdessen das Framework das Anweisungshandle zugeordnet, beim Aufrufen von `OpenEx` oder **öffnen**. Das Framework das Handle freigegeben, beim Aufrufen der **löschen** Operator auf die `CDatabase` Objekt. Beachten Sie, dass die **schließen** Memberfunktion das Handle nicht freigeben.  
  
 In einigen Fällen jedoch, Sie müssen möglicherweise das Handle direkt verwenden. Angenommen, Sie ODBC-API-Funktionen direkt anstatt über Klasse aufrufen müssen `CDatabase`, möglicherweise ein Verbindungshandle als Parameter übergeben. Finden Sie im folgenden Codebeispiel wird ein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="onsetoptions"></a>  CDatabase::OnSetOptions  
 Das Framework ruft diese Memberfunktion auf, wenn eine SQL-Anweisung mit direkt Ausführen der `ExecuteSQL` Memberfunktion.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Das Handle der ODBC-Anweisung für das Optionen festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 `CRecordset::OnSetOptions` Außerdem wird diese Memberfunktion aufgerufen.  
  
 `OnSetOptions` Legt den Wert für das Anmeldungstimeout an. Wenn vorherigen Aufrufe von wurden die `SetQueryTimeout` und Memberfunktion, `OnSetOptions` gibt die aktuellen Werten; andernfalls, legt Standardwerte fest.  
  
> [!NOTE]
>  Vor MFC-4.2 `OnSetOptions` den Verarbeitungsmodus auch festlegen, um entweder Snychronous oder asynchron. Ab MFC 4.2, sind alle Vorgänge synchron. Um einen asynchronen Vorgang ausführen zu können, müssen Sie einen direkten Aufruf der ODBC-API-Funktion, **SQLSetPos**.  
  
 Sie müssen nicht außer Kraft setzen `OnSetOptions` so ändern Sie den Timeoutwert. Rufen Sie stattdessen zum Anpassen der Timeoutwert für Abfragen `SetQueryTimeout` vor dem Erstellen eines Recordsets; `OnSetOptions` verwendet den neuen Wert. Die festgelegten Werte gelten für nachfolgende Operationen auf allen Recordsets oder direkte SQL-Aufrufe.  
  
 Überschreiben Sie `OnSetOptions` , wenn Sie zusätzliche Optionen festlegen möchten. Ihre Überschreibung der Basisklasse aufrufen sollte `OnSetOptions` vor oder nach dem Aufruf der ODBC-API-Funktion **SQLSetStmtOption**. Führen Sie die Methode in der Framework-Standardimplementierung von `OnSetOptions`.  
  
##  <a name="open"></a>  CDatabase:: Open  
 Rufen Sie diese Memberfunktion zum Initialisieren einer neu erstellten `CDatabase` Objekt.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDSN`  
 Gibt einen Datenquellennamen – ein Namen, die mit ODBC über das Programm für die ODBC-Administrator registriert. Wenn in ein DSN-Wert angegeben ist `lpszConnect` (im Format "DSN =\<Data Source->"), müssen nicht erneut angegeben werden `lpszDSN`. In diesem Fall `lpszDSN` muss **NULL**. Andernfalls können Sie übergeben **NULL** gegebenenfalls die Benutzer mit einer Datenquelle (Dialogfeld) dar, in dem der Benutzer eine Datenquelle auswählen kann. Weitere Informationen finden Sie unter "Hinweise".  
  
 `bExclusive`  
 In dieser Version der Klassenbibliothek unterstützt nicht. Derzeit ist eine Assertion fehlschlägt, wenn dieser Parameter ist **"true"**. Die Datenquelle ist immer geöffnet, wie freigegebene (nicht exklusiv).  
  
 `bReadOnly`  
 **"True"** Wenn Sie beabsichtigen, dass die Verbindung schreibgeschützt sein und mit der Datenquelle Updates verhindert werden soll. Alle abhängigen Recordsets erben dieses Attribut. Der Standardwert ist **"false"**.  
  
 `lpszConnect`  
 Gibt eine Verbindungszeichenfolge an. Die Verbindungszeichenfolge verkettet Informationen, einschließlich möglicherweise einen Datenquellennamen, eine Benutzer-ID gültig für die Datenquelle, eine Benutzer-Authentifizierung-Zeichenfolge (Kennwort, falls die Datenquelle eines benötigt) und andere Informationen. Die gesamte Verbindungszeichenfolge muss durch die Zeichenfolge "ODBC" vorangestellt werden. (Groß- oder Kleinbuchstabe). Die "ODBC"; Diese Zeichenfolge wird verwendet, um anzugeben, dass die Verbindung mit einer ODBC-Datenquelle; Dies ist für die Aufwärtskompatibilität, wenn zukünftige Versionen von der Klassenbibliothek-ODBC-Datenquellen unterstützen können.  
  
 `bUseCursorLib`  
 **"True"** , wenn Sie die ODBC Cursor Library-DLL geladen werden soll. Die Cursorbibliothek maskiert einige Funktionen der zugrunde liegende ODBC-Treiber, effektiv verhindert, dass Dynasets (wenn der Treiber unterstützt). Die einzige Cursor unterstützt, wenn die Cursorbibliothek geladen ist sind Momentaufnahmen statische und Vorwärtscursor. Der Standardwert ist **"true"**. Wenn Sie planen, erstellen Sie ein Recordset-Objekt direkt aus `CRecordset` ohne daraus ableiten, sollten Sie nicht die Cursorbibliothek geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; Abbrechen andernfalls 0, wenn der Benutzer auf, wenn ein Dialogfeld Weitere Verbindungsinformationen angefordert werden angezeigt. In allen anderen Fällen löst das Framework eine Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
 Database-Objekt muss initialisiert werden, bevor Sie ihn verwenden, um einem Recordset-Objekt zu erstellen.  
  
> [!NOTE]
>  Aufrufen der [OpenEx](#openex) Memberfunktion ist die bevorzugte Methode zum Herstellen einer Verbindung mit einer Datenquelle und Database-Objekt zu initialisieren.  
  
 Wenn die Parameter in Ihre **öffnen** Aufruf enthalten keine ausreichende Informationen zum Herstellen die Verbindung, die ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf **öffnen**, Ihre Verbindungszeichenfolge `lpszConnect`, privat in gespeichert wurde die `CDatabase` Objekt, und ist verfügbar durch Aufrufen der [GetConnect](#getconnect) Memberfunktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf **öffnen** beim Abrufen von Informationen aus der Benutzer, z. B. eines Kennworts der Verbindungszeichenfolge übergeben Sie an diese Informationen dann hinzufügen **öffnen**. Vielleicht möchten Sie Zeit sparen der Verbindungszeichenfolge übergeben werden, damit Sie es das nächste wiederverwenden können Ihre Anwendung Aufrufe **öffnen** auf eine `CDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für ein anderes `CDatabase` Objekt) oder andere Daten datenquellenspezifische Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 5 im Windows SDK.  
  
 Es ist möglich, für einen Verbindungsversuch zu einem Timeout, wenn Sie z. B. die DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch nicht gelingt, **öffnen** löst eine `CDBException`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="openex"></a>  CDatabase:: OpenEx  
 Rufen Sie diese Memberfunktion zum Initialisieren einer neu erstellten `CDatabase` Objekt.  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnectString`  
 Gibt eine ODBC-Verbindungszeichenfolge an. Dies schließt die Namen der Datenquelle sowie andere optionale Informationen, wie Benutzer-ID und Kennwort. Z. B. "DSN = SQLServer_Source; UID = SA; PWD = abc123 "ist eine mögliche Verbindungszeichenfolge. Beachten Sie, dass, wenn Sie übergeben **NULL** für `lpszConnectString`, ein Dialogfeld für die Datenquelle wird der Benutzer aufgefordert, eine Datenquelle auswählen.  
  
 `dwOptions`  
 Eine Bitmaske, die eine Kombination der folgenden Werte gibt. Der Standardwert ist 0 (null) bedeutet, dass die Datenbank als geöffnet wird, mit Schreibzugriff freigegeben, die ODBC Cursor Library-DLL wird nicht geladen werden, und das Dialogfeld ODBC-Verbindung wird nur angezeigt, wenn es nicht genügend Informationen zum Herstellen die Verbindung ist.  
  
- **CDatabase::openExclusive** in dieser Version der Klassenbibliothek nicht unterstützt. Eine Datenquelle ist immer geöffnet, wie freigegebene (nicht exklusiv). Momentan kann eine Assertion, wenn Sie diese Option angeben.  
  
- **CDatabase::openReadOnly** öffnen Sie die Datenquelle als schreibgeschützt.  
  
- **DwOptions** die ODBC-Cursorbibliothek DLL zu laden. Die Cursorbibliothek maskiert einige Funktionen der zugrunde liegende ODBC-Treiber, effektiv verhindert, dass Dynasets (wenn der Treiber unterstützt). Die einzige Cursor unterstützt, wenn die Cursorbibliothek geladen ist sind Momentaufnahmen statische und Vorwärtscursor. Wenn Sie planen, erstellen Sie ein Recordset-Objekt direkt aus `CRecordset` ohne daraus ableiten, sollten Sie nicht die Cursorbibliothek geladen.  
  
- **CDatabase::noOdbcDialog** nicht anzeigen klicken Sie im Dialogfeld ODBC-Verbindung unabhängig davon, ob genügend Verbindungsinformationen bereitgestellt wird.  
  
- **CDatabase::forceOdbcDialog** immer zeigt das Dialogfeld ODBC-Verbindung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; Abbrechen andernfalls 0, wenn der Benutzer auf, wenn ein Dialogfeld Weitere Verbindungsinformationen angefordert werden angezeigt. In allen anderen Fällen löst das Framework eine Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
 Database-Objekt muss initialisiert werden, bevor Sie ihn verwenden, um einem Recordset-Objekt zu erstellen.  
  
 Wenn die `lpszConnectString` Parameter in Ihre `OpenEx` Aufruf nicht genügend Informationen zum Herstellen der Verbindung enthält, wird der ODBC-Treiber öffnet ein Dialogfeld können Sie dem Benutzer die erforderlichen Informationen abrufen, sofern Sie nicht festgelegt haben **CDatabase:: NoOdbcDialog** oder **CDatabase::forceOdbcDialog** in der `dwOptions` Parameter. Beim Aufruf `OpenEx`, Ihre Verbindungszeichenfolge `lpszConnectString`, privat in gespeichert wurde die `CDatabase` Objekt, und ist verfügbar durch Aufrufen der [GetConnect](#getconnect) Memberfunktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf `OpenEx` zum Abrufen von Informationen vom Benutzer, z. B. ein Kennwort, und klicken Sie dann hinzufügen, die Informationen der Verbindungszeichenfolge übergeben werden, um `OpenEx`. Vielleicht möchten Sie Zeit sparen der Verbindungszeichenfolge übergeben werden, damit Sie es das nächste wiederverwenden können Ihre Anwendung Aufrufe `OpenEx` auf eine `CDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen von anmeldeautorisierung (jeweils für ein anderes `CDatabase` Objekt) oder andere Daten datenquellenspezifische Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 6 in der *ODBC Programmer's Reference*.  
  
 Es ist möglich, für einen Verbindungsversuch zu einem Timeout, wenn Sie z. B. die DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch nicht gelingt, `OpenEx` löst eine `CDBException`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="rollback"></a>  CDatabase  
 Rufen Sie diese Memberfunktion, um die während einer Transaktion vorgenommenen Änderungen umzukehren.  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Transaktion erfolgreich umgekehrt wurde; andernfalls 0. Wenn eine **Rollback** Aufruf fehlschlägt, die Datenquelle und die Transaktion Status ist nicht definiert. Wenn **Rollback** 0 zurück, müssen Sie überprüfen, die Datenquelle, um dessen Status zu bestimmen.  
  
### <a name="remarks"></a>Hinweise  
 Alle `CRecordset` `AddNew`, **bearbeiten**, **löschen**, und **Update** Aufrufe, die seit der letzten ausgeführten [BeginTrans](#begintrans) werden rückgängig gemacht in den Zustand, der zum Zeitpunkt dieses Aufrufs vorhanden waren.  
  
 Nach einem Aufruf von **Rollback**, übersteigt die Transaktion, und rufen Sie **BeginTrans** für eine andere Transaktion erneut aus. Der Datensatz, der vor dem Aufrufen aktuell waren, **BeginTrans** wird zum aktuellen Datensatz erneut nach **Rollback**.  
  
 Nach einem Rollback bleibt der Datensatz, der vor dem Rollback aktuell war aktuelle. Weitere Informationen über den Status des Recordsets und der Datenquelle nach einem Rollback, finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="setlogintimeout"></a>  CDatabase::SetLoginTimeout  
 Rufen Sie diese Memberfunktion – vor dem Aufruf `OpenEx` oder **öffnen** – die Standardanzahl von Sekunden, die zulässig sind, bevor ein versuchten Daten überschreiben-Verbindung ein Timeout eintritt.  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSeconds`  
 Die Anzahl der Sekunden, bevor ein Verbindungsversuch ein Timeout eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Verbindungsversuch möglicherweise einen Timeout beendet, wenn z. B. das DBMS nicht verfügbar ist. Rufen Sie **SetLoginTimeout** Nachdem Sie den nicht initialisierten konstruiert `CDatabase` -Objekt jedoch vor dem Aufrufen `OpenEx` oder **öffnen**.  
  
 Der Standardwert für die Anmeldung Timeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Timeoutwert für die Anmeldung anzugeben. Wenn die Datenquelle Timeout nicht unterstützt wird, erhalten Sie Ablaufverfolgungsausgabe jedoch nicht auf eine Ausnahme. Ein Wert von 0 bedeutet "unendlich".  
  
##  <a name="setquerytimeout"></a>  CDatabase::SetQueryTimeout  
 Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge in die verbundene Datenquelle-Timeout zu überschreiben.  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSeconds`  
 Die Anzahl der Sekunden, bevor ein abfrageversuch ein Timeout eintritt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang möglicherweise aufgrund von Netzwerkproblemen-Zugriff, übermäßige Abfrage Verarbeitungszeit und usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufruf des Recordsets `AddNew`, **Update** oder **löschen** Memberfunktionen, wenn Sie den Timeoutwert für Abfragen ändern möchten. Die Einstellung wirkt sich auf alle nachfolgenden **öffnen**, `AddNew`, **Update**, und **löschen** Aufrufe an alle zugeordneten Recordsets `CDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach Öffnen ändert sich nicht auf den Wert für das Recordset. Beispielsweise wird bei nachfolgenden **verschieben** Vorgänge verwenden Sie den neuen Wert nicht.  
  
 Der Standardwert für Abfragetimeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. die Kommunikation mit der Datenquelle reagiert. Dieses Verhalten kann während der Entwicklung nützlich sein. Wenn die Datenquelle Timeout nicht unterstützt wird, erhalten Sie Ablaufverfolgungsausgabe jedoch nicht auf eine Ausnahme.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
