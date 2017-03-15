---
title: "TN068: Ausf&#252;hren von Transaktionen mit dem Microsoft Access 7 ODBC-Treiber | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN068"
  - "Transaktionen, Aufrufen von BeginTrans"
  - "Transaktionen, Microsoft Access"
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN068: Ausf&#252;hren von Transaktionen mit dem Microsoft Access 7 ODBC-Treiber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird beschrieben, wie Transaktionen ausgeführt wird, wenn er die MFC\-ODBC\-Datenbankklassen und den Microsoft Access 7.0\-ODBC\-Treiber verwendet, die in der Treiber\-Packversion 3.0 Microsoft ODBC Tischplatteneingeschlossen werden.  
  
## Übersicht  
 Wenn die Datenbankanwendung Transaktionen ausgeführt wird, müssen Sie darauf achten, dass `CDatabase::BeginTrans` und `CRecordset::Open` in der richtigen Sequenz in der Anwendung aufrufen.  Der Microsoft Access 7.0\-Treiber verwendet das Microsoft Jet\-Datenbankmodul Jet erfordert, und dass die Anwendung, eine Transaktion für jede Datenbank nicht zu beginnen, die einen offenen Cursor hat.  Für die MFC\-ODBC\-Datenbankklassen entspricht ein offener Cursor mit geöffneten `CRecordset` ein Objekt aus.  
  
 Wenn Sie ein Recordset öffnen, bevor Sie **BeginTrans** aufrufen, wird ggf. keine Fehlermeldungen.  jedoch aktualisiert jedes beliebige Recordset der Anwendung macht Sie dauerhaft, nachdem `CRecordset::Update` aufgerufen hat, und die Aktualisierungen nicht zurückgesetzt, indem **Zurücksetzung** aufruft.  Um dieses Problem zu vermeiden, müssen Sie zuerst **BeginTrans** aufrufen und öffnen dann das Recordset.  
  
 MFC überprüft die Treiberfunktionalität für Cursor\-Commit und Rollbackverhalten.  `CDatabase`\-Klasse stellt zwei Memberfunktionen bereit, `GetCursorCommitBehavior` und `GetCursorRollbackBehavior` bereit, um die Auswirkungen einer Transaktion zu bestimmen auf das geöffnete `CRecordset`\-Objekt.  Für den Microsoft Access 7.0\-ODBC\-Treiber geben dieser Memberfunktionen `SQL_CB_CLOSE` zurück, da der Zugriffstreiber nicht Cursor\-Beibehaltung unterstützt.  Daher müssen Sie `CRecordset::Requery` aufrufen, die einen **CommitTrans** oder **Zurücksetzung** Vorgang folgt.  
  
 Wenn Sie nacheinander mehrere Transaktionen durchführen müssen, können Sie **Requery** nach der ersten Transaktion nicht aufrufen und Folgendes dann starten.  Sie müssen das Recordset bevor der nächste Aufruf von **BeginTrans** schließen, um Jet Anforderung erfüllen.  Dieser technische Hinweis beschreibt zwei Methoden der Behandlung dieser Situation:  
  
-   Schließen des Recordsets nach jedem Vorgang **CommitTrans** oder **Zurücksetzung**.  
  
-   unter Verwendung der ODBC\-API\-Funktion **SQLFreeStmt**.  
  
## Schließen des Recordsets nach jedem Vorgang CommitTrans oder des Rollbacks  
 Bevor Sie eine Transaktion beginnen, müssen Sie sicherstellen, dass das Recordset geschlossen wird.  Nachdem Sie mit **BeginTrans** aufgerufen haben, rufen Sie die **Öffnen**\-Memberfunktion des Recordsets auf.  Schließen Sie das Recordset unmittelbar nach dem Aufrufen von **CommitTrans** oder **Zurücksetzung**.  Beachten Sie, dass das Recordset wiederholt öffnen und schließen die Leistung einer Anwendung verlangsamen können.  
  
## Verwenden SQLFreeStmt  
 nach dem Ende einer Transaktion Sie können die ODBC\-API\-Funktion **SQLFreeStmt** auch verwenden, um den Cursor explizit zu schließen.  Um einer anderen Transaktion zu starten, rufen Sie **BeginTrans** gefolgt von `CRecordset::Requery` auf.  Wenn Sie **SQLFreeStmt** aufrufen, müssen Sie dem HSTMT des Recordsets als ersten Parameter und **SQL\_CLOSE** geben als zweiten Parameter.  Diese Methode ist schneller, als das Recordset zu Beginn jeder Transaktion Schließen und Öffnen.  Der folgende Code zeigt, wie diese Methode implementiert:  
  
```  
CMyDatabase db;  
db.Open( "MYDATASOURCE" );  
CMyRecordset rs( &db );  
  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor  
::SQLFreeStmt( rs.m_hstmt, SQL_CLOSE );  
  
// start transaction 2  
db.BeginTrans( );  
  
// now get the result set  
rs.Requery( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  
  
rs.Close( );  
db.Close( );  
```  
  
 Eine andere Methode, dieses Verfahren zu implementieren ist, eine neue Funktion, **RequeryWithBeginTrans** zu schreiben, die Sie aufrufen können, um die folgende Transaktionen zu starten, nachdem Sie das erste und Rollback verpflichten.  Um eine solche Funktion schreiben, verwenden Sie die folgenden Schritte:  
  
1.  Kopieren Sie den Code für eine **CRecordset::Requery\( \)** der neuen Funktion.  
  
2.  Fügen Sie die folgende Zeile direkt unter dem Aufruf **SQLFreeStmt** hinzu:  
  
     `m_pDatabase->BeginTrans( );`  
  
 Jetzt können Sie diese Funktion zwischen jedem Paar Transaktionen aufrufen:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor, start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  // or Rollback( )  
```  
  
> [!NOTE]
>  Verwenden Sie diese Vorgehensweise, wenn Sie die Recordsetmembervariablen **m\_strFilter** oder `m_strSort` zwischen Transaktionen ändern müssen.  In diesem Fall sollten Sie das Recordset nach jedem **CommitTrans** oder **Zurücksetzung** Vorgang schließen.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)