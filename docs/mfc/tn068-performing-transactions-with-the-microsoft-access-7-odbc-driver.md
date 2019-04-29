---
title: 'TN068: Ausführen von Transaktionen mit der Microsoft Access 7 ODBC-Treiber'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: 3121587f85c4ea19cc92e39569008b597d24ea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363790"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Ausführen von Transaktionen mit der Microsoft Access 7 ODBC-Treiber

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt die Durchführung von Transaktionen, bei der Verwendung der MFC-ODBC-Datenbankklassen und der Microsoft Access-7.0-ODBC-Treiber, die in der Microsoft ODBC Desktop-Driver-Pack-Version 3.0 enthalten.

## <a name="overview"></a>Übersicht

Wenn Ihre datenbankanwendung Transaktionen ausführt, achten Sie aufzurufende `CDatabase::BeginTrans` und `CRecordset::Open` in der richtigen Reihenfolge in Ihrer Anwendung. Der Microsoft Access-7.0-Treiber verwendet die Microsoft Jet-Datenbank-Engine und Jet erfordert, dass Ihre Anwendung eine Transaktion für eine beliebige Datenbank, die einen geöffneten Cursor enthält nicht beginnen. Für die MFC-ODBC-Datenbankklassen entspricht ein geöffneten Cursor ein offenes `CRecordset` Objekt.

Wenn Sie ein Recordset vor dem Aufruf öffnen `BeginTrans`, möglicherweise keine Fehlermeldungen angezeigt. Alle Recordsets aktualisiert jedoch Ihre Anwendung nutzt, werden nach dem Aufruf permanent `CRecordset::Update`, und die Updates werden kein Rollback durch Aufrufen von `Rollback`. Um dieses Problem zu vermeiden, rufen Sie `BeginTrans` erste, und klicken Sie dann öffnen Sie das Recordset.

MFC überprüft die Funktionalität des Treibers für Cursorverhalten Commit- und Rollback. Klasse `CDatabase` stellt zwei Memberfunktionen, `GetCursorCommitBehavior` und `GetCursorRollbackBehavior`, um zu bestimmen, die Auswirkungen von einer beliebigen Transaktion auf Ihrem Open `CRecordset` Objekt. Microsoft Access-7.0-ODBC-Treiber diese Memberfunktionen geben `SQL_CB_CLOSE` , da die Access-Treiber die Beibehaltung der Cursor nicht unterstützt. Aus diesem Grund müssen Sie aufrufen `CRecordset::Requery` folgenden eine `CommitTrans` oder `Rollback` Vorgang.

Wenn Sie mehrere Transaktionen nacheinander ausführen möchten, rufen Sie können nicht `Requery` nach der ersten Transaktion und starten Sie dann dem nächsten fort. Schließen Sie das Recordset vor dem nächsten Aufruf von `BeginTrans` um des Jet-Anforderung zu erfüllen. Diese technische Hinweis werden zwei Methoden zur Handhabung dieser Situation beschrieben:

- Schließen das Recordset nach jedem `CommitTrans` oder `Rollback` Vorgang.

- Mithilfe der ODBC-API-Funktion `SQLFreeStmt`.

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Schließen das Recordset nach jedem CommitTrans oder Rollback-Vorgangs

Stellen Sie vor dem Start einer Transaktions können Sie sicher, dass das Recordset-Objekt geschlossen wird. Nach dem Aufruf `BeginTrans`, rufen Sie der Recordsets `Open` Member-Funktion. Schließen Sie das Recordset sofort nach dem Aufruf `CommitTrans` oder `Rollback`. Beachten Sie, dass wiederholte öffnen und schließen das Recordset die Leistung einer Anwendung verlangsamen können.

## <a name="using-sqlfreestmt"></a>SQLFreeStmt verwenden

Sie können auch die ODBC-API-Funktion verwenden `SQLFreeStmt` explizit schließen des Cursors nach Beendigung einer Transaktions. Rufen Sie zum Starten einer anderen Transaktion `BeginTrans` gefolgt von `CRecordset::Requery`. Beim Aufrufen von `SQLFreeStmt`, geben Sie als ersten Parameter die Recordset Befehls beschäftigt und *SQL_CLOSE* als zweiten Parameter. Diese Methode ist schneller als schließen und öffnen das Recordset zu Beginn jeder Transaktion auf. Der folgende Code veranschaulicht die Implementierung dieser Technik:

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

Eine weitere Möglichkeit zum Implementieren dieser Technik ist, Schreiben Sie eine neue Funktion, `RequeryWithBeginTrans`, die Sie aufrufen können, um die nächste Transaktion zu starten, nach dem commit oder Rollback das erste Abonnement. Um eine solche Funktion schreiben möchten, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den Code für `CRecordset::Requery( )` auf die neue Funktion.

2. Fügen Sie die folgende Zeile unmittelbar nach dem Aufruf von `SQLFreeStmt`:

   `m_pDatabase->BeginTrans( );`

Jetzt können Sie diese Funktion zwischen jedem Paar von Transaktionen aufrufen:

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> Dieses Verfahren nicht verwenden, wenn Sie die Membervariablen Recordset müssen *M_strFilter* oder *M_strSort* zwischen den Transaktionen. In diesem Fall schließen Sie das Recordset nach jedem `CommitTrans` oder `Rollback` Vorgang.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
