---
title: 'TN042: Empfehlungen für ODBC-Treiberentwickler'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 462f8229d995add79f48f34b7f81257710b4a8b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276610"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: Empfehlungen für ODBC-Treiberentwickler

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis werden die Richtlinien für Autoren von ODBC-Treiber beschrieben. Es erläutert allgemeine Anforderungen und Annahmen des ODBC-Funktionen, die die MFC-Datenbankklassen treffen und verschiedene erwartete semantische Details. Benötigten Treiberfunktionen zur Unterstützung von drei `CRecordset` Modi öffnen (**"forwardOnly"**, **Momentaufnahme** und **Dynaset**) beschrieben werden.

## <a name="odbcs-cursor-library"></a>Der ODBC-Cursorbibliothek

Die MFC-Datenbankklassen stellen Funktionen, die dem Benutzer, der in vielen Fällen die Funktionalität von ODBC-Treiber für die meisten Ebene 1 übersteigt. Glücklicherweise ODBCs-Cursorbibliothek überlagert selbst zwischen den Datenbankklassen und der Treiber und wird automatisch ein Großteil dieser zusätzlichen Funktionalität bereitstellen.

Z. B. unterstützt die meisten 1.0-Treiber nicht rückwärts-scrollen. Die Cursorbibliothek kann erkennen, und wird Zwischenspeichern Zeilen aus dem Treiber und präsentieren auf FETCH_PREV Aufrufen in Anforderung `SQLExtendedFetch`.

Ein weiteres Beispiel für wichtiges Abhängigkeit für Cursor-Bibliothek ist positionierte Updates. Die meisten 1.0 Treiber auch keine positionierten Updates, aber die Cursorbibliothek generiert Update-Anweisungen, die eine Zielzeile für die Datenquelle basierend auf der die aktuellen Werte für zwischengespeicherte Daten oder einen zwischengespeicherten Timestamp-Wert zu identifizieren.

Die Class-Bibliothek noch nie verwendet mehrere Rowsets. Aus diesem Grund die nur einige `SQLSetPos` Anweisungen werden immer angewendet, um die Zeile 1 des Rowsets.

## <a name="cdatabases"></a>CDatabases

Jede `CDatabase` weist eine einzelne **HDBC**. (Wenn `CDatabase`des `ExecuteSQL` Funktion wird verwendet, eine **Befehls beschäftigt** vorübergehend zugeordnet ist.) Wenn mehrere `CDatabase`des sind erforderlich, mehrere **HDBC**s pro **HENV** unterstützt werden müssen.

Die Datenbankklassen erfordern die Cursorbibliothek. Diese Berechnung sieht einem `SQLSetConnections` Aufrufen **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** dient der `CDatabase::Open` zum Herstellen der Verbindung mit der Datenquelle.

Der Treiber muss unterstützen `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**, `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**.

In der Reihenfolge für Transaktionen unterstützt werden die `CDatabase` und ihre abhängigen Recordsets, `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` und **SQL_CURSOR_ROLLBACK_BEHAVIOR** benötigen **SQL_CR_PRESERVE**. Andernfalls werden versucht, führen Sie die transaktionssteuerung ignoriert.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` muss unterstützt werden. Wenn sie "Y" zurückgibt, werden keine Update-Operationen für die Datenquelle ausgeführt werden.

Wenn die `CDatabase` geöffnet ist schreibgeschützt, beim Festlegen der Datenquelle lesen nur werden erfolgt mit `SQLSetConnectOption SQL_ACCESS_MODE`, **SQL_MODE_READ_ONLY**.

Wenn Bezeichner zitieren benötigen, diese Informationen zurückgegeben werden sollen aus dem Treiber mit einer `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` aufrufen.

Für das Debuggen `SQLGetInfo SQL_DBMS_VER` und **SQL_DBMS_NAME** aus dem Treiber abgerufen werden.

`SQLSetStmtOption SQL_QUERY_TIMEOUT` und **SQL_ASYNC_ENABLE** kann aufgerufen werden, auf eine `CDatabase`des **HDBC**.

`SQLError` möglicherweise einige oder alle Argumente NULL aufgerufen werden.

Natürlich `SQLAllocEnv`, `SQLAllocConnect`, `SQLDisconnect` und `SQLFreeConnect` unterstützt werden müssen.

## <a name="executesql"></a>ExecuteSQL

Zusätzlich zum Zuordnen und freigeben einen temporären **Befehls beschäftigt**, `ExecuteSQL` Aufrufe `SQLExecDirect`, `SQLFetch`, `SQLNumResultCol` und `SQLMoreResults`. `SQLCancel` kann aufgerufen werden, auf die **Befehls beschäftigt**.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` wird aufgerufen.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, Rollback

