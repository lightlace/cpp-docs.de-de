---
title: 'TN042: Empfehlungen für ODBC-Treiberentwickler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.odbc
dev_langs:
- C++
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35c75f5c5bae3a1b56abe91340de00f373663792
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384793"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: Empfehlungen für ODBC-Treiberentwickler
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem Hinweis werden die Richtlinien für ODBC-Treiber-Writer. Es werden allgemeine Anforderungen und Annahmen der ODBC-Funktionen, die die MFC-Datenbankklassen stellen und verschiedene erwartete semantische Details. Erforderliche Funktionalität zur Unterstützung von drei Treibers `CRecordset` öffnen Modi (**"forwardOnly"**, **Momentaufnahme** und **Dynaset**) beschrieben werden.  
  
## <a name="odbcs-cursor-library"></a>Der ODBC-Cursorbibliothek  
 Die MFC-Datenbankklassen präsentieren Funktionalität für den Benutzer, der in vielen Fällen die von den meisten Level 1-ODBC-Treiber bereitgestellte Funktionalität überschreitet. Glücklicherweise ODBCs-Cursorbibliothek überlagert selbst zwischen den Datenbankklassen und der Treiber und wird automatisch ein Großteil dieser zusätzlichen Funktionalität bereit.  
  
 Für die Instanz, unterstützt die meisten 1.0 Treiber nicht rückwärts-scrollen. Die Cursorbibliothek erkannt, und wird aus dem Treiber Zeilen zwischengespeichert und stellt sie wie bei FETCH_PREV Aufrufen in angefordert können **SQLExtendedFetch**.  
  
 Ein weiteres Beispiel für wichtiges Cursor Library Abhängigkeit ist positionierte Updates. Die meisten 1.0 Treiber auch keinen positionierte Updates, aber die Cursorbibliothek generiert Update-Anweisungen, die eine Zielzeile für die Datenquelle basierend auf deren aktuelle Werte für die zwischengespeicherten Daten oder einen zwischengespeicherten Timestampwert zu identifizieren.  
  
 Die Klassenbibliothek nie verwendet mehrere Rowsets. Aus diesem Grund wenigen **SQLSetPos** Anweisungen werden immer angewendet, um die Zeile 1 des Rowsets.  
  
## <a name="cdatabases"></a>CDatabases  
 Jede `CDatabase` weist einen einzelnen **HDBC**. (Wenn `CDatabase`des `ExecuteSQL` Funktion verwendet wird, ein **Befehls beschäftigt** vorübergehend zugeordnet ist.) Wenn mehrere `CDatabase`des sind erforderlich, mehrere **HDBC**s pro **HENV** unterstützt werden müssen.  
  
 Die Datenbankklassen erfordern die Cursorbibliothek. Dies wirkt sich eine **SQLSetConnections** Aufrufen **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.  
  
 **SQLDriverConnect**, **SQL_DRIVER_COMPLETE** dient der `CDatabase::Open` zum Herstellen der Verbindung mit der Datenquelle.  
  
 Der Treiber muss unterstützen **SQLGetInfo SQL_ODBC_API_CONFORMANCE** >= **SQL_OAC_LEVEL1**, **SQLGetInfo SQL_ODBC_SQL_CONFORMANCE**  >=  **SQL_OSC_MINIMUM**.  
  
 In der Reihenfolge für Transaktionen für unterstützt werden die `CDatabase` und ihre abhängigen Recordsets **SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR** und **SQL_CURSOR_ROLLBACK_BEHAVIOR** benötigen **SQL_CR_PRESERVE**. Andernfalls werden versucht, die Steuerung von Transaktionen auszuführen ignoriert.  
  
 **SQLGetInfo SQL_DATA_SOURCE_READ_ONLY** unterstützt werden müssen. Wenn "Y" zurückgegeben wird, werden keine Update-Operationen für die Datenquelle ausgeführt werden.  
  
 Wenn die `CDatabase` geöffnet ist schreibgeschützt, beim Festlegen der Datenquelle lesen nur wird mit vorgenommen werden **SQLSetConnectOption SQL_ACCESS_MODE**, **SQL_MODE_READ_ONLY**.  
  
 Wenn Bezeichner zitieren benötigen, diese Informationen zurückgegeben werden soll aus den Treiber mit einer **SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR** aufrufen.  
  
 Für das Debuggen verwenden **SQLGetInfo SQL_DBMS_VER** und **SQL_DBMS_NAME** aus dem Treiber abgerufen werden.  
  
 **SQLSetStmtOption SQL_QUERY_TIMEOUT** und **SQL_ASYNC_ENABLE** aufgerufen werden, auf eine `CDatabase`des **HDBC**.  
  
 **SQLError** können Sie einzelne oder alle Argumente NULL aufgerufen werden.  
  
 Natürlich **SQLAllocEnv**, **SQLAllocConnect**, **SQLDisconnect** und **SQLFreeConnect** unterstützt werden müssen.  
  
## <a name="executesql"></a>ExecuteSQL  
 Zusätzlich zum Zuordnen und befreien einen temporären **Befehls beschäftigt**, `ExecuteSQL` Aufrufe **SQLExecDirect**, **SQLFetch**, **SQLNumResultCol**und `SQLMoreResults`. **SQLCancel** aufgerufen werden, auf die **Befehls beschäftigt**.  
  
