---
title: 'Recordset: Weitere Informationen zu Aktualisierungen (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ad9042c4001fc1a0e0c8c8d19e5ac53b6312875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-more-about-updates-odbc"></a>Recordset: Weitere Informationen zu Aktualisierungen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Auswirkungen von Updates durch andere Vorgänge, wie Transaktionen,](#_core_how_transactions_affect_updates).  
  
-   [Die Updates und die von anderen Benutzern](#_core_your_updates_and_the_updates_of_other_users).  
  
-   [Weitere Informationen über die Memberfunktionen Update- und Delete](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, einige der Informationen ist nicht relevant. Angenommen, Sie können nicht aufgerufen werden der `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen; allerdings können Sie Transaktionen ausführen. Weitere Informationen über das gesammelte finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_how_other_operations_affect_updates"></a>Auswirkungen von Aktualisierungen in anderen Vorgängen  
 Die Updates werden von Transaktionen faktisch zum Zeitpunkt des Updates durch Schließen des Recordsets vor dem Abschluss einer Transaktions und Durchführen eines Bildlaufs vor dem Abschluss einer Transaktions betroffen.  
  
###  <a name="_core_how_transactions_affect_updates"></a>Auswirkungen von Transaktionen auf Aktualisierungen  
 Neben wie `AddNew`, **bearbeiten**, und **löschen** arbeiten, ist es wichtig zu verstehen, wie die **BeginTrans**, **CommitTrans**, und **Rollback** Memberfunktionen der [CDatabase](../../mfc/reference/cdatabase-class.md) können Sie mit der Update-Funktionen von [CRecordset](../../mfc/reference/crecordset-class.md).  
  
 Standardmäßig Aufrufe von `AddNew` und **bearbeiten** auswirken, die die Datenquelle sofort beim Aufruf **Update**. **Löschen Sie** Aufrufe werden sofort wirksam. Sie können jedoch eine Transaktion einrichten und ein Batch, der solche Aufrufe ausgeführt. Die Updates sind nicht dauerhaft, bis Sie ein Commit ausgeführt. Wenn Sie Ihre Meinung ändern, können Sie die Transaktion ein Commit anstelle von zurücksetzen.  
  
 Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a>Wie das Recordset geschlossen Updates auswirkt.  
 Wenn Sie ein Recordset verwendet werden soll, oder die zugehörigen schließen `CDatabase` Objekt, mit einer Transaktion ausgeführt (Sie haben nicht aufgerufen [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) oder [CDatabase](../../mfc/reference/cdatabase-class.md#rollback)), wird die Transaktion ein Rollback ausgeführt Sichern Sie automatisch (es sei denn, Ihre Datenbank-Back-End-Microsoft Jet-Datenbankmodul).  
  
> [!CAUTION]
>  Wenn Sie das Microsoft Jet-Datenbankmodul verwenden, führt Schließen eines Recordsets innerhalb einer expliziten Transaktion nicht zu Freigeben von Zeilen, die geändert wurden oder sperren, die gespeichert wurden, bis die explizite Transaktion ein Commit oder Rollback ist. Empfohlen wird, Sie öffnen und Schließen von Recordsets innerhalb oder außerhalb einer expliziten Jet-Transaktion.  
  
###  <a name="_core_how_scrolling_affects_updates"></a>Wie wirkt sich auf Durchführen eines Bildlaufs Updates  
 Wenn Sie [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) in einem Recordset Bearbeitungspuffer mit jeder neuen aktuellen Datensatz, der (vorherigen Datensatzes ist dabei nicht zuerst gespeichert) gefüllt ist. Durchführen eines Bildlaufs überspringt Datensätze gelöscht zuvor ein. Wenn Sie einen Bildlauf nach dem Ausführen einer `AddNew` oder **bearbeiten** Aufruf ohne Aufruf **Update**, **CommitTrans**, oder **Rollback** zuerst alle Änderungen sind verloren (keine Warnung auf Sie), wie ein neuer Datensatz in den Bearbeitungspuffer geschaltet wird. Bearbeitungspuffer wird mit dem Zieldatensatz gefüllt, gespeicherte Datensatz wird freigegeben, und für die Datenquelle findet keine Änderung statt. Dies gilt für beide `AddNew` und **bearbeiten**.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a>Die Updates und die Updates von anderen Benutzern  
 Wenn Sie ein Recordset verwenden, um Daten zu aktualisieren, wirkt sich Ihre Updates auf andere Benutzer. Auf ähnliche Weise wirkt sich auf die Updates von anderen Benutzern während der Lebensdauer des Recordsets.  
  
 In einer mehrbenutzerumgebung können andere Benutzer Recordsets öffnen, die einige der dieselben Datensätze enthalten, die Sie im Recordset ausgewählt haben. Änderungen an einen Datensatz, bevor Sie sie abrufen, werden im Recordset widergespiegelt. Da Dynasets einen Datensatz jedes Mal, die Sie ihm einen Bildlauf durchführen abzurufen, Änderungen Dynasets jedes Mal, wenn Sie einen zu einem Datensatz Bildlauf. Abrufen von Momentaufnahmen ein Datensatzes, zu blättern, damit Momentaufnahmen nur für diese Änderungen, die auftreten widerspiegeln, bevor Sie mit dem Datensatz zunächst einen Bildlauf, zum ersten Mal.  
  
 Datensätze, die von anderen Benutzern hinzugefügt werden, nachdem Sie das Recordset geöffnet werden nicht im Recordset angezeigt, es sei denn, Sie abzufragen. Wenn das Recordset ein Dynaset ist, werden Änderungen an vorhandenen Datensätze von anderen Benutzern im Dynaset angezeigt, wenn Sie einen zu der betreffenden Datensatz Bildlauf. Wenn das Recordset eine Momentaufnahme ist, Änderungen nicht mehr anzeigen, bis Sie die Momentaufnahme erneut abgefragt. Wenn Sie verwenden möchten, finden Sie unter Datensätze hinzugefügt oder gelöscht, die von anderen Benutzern in Ihrer Momentaufnahme oder Datensätze, die von anderen Benutzern in Ihrer Dynaset hinzugefügt Aufrufen [CRecordset](../../mfc/reference/crecordset-class.md#requery) das Recordset neu erstellen. (Beachten Sie, dass das Löschen von anderen Benutzern unter "Dynaset" angezeigt.) Sie können auch aufrufen **Requery** Datensätze finden Sie hinzugefügt haben, aber nicht um finden Sie unter Ihr gelöscht.  
  
> [!TIP]
>  Um eine gesamte Momentaufnahme gleichzeitig caching zu erzwingen, rufen Sie `MoveLast` sofort nach dem Öffnen von der Momentaufnahme. Rufen Sie anschließend **MoveFirst** zum Arbeiten mit den Datensätzen. `MoveLast`ist gleich alle Datensätze, aber es sie alle auf einmal abgerufen. Beachten Sie jedoch, dass die Leistung beeinträchtigt werden kann und möglicherweise nicht für einige Treiber erforderlich.  
  
 Die Auswirkungen von Updates für andere Benutzer sind ihre Auswirkungen auf die Sie ähnlich.  
  
##  <a name="_core_more_about_update_and_delete"></a>Weitere Informationen zu Update- und Delete  
 Dieser Abschnitt enthält zusätzliche Informationen zum Arbeiten mit **Update** und **löschen**.  
  
### <a name="update-success-and-failure"></a>Update Erfolg und Fehler  
 Wenn **Update** erfolgreich ist, die `AddNew` oder **bearbeiten** endet. Zum Starten einer `AddNew` oder **bearbeiten** Modus erneut aus, rufen `AddNew` oder **bearbeiten**.  
  
 Wenn **Update** ein Fehler auftritt (gibt **"false"** oder eine Ausnahme auslöst), Sie behalten immer die `AddNew` oder **bearbeiten** Modus, je nachdem welche Funktion Sie zuletzt aufgerufen haben. Sie können dann eine der folgenden Aktionen ausführen:  
  
-   Ändern Sie einen Datenmember des Felds, und wiederholen Sie den **Update** erneut aus.  
  
-   Rufen Sie `AddNew` um den Felddatenmembern auf Null zurückgesetzt, legen Sie den Felddatenmembern Werte fest, und rufen dann **Update** erneut aus.  
  
-   Rufen Sie **bearbeiten** , die Werte erneut zu laden, die im Recordset vor dem ersten Aufruf von Waren `AddNew` oder **bearbeiten**, legen Sie den Felddatenmembern Werte fest und rufen dann **aktualisieren**erneut aus. Nach einer erfolgreichen **Update** aufrufen (außer nach einem `AddNew` aufrufen), die Felddatenmembern behalten ihre neuen Werte.  
  
-   Rufen Sie **verschieben** (einschließlich **verschieben** mit einem Parameter des **AFX_MOVE_REFRESH**, oder 0), die alle leert ändert und beendet alle `AddNew` oder **Bearbeiten** Modus aktiv.  
  
### <a name="update-and-delete"></a>Update- und Delete  
 Dieser Abschnitt gilt für beide **Update** und **löschen**.  
  
 Auf einem **Update** oder **löschen** Vorgang lediglich einen einzelnen Datensatz aktualisiert werden soll. Dieser Datensatz wird der aktuelle Datensatz, der die Datenwerte in den Feldern des Recordset-Objekts entspricht. Wenn es aus einem unbestimmten Grund keine Datensätze oder betroffen sind mehr als ein Datensatz ist, eine Ausnahme ausgelöst wird, enthält die folgenden **RETCODE** Werte:  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED**  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**  
  
 Wenn diese Ausnahmen ausgelöst werden, verbleiben Sie in der `AddNew` oder **bearbeiten** Status Sie beim Aufrufen haben **Update** oder **löschen**. Hier sind die häufigsten Szenarien, in denen Sie diese Ausnahmen angezeigt werden. Sie sind am wahrscheinlichsten finden Sie unter:  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED** bei optimistisches Sperrverhalten und ein anderer Benutzer Verwendung wurde geändert, den Datensatz in einer Weise, die verhindert, dass das Framework identifizieren den richtigen Datensatz zu aktualisieren oder zu löschen.  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** bei die Tabelle aktualisiert werden soll, wurde kein Primärschlüssel oder eindeutigen Index, und Sie haben nicht genügend Spalten im Recordset zur eindeutigen Identifizierung einer Zeile einer Tabelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md)