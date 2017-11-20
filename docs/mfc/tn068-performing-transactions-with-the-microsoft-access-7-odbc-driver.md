---
title: "TN068: Ausführen von Transaktionen mit dem Microsoft Access 7 ODBC-Treiber | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.data.odbc
dev_langs: C++
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3920aea4d4d08b088831b558b220a6b2052fb7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Ausführen von Transaktionen mit dem Microsoft Access 7 ODBC-Treiber
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Durchführung von Transaktionen bei Verwendung der MFC-ODBC-Datenbankklassen und der Microsoft Access 7.0 ODBC-Treiber, die in der Microsoft ODBC-Desktop-Treiber-Pack-Version 3.0 enthalten.  
  
## <a name="overview"></a>Übersicht  
 Wenn Ihre datenbankanwendung Transaktionen ausgeführt werden, achten Sie aufrufen `CDatabase::BeginTrans` und `CRecordset::Open` in der richtigen Reihenfolge in der Anwendung. Der Microsoft Access 7.0-Treiber verwendet den Microsoft Jet-Datenbankmodul und Jet erfordert, dass Ihre Anwendung eine Transaktion für jede Datenbank, die einen geöffneten Cursor wurde nicht beginnen. Für die MFC-ODBC-Datenbankklassen entspricht ein geöffneten Cursor ein offenes `CRecordset` Objekt.  
  
 Wenn Sie ein Recordset vor dem Aufruf öffnen **BeginTrans**, möglicherweise keine Fehlermeldungen angezeigt. Allerdings alle Recordset aktualisiert Ihre Anwendung vereinfacht werden permanente nach dem Aufruf `CRecordset::Update`, und die Updates werden kein Rollback durch Aufrufen von **Rollback**. Um dieses Problem zu vermeiden, rufen Sie **BeginTrans** erste, und öffnen Sie das Recordset.  
  
 MFC überprüft die Funktionalität des Treibers für Cursorverhalten Commit- und Rollback. Klasse `CDatabase` stellt zwei Memberfunktionen `GetCursorCommitBehavior` und `GetCursorRollbackBehavior`, um zu bestimmen, die Auswirkungen von Transaktionen auf geöffneter `CRecordset` Objekt. Microsoft Access 7.0-ODBC-Treiber diese Memberfunktionen geben `SQL_CB_CLOSE` , da die Access-Treiber die Beibehaltung der Cursor nicht unterstützt. Aus diesem Grund müssen Sie aufrufen `CRecordset::Requery` folgende eine **CommitTrans** oder **Rollback** Vorgang.  
  
 Wenn Sie mehrere Transaktionen nacheinander ausführen müssen, rufen Sie können nicht **Requery** nach der ersten Transaktion und der nächsten dann neu gestartet. Sie müssen das Recordset vor dem nächsten Aufruf von schließen **BeginTrans** um des Jet-Anforderung zu erfüllen. In diesem technischen Hinweis werden zwei Methoden zur Handhabung dieser Situation beschrieben:  
  
-   Schließen das Recordset nach jedem **CommitTrans** oder **Rollback** Vorgang.  
  
-   Mithilfe der ODBC-API-Funktion **SQLFreeStmt**.  
  
## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Schließen das Recordset nach jedem CommitTrans oder Rollback-Vorgangs  
 Vor dem Start einer Transaktions: Stellen Sie sicher, dass das Recordsetobjekt geschlossen wird. Nach dem Aufruf **BeginTrans**, rufen Sie des Recordsets **öffnen** Memberfunktion. Schließen Sie das Recordset sofort nach dem Aufruf **CommitTrans** oder **Rollback**. Beachten Sie, dass wiederholte öffnen und schließen das Recordset die Leistung einer Anwendung verlangsamen können.  
  
## <a name="using-sqlfreestmt"></a>SQLFreeStmt verwenden  
 Sie können auch die ODBC-API-Funktion **SQLFreeStmt** explizit schließen des Cursors nach dem Beenden einer Transaktions. Um eine andere Transaktion zu starten, rufen **BeginTrans** gefolgt von `CRecordset::Requery`. Beim Aufrufen von **SQLFreeStmt**, Sie müssen das Recordset Befehls beschäftigt als erster Parameter angeben und **SQL_CLOSE** als zweiten Parameter. Diese Methode ist schneller als schließen und öffnen das Recordset am Anfang jeder Transaktion auf. Der folgende Code zeigt, wie diese Technik implementiert wird:  
  
```  
CMyDatabase db;  
db.Open("MYDATASOURCE");

CMyRecordset rs(&db);

 
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
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
  
 Eine weitere Möglichkeit zum Implementieren dieser Technik ist, Schreiben Sie eine neue Funktion **RequeryWithBeginTrans**, die Sie aufrufen können, um die nächste Transaktion zu starten, nachdem Sie einen commit oder Rollback der ersten Aktivität. Um eine solche Funktion schreiben, müssen Sie die folgenden Schritte aus:  
  
1.  Kopieren Sie den Code für **CRecordset ()** an die neue Funktion.  
  
2.  Fügen Sie die folgende Zeile unmittelbar nach dem Aufruf von **SQLFreeStmt**:  
  
 `m_pDatabase->BeginTrans( );`  
  
 Jetzt können Sie diese Funktion zwischen jedem Paar von Transaktionen aufrufen:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor,
    start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();
*// or Rollback()  
```  
  
> [!NOTE]
>  Verwenden Sie dieses Verfahren nicht, wenn Sie die Membervariablen Recordset ändern müssen **M_strFilter** oder `m_strSort` zwischen den Transaktionen. In diesem Fall sollten Sie das Recordset schließen Sie nach jedem **CommitTrans** oder **Rollback** Vorgang.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