## <a name="getdatabasename"></a>GetDatabaseName  
 **SQLGetInfo SQL_DATABASE_NAME** aufgerufen wird.  
  
## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, Rollback  
 **SQLSetConnectOption SQL_AUTOCOMMIT** und **SQLTransact SQL_COMMIT**, **SQL_ROLLBACK** und **SQL_AUTOCOMMIT** wird aufgerufen, wenn die Transaktion fordert erfolgen.  
  
## <a name="crecordsets"></a>CRecordsets  
 **SQLAllocStmt:**, **SQLPrepare**, **SQLExecute** (für **öffnen** und **Requery**), **SQLExecDirect**  (für Updatevorgänge) **SQLFreeStmt** unterstützt werden müssen. **SQLNumResultCols** und **SQLDescribeCol** wird für die Resultsets, die zu verschiedenen Zeiten aufgerufen werden.  
  
 **SQLSetParam** umfassend verwendet wird, zum Binden von Parameterdaten und **DATA_AT_EXEC** Funktionalität.  
  
 **SQLBindCol** sehr häufig verwendet, um registrieren Spalte-Datenspeicherorte mit ODBC-Ausgabe.  
  
 Zwei **SQLGetData** Aufrufe zum Abrufen **SQL_LONG_VARCHAR** und **SQL_LONG_VARBINARY** Daten. Der erste Aufruf versucht, durch Aufrufen der Gesamtlänge des Spaltenwerts finden **SQLGetData** mit CbMaxValue 0, jedoch mit einer gültigen PcbValue. Wenn PcbValue enthält **SQL_NO_TOTAL**, wird eine Ausnahme ausgelöst. Andernfalls ein `HGLOBAL` belegt, und eine andere **SQLGetData** Aufruf zum Abrufen des gesamten Resultsets.  
  
## <a name="updating"></a>Wird aktualisiert  
 Wenn das vollständige Sperren angefordert wird, **SQLGetInfo SQL_LOCK_TYPES** abgefragt werden. Wenn **SQL_LCK_EXCLUSIVE** wird nicht unterstützt, wird eine Ausnahme ausgelöst.  
  
 Aktualisiert eine `CRecordset` (**Momentaufnahme** oder **Dynaset**) führt dazu, dass eine zweite **Befehls beschäftigt** zugeordnet werden soll. Zweiter für Treiber, die nicht unterstützen **Befehls beschäftigt**, die Cursorbibliothek wird diese Funktionalität simuliert. Leider Dies bedeutet möglicherweise, in einigen Fällen erzwingen die aktuelle Abfrage auf der ersten **Befehls beschäftigt** bis zum Abschluss vor der Verarbeitung der zweiten **Befehls beschäftigt**Anfrage.  
  
 **SQLFreeStmt SQL_CLOSE** und **SQL_RESET_PARAMS** und **SQLGetCursorName** wird während der Update-Vorgänge aufgerufen werden.  
  
 Treten **CLongBinarys** in der **OutputColumns**, ODBC **DATA_AT_EXEC** Funktionen unterstützt werden muss. Dies schließt zurückgeben **SQL_NEED_DATA** aus **SQLExecDirect**, **SQLParamData** und **SQLPutData**.  
  
 **SQLRowCount** wird aufgerufen, nachdem ausführen, um sicherzustellen, dass nur 1-Datensatz, durch aktualisiert wurde die **SQLExecDirect**.  
  
## <a name="forwardonly-cursors"></a>"ForwardOnly"-Cursor  
 Nur **SQLFetch** ist erforderlich, damit die **verschieben** Vorgänge. Beachten Sie, dass **"forwardOnly"** Cursor unterstützen keine Updates.  
  
## <a name="snapshot-cursors"></a>Momentaufnahmecursor  
 Hardwaresnapshot-Funktionalität erfordert **SQLExtendedFetch** unterstützen. Wie oben bereits erwähnt, wird der ODBC-Cursorbibliothek erkennen, wenn ein Treiber nicht unterstützt wird **SQLExtendedFetch**, und geben Sie die erforderliche Unterstützung selbst.  
  
 **SQLGetInfo**, **SQL_SCROLL_OPTIONS** muss unterstützen **SQL_SO_STATIC**.  
  
## <a name="dynaset-cursors"></a>Dynaset Cursor  
 Im folgenden sehen Sie die minimale Unterstützung erforderlich, um ein Dynaset öffnen:  
  
 **SQLGetInfo**, **SQL_ODBC_VER** muss zurückgeben > "01".  
  
 **SQLGetInfo**, **SQL_SCROLL_OPTIONS** muss unterstützen **SQL_SO_KEYSET_DRIVEN**.  
  
 **SQLGetInfo**, **SQL_ROW_UPDATES** muss "Y" zurück.  
  
 **SQLGetInfo**, **SQL_POSITIONED_UPDATES** muss unterstützen **SQL_PS_POSITIONED_DELETE** und **SQL_PS_POSITIONED_UPDATE**.  
  
 Darüber hinaus, wenn das vollständige Sperren angefordert wird einen Aufruf von **SQLSetPos** mit Irow 1, fRefresh "false" und Bestand **SQL_LCK_EXCLUSIVE** durchgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