`SQLSetConnectOption SQL_AUTOCOMMIT` und `SQLTransact SQL_COMMIT`, **SQL_ROLLBACK** und **SQL_AUTOCOMMIT** wird aufgerufen, wenn die transaktionsanforderungen gestellt werden.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare`, `SQLExecute` (Für `Open` und `Requery`), `SQLExecDirect` (für Updatevorgänge) `SQLFreeStmt` unterstützt werden müssen. `SQLNumResultCols` und `SQLDescribeCol` wird für die Resultsets, die zu verschiedenen Zeiten aufgerufen werden.

`SQLSetParam` wird häufig verwendet, zum Binden von Daten von Parametern und **DATA_AT_EXEC** Funktionalität.

`SQLBindCol` wird häufig verwendet, um die Registrierung Spalte Datenspeicherorte mit dem ODBC-Ausgabe.

Zwei `SQLGetData` Aufrufe werden verwendet, um das Abrufen von **SQL_LONG_VARCHAR** und **SQL_LONG_VARBINARY** Daten. Der erste Aufruf versucht wird, finden Sie die Gesamtlänge des Spaltenwerts durch Aufrufen von `SQLGetData` mit CbMaxValue 0, jedoch mit einem gültigen PcbValue. Wenn PcbValue enthält **SQL_NO_TOTAL**, wird eine Ausnahme ausgelöst. Andernfalls ein **HGLOBAL** zugeordnet ist, und ein weiteres `SQLGetData` Aufruf zum Abrufen des gesamten Resultsets.

## <a name="updating"></a>Wird aktualisiert

Wenn pessimistische Sperrung angefordert wird, `SQLGetInfo SQL_LOCK_TYPES` wird abgefragt werden. Wenn **SQL_LCK_EXCLUSIVE** wird nicht unterstützt, wird eine Ausnahme ausgelöst werden.

Versucht, zu aktualisieren eine `CRecordset` (**Momentaufnahme** oder **Dynaset**) führt dazu, dass eine zweite **Befehls beschäftigt** zugeordnet werden. Zweiter für Treiber, die nicht unterstützen **Befehls beschäftigt**, simuliert die Cursorbibliothek diese Funktionalität. Leider kann manchmal dies erzwingen die aktuelle Abfrage auf der ersten **Befehls beschäftigt** bis zum Abschluss vor der Verarbeitung der zweiten **Befehls beschäftigt**Anforderung.

`SQLFreeStmt SQL_CLOSE` und **SQL_RESET_PARAMS** und `SQLGetCursorName` wird während der Update-Vorgänge aufgerufen werden.

Treten **CLongBinarys** in die **OutputColumns**, der ODBC- **DATA_AT_EXEC** Funktionen unterstützt werden muss. Dies schließt zurückgeben **SQL_NEED_DATA** aus `SQLExecDirect`, `SQLParamData` und `SQLPutData`.

`SQLRowCount` wird aufgerufen, nachdem um sicherzustellen, dass nur noch 1 Datensatz aktualisiert wurde, indem Sie Ausführung der `SQLExecDirect`.

## <a name="forwardonly-cursors"></a>"ForwardOnly"-Cursor

Nur `SQLFetch` ist erforderlich, damit die `Move` Vorgänge. Beachten Sie, dass **"forwardOnly"** -Cursor unterstützen nicht die Updates.

## <a name="snapshot-cursors"></a>Momentaufnahmecursor

Hardwaresnapshot-Funktionalität erfordert `SQLExtendedFetch` unterstützen. Wie bereits erwähnt, wird die ODBC-Cursorbibliothek erkennen, wenn ein Treiber nicht unterstützt `SQLExtendedFetch`, und geben Sie die benötigten Supportdateien für sich selbst.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** muss unterstützen **SQL_SO_STATIC**.

## <a name="dynaset-cursors"></a>Dynaset Cursor

Im folgenden sehen Sie die minimale Unterstützung erforderlich, um ein Dynaset öffnen:

`SQLGetInfo`, **SQL_ODBC_VER** zurückgeben > "01".

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** muss unterstützen **SQL_SO_KEYSET_DRIVEN**.

`SQLGetInfo`, **SQL_ROW_UPDATES** must return "Y".

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** muss unterstützen **SQL_PS_POSITIONED_DELETE** und **SQL_PS_POSITIONED_UPDATE**.

Darüber hinaus, wenn pessimistische Sperrung angefordert wird einen Aufruf von `SQLSetPos` mit Irow 1, fRefresh "false" und Bestand **SQL_LCK_EXCLUSIVE** erfolgen.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
