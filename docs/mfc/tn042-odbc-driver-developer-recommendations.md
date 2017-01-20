---
title: "TN042: Empfehlungen f&#252;r ODBC-Treiberentwickler"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenbanken [C++], ODBC"
  - "ODBC-Treiber [C++], Schreiben"
  - "TN042"
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# TN042: Empfehlungen f&#252;r ODBC-Treiberentwickler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt Richtlinien für ODBC\-Treiber\-Writer.  Er beschreibt allgemeine Anforderungen und Annahmen aus ODBC\-Funktionalität, dass die MFC\-Datenbankklassen machen, und die verschiedenen erwarteten Semantik\- Details.  Die erforderliche Treiberfunktionalität, um die drei Modi geöffneten `CRecordset` \(**forwardOnly**, **Momentaufnahme** und **dynaset**\) zu unterstützen werden beschrieben.  
  
## Cursorbibliothek ODBC  
 Die MFC\-Datenbankklassen bieten dem Benutzer Funktionen dar, die in vielen Fällen die Funktionalität übertrifft, die von den meisten Ebene 1 ODBC\-Treibern bereitgestellt wird.  Glücklicherweise überlagert sich Cursorbibliothek ODBC zwischen den Datenbankklassen und dem Treiber und stellt automatisch viele dieser zusätzlichen Funktionen.  
  
 Beispielsweise unterstützen die meisten 1.0 Treiber nicht Rückwärtsscrollen.  Die Cursorbibliothek kann erkennen, und dieses wird Zeilen vom Treiber zwischenspeichern und diese darstellt, wie auf FETCH\_PREV\-Aufrufen in **SQLExtendedFetch** angefordert.  
  
 Ein anderes wichtiges Beispiel der Cursorbibliotheksabhängigkeit ist positionierbare Aktualisierungen.  Die meisten verfügen nicht 1.0 Treiber positionierbare Aktualisierungen, die Cursorbibliothek generiert Aktualisierungsanweisungen, die eine Zielzeile auf der Datenquelle angeben, die nach den aktuellen Werten der zwischengespeicherten Daten basiert wird, oder einen zwischengespeicherten Timestampwert.  
  
 Die Klassenbibliothek nutzt nie mehrere Rowsets aus.  Deshalb werden die wenigsten **SQLSetPos**\-Anweisungen immer angewendet, dass 1 % des Rowsets zu Zeile.  
  
## CDatabases  
 Jedes `CDatabase` ordnet einzelnen **HDBC**. \(Wenn Funktion `CDatabase``ExecuteSQL` verwendet wird, ist vorübergehend **HSTMT** zugeordnet.\) Somit, wenn mehrere `CDatabase`s erforderlich sind, müssen mehrere **HDBC**s pro **HENV** unterstützt werden.  
  
 Die Datenbankklassen benötigen die Cursorbibliothek.  Dies wird in einem **SQLSetConnections** \- Aufruf **SQL\_ODBC\_CURSORS**, **SQL\_CUR\_USE\_ODBC** übernommen.  
  
 **SQLDriverConnect**, **SQL\_DRIVER\_COMPLETE** wird von `CDatabase::Open` verwendet, um die Verbindung zur Datenquelle einzurichten.  
  
 Der Treiber muss **SQLGetInfo SQL\_ODBC\_API\_CONFORMANCE** \>\= **SQL\_OAC\_LEVEL1**, **SQLGetInfo SQL\_ODBC\_SQL\_CONFORMANCE** \>\= **SQL\_OSC\_MINIMUM** unterstützt.  
  
 Damit Transaktionen für `CDatabase` und die abhängigen Recordsets unterstützt werden können, müssen **SQLGetInfo** und **SQL\_CURSOR\_COMMIT\_BEHAVIORSQL\_CURSOR\_ROLLBACK\_BEHAVIORSQL\_CR\_PRESERVE** verfügen.  Andernfalls versucht werden, Transaktionssteuerelement auszuführen ignoriert.  
  
 **SQLGetInfo SQL\_DATA\_SOURCE\_READ\_ONLY** muss unterstützt werden.  Wenn es "Y" zurückgibt, werden keine Aktualisierungsvorgänge in der Datenquelle ausgeführt.  
  
 Wenn `CDatabase` geöffnetes schreibgeschützt ist, wird versucht, die schreibgeschützte Datenquelle festzulegen mit **SQLSetConnectOption SQL\_ACCESS\_MODE**, **SQL\_MODE\_READ\_ONLY** ausgeführt.  
  
 Wenn Bezeichner der Veranschlagung benötigen, sollten diese Informationen vom Treiber mit einem Aufruf **SQLGetInfo SQL\_IDENTIFIER\_QUOTE\_CHAR** zurückgegeben werden.  
  
 Für Debugzwecke werden **SQLGetInfo SQL\_DBMS\_VER** und **SQL\_DBMS\_NAME** vom Treiber abgerufen.  
  
 **SQLSetStmtOption SQL\_QUERY\_TIMEOUT** und **SQL\_ASYNC\_ENABLE** werden von `CDatabase`**HDBC** aufgerufen werden.  
  
 **SQLError** wird mit allen aufgerufen werden, oder alle Argumente wird ungültig.  
  
 Natürlich müssen **SQLAllocEnv**, **SQLAllocConnect**, **SQLDisconnect** und **SQLFreeConnect** unterstützt werden.  
  
## ExecuteSQL  
 Zusätzlich zum Belegen und zum Freigeben von temporären **HSTMT** ruft `ExecuteSQL`, **SQLExecDirect**, **SQLFetch**, **SQLNumResultCol** und `SQLMoreResults` auf.  **SQLCancel** wird auf **HSTMT** aufgerufen werden.  
  
## GetDatabaseName  
 **SQLGetInfo SQL\_DATABASE\_NAME** wird aufgerufen.  
  
## BeginTrans, CommitTrans, Rollback\-  
 **SQLSetConnectOption** und **SQL\_AUTOCOMMITSQLTransact SQL\_COMMIT**, **SQL\_ROLLBACK** und **SQL\_AUTOCOMMIT** werden aufgerufen, wenn Transaktionsanforderungen gemacht werden.  
  
## CRecordsets  
 **SQLAllocStmt**, **SQLPrepare**, **SQLExecute** \(für **Öffnen** und **Requery**\), **SQLExecDirect** \(für Aktualisierungsvorgänge\), **SQLFreeStmt** muss unterstützt werden.  Damit **SQLNumResultCols** und **SQLDescribeCol** werden das Resultset zu verschiedenen Zeitpunkten aufgerufen.  
  
 **SQLSetParam** wird für zahlreiche für Bindungsparameterdaten und **DATA\_AT\_EXEC**\-Funktionen verwendet.  
  
 **SQLBindCol** wird für zahlreiche verwendet, um Ausgabespaltendatenspeicherungsspeicherorte mit ODBC zu registrieren.  
  
 Zwei **SQLGetData** Aufrufe werden verwendet, um **SQL\_LONG\_VARCHAR** und **SQL\_LONG\_VARBINARY** Daten abzurufen.  Die Versuche im ersten Aufruf, die Gesamtlänge des Spaltenwerts durch Aufrufen von **SQLGetData** mit cbMaxValue von 0, aber mit einem gültigen pcbValue zu suchen.  Wenn pcbValue **SQL\_NO\_TOTAL** enthält, wird eine Ausnahme ausgelöst.  Andernfalls wird `HGLOBAL` zugeordnet und ein anderer **SQLGetData** aufgerufen, um das ganze Ergebnis abzurufen.  
  
## Aktualisieren  
 Wenn vollständig Sperren angefordert wird, wird **SQLGetInfoSQL\_LOCK\_TYPES** abgefragt.  Wenn **SQL\_LCK\_EXCLUSIVE** nicht unterstützt wird, wird eine Ausnahme ausgelöst.  
  
 Versucht, `CRecordset` zu aktualisieren \(**Momentaufnahme** oder **dynaset**\) führen eine Sekunde **HSTMT** zugeordnet.  Für Treiber, die nicht zweites **HSTMT** vorsehen, simuliert die Cursorbibliothek diese Funktionalität.  Leider bedeutet dies möglicherweise gelegentlich das Erzwingen der aktuellen Abfrage auf ersten **HSTMT** abgeschlossen, bevor die zweite **HSTMT** Anforderung verarbeitet.  
  
 **SQLFreeStmt SQL\_CLOSE** und **SQL\_RESET\_PARAMS** und **SQLGetCursorName** werden während der Aktualisierungsvorgänge aufgerufen.  
  
 Wenn es **CLongBinarys** in **outputColumns** gibt, muss **DATA\_AT\_EXEC**\-Funktionen unterstützt werden.  Ebenfalls Rückgabe von **SQL\_NEED\_DATA** von **SQLExecDirect**, **SQLParamData** und **SQLPutData** ein.  
  
 **SQLRowCount** aufgerufen wird, nachdem von sicherzustellen ausgeführt, dass nur 1 Datensatz durch **SQLExecDirect** aktualisiert wurde.  
  
## ForwardOnly\-Cursor  
 Nur **SQLFetch** ist für die **Verschieben** Operationen erforderlich.  Beachten Sie, dass **forwardOnly** Cursor keine Aktualisierungen unterstützen.  
  
## Momentaufnahme\-Cursor  
 Momentaufnahmefunktionalität erfordert **SQLExtendedFetch** Unterstützung.  Wie oben erwähnt, erkennt die ODBC\-Cursorbibliothek, wann ein Treiber **SQLExtendedFetch** nicht unterstützt, und es bleibt die erforderliche Unterstützung selbst.  
  
 **SQLGetInfo**, **SQL\_SCROLL\_OPTIONS** muss **SQL\_SO\_STATIC** unterstützt.  
  
## Dynaset\-Cursor  
 Unten ist die minimale Unterstützung, die erforderlich ist, ein Dynaset zu öffnen:  
  
 **SQLGetInfo**, **SQL\_ODBC\_VER** muss "01 " zurückgegeben \>.  
  
 **SQLGetInfo**, **SQL\_SCROLL\_OPTIONS** muss **SQL\_SO\_KEYSET\_DRIVEN** unterstützt.  
  
 **SQLGetInfo**, **SQL\_ROW\_UPDATES** muss "Y" zurückgegeben.  
  
 **SQLGetInfo**, **SQL\_POSITIONED\_UPDATES** muss **SQL\_PS\_POSITIONED\_DELETE** und **SQL\_PS\_POSITIONED\_UPDATE** vorsehen.  
  
 Wenn vollständig Sperren angefordert wird, wird ein Aufruf von **SQLSetPos** mit irow 1, fRefresh FALSE und Anzahl von **SQL\_LCK\_EXCLUSIVE** vorgenommen.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)