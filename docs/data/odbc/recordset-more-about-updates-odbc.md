---
title: 'Recordset: Weitere Informationen zu Aktualisierungen (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e09ab80d8f525412d96d696c6ff3cb02926913d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034979"
---
# <a name="recordset-more-about-updates-odbc"></a>Recordset: Weitere Informationen zu Aktualisierungen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
In diesem Thema wird Folgendes erläutert:  
  
- [Auswirkungen auf andere Vorgänge, wie Transaktionen, Aktualisierungen](#_core_how_transactions_affect_updates).  
  
- [Ihre Updates und anderer Benutzer](#_core_your_updates_and_the_updates_of_other_users).  
  
- [Weitere Informationen zu den Update- und Delete-Memberfunktionen](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die massenzeilenabruf implementiert haben, einige der Informationen ist nicht relevant. Angenommen, Sie können nicht aufrufen, die `AddNew`, `Edit`, `Delete`, und `Update` Memberfunktionen; allerdings können Sie Transaktionen ausführen. Weitere Informationen zu gesammelten Abrufens von Zeilen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_how_other_operations_affect_updates"></a> Auswirkungen von Aktualisierungen in anderen Vorgängen  

Ihre Updates sind von Transaktionen in Kraft zum Zeitpunkt des Updates durch Schließen des Recordsets vor dem Abschluss einer Transaktions und Durchführen eines Bildlaufs vor dem Abschluss einer Transaktions betroffen.  
  
###  <a name="_core_how_transactions_affect_updates"></a> Auswirkungen von Transaktionen auf Aktualisierungen  

Über Kenntnisse wie `AddNew`, `Edit`, und `Delete` Arbeit, es ist wichtig zu verstehen, wie die `BeginTrans`, `CommitTrans`, und `Rollback` Memberfunktionen der [CDatabase](../../mfc/reference/cdatabase-class.md) funktionieren mit die Funktionen der Aktualisierung der [CRecordset](../../mfc/reference/crecordset-class.md).  
  
Aufrufe in der Standardeinstellung `AddNew` und `Edit` Auswirkung, die die Datenquelle sofort beim Aufruf `Update`. `Delete` Aufrufe werden sofort wirksam. Sie können jedoch eine Transaktion einrichten und Ausführen ein Batches von solche Aufrufe. Die Updates sind nicht dauerhaft, bis ein Commit ausgeführt. Wenn Sie Ihre Meinung ändern, können Sie die Transaktion durch ein Commit zurücksetzen.  
  
Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> Schließen das Recordset Updates Auswirkungen  

Wenn Sie ein Recordset verwendet werden soll, oder die zugehörigen schließen `CDatabase` Objekt mit einer Transaktion ausgeführt (nicht aufgerufen [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) oder [CDatabase](../../mfc/reference/cdatabase-class.md#rollback)), die Transaktion wird ein Rollback ausgeführt. Sichern Sie automatisch (sofern Ihre Datenbank-Back-End der Microsoft Jet-Datenbank-Engine darstellt).  
  
> [!CAUTION]
>  Wenn Sie die Microsoft Jet-Datenbank-Engine verwenden, führt Schließen eines Recordsets innerhalb einer expliziten Transaktion nicht zu Freigeben von Zeilen, die geändert wurden oder sperren, die gespeichert wurden, bis die explizite Transaktion ein Commit oder Rollback ist. Empfohlen wird, Sie öffnen und Schließen von Recordsets innerhalb oder außerhalb einer expliziten Jet-Transaktion.  
  
###  <a name="_core_how_scrolling_affects_updates"></a> Durchführen eines Bildlaufs Updates Auswirkungen  

Wenn Sie [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) eines Recordsets Bearbeitungspuffer mit jeder neuen aktuellen Datensatz (des vorherigen Datensatzes ist dabei nicht zuerst gespeichert) gefüllt ist. Scrollen vorher gelöschte Datensätze überspringt. Wenn Sie nach dem Scrollen ein `AddNew` oder `Edit` Aufruf ohne `Update`, `CommitTrans`, oder `Rollback` zunächst alle Änderungen verloren (mit keine Warnung für Sie) wie ein neuer Datensatz in die Bearbeitungspuffer eingebunden ist. Bearbeitungspuffer wird gefüllt, mit dem Datensatz, der ein Bildlauf durchgeführt, und es erfolgt keine Änderung in der Datenquelle gespeicherte Datensatz wird freigegeben. Dies gilt für `AddNew` und `Edit`.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> Ihre Updates und die Updates für andere Benutzer  

Wenn Sie ein Recordset verwenden, um Daten zu aktualisieren, Auswirkungen auf Ihre Updates auf andere Benutzer. Auf ähnliche Weise wirkt sich auf die Updates für andere Benutzer während der Lebensdauer des Recordsets.  
  
In einer mehrbenutzerumgebung können andere Benutzer Recordsets öffnen, die einige der gleichen Einträge enthalten, die Sie im Recordset ausgewählt haben. Änderungen an einem Datensatz, bevor Sie sie abrufen, werden im Recordset wiedergegeben. Da Dynasets ein Datensatzes jedes Mal, die Sie darin einen Bildlauf durchführen abrufen, wider Dynasets Änderungen jedes Mal, wenn Sie einen Bildlauf zu einem Datensatz durchführen. Abrufen von Momentaufnahmen ein Datensatzes beim ersten, die Sie darauf, scrollen, damit Momentaufnahmen nur diese Änderungen, die auftreten widerspiegeln, bevor Sie mit dem Datensatz zunächst einen Bildlauf durchführen.  
  
Datensätze, die von anderen Benutzern hinzugefügt wird, nach dem Öffnen des Recordsets werden nicht im Recordset angezeigt, es sei denn, Sie diese erneut abfragen. Wenn das Recordset ein Dynaset ist, werden Änderungen an vorhandenen Datensätze, die von anderen Benutzern im Dynaset angezeigt, wenn Sie auf den betroffenen Datensatz Bildlauf ausführen. Wenn das Recordset eine Momentaufnahme ist, Änderungen nicht mehr anzeigen, solange Sie die Momentaufnahme erneut abfragen. Wenn Sie verwenden möchten, finden Sie unter Datensätze hinzugefügt wurden, oder rufen Sie die von anderen Benutzern im Snapshot oder von anderen Benutzern im Dynaset, hinzugefügte Datensätze gelöscht [CRecordset](../../mfc/reference/crecordset-class.md#requery) das Recordset neu zu erstellen. (Beachten Sie, dass die Löschen von anderen Benutzern im Dynaset angezeigt.) Sie können auch aufrufen, `Requery` Einträge sehen Sie hinzugefügt haben, aber nicht um finden Sie unter Ihrem löschungen.  
  
> [!TIP]
>  Rufen Sie zum Zwischenspeichern für eine gesamte Momentaufnahme auf einmal zu erzwingen, `MoveLast` sofort nach dem Öffnen von der Momentaufnahme. Rufen Sie anschließend `MoveFirst` , wie mit den Datensätzen arbeiten. `MoveLast` ist gleich alle Datensätze, aber es werden alle auf einmal abgerufen. Beachten Sie jedoch, dass dies die Leistung beeinträchtigt werden kann und möglicherweise nicht erforderlich, damit einige Treiber.  
  
Die Auswirkungen Ihrer Updates für andere Benutzer sind die Auswirkungen auf die Sie ähnlich.  
  
##  <a name="_core_more_about_update_and_delete"></a> Weitere Informationen zu aktualisieren und löschen  

Dieser Abschnitt enthält zusätzliche Informationen, damit Ihnen die Arbeit mit `Update` und `Delete`.  
  
### <a name="update-success-and-failure"></a>Update Erfolg und Fehler  

Wenn `Update` erfolgreich ist, die `AddNew` oder `Edit` endet. Zum Starten einer `AddNew` oder `Edit` Modus erneut aus, rufen `AddNew` oder `Edit`.  
  
Wenn `Update` schlägt fehl ("false" zurückgibt, oder löst eine Ausnahme aus), Sie behalten immer die `AddNew` oder `Edit` Modus, je nachdem welche Funktion Sie zuletzt aufgerufen haben. Sie können dann eine der folgenden Aktionen ausführen:  
  
- Ändern Sie einen Datenmember des Felds, und versuchen Sie es der `Update` erneut aus.  
  
- Rufen Sie `AddNew` um den Felddatenmembern auf Null zurückzusetzen, legen Sie die Werte der Felddatenmember, und rufen Sie dann `Update` erneut aus.  
  
- Rufen Sie `Edit` das Neuladen von Werten, die das Recordset vor dem ersten Aufruf von wurden `AddNew` oder `Edit`, legen Sie die Werte der Felddatenmember des und rufen dann `Update` erneut. Nach einer erfolgreichen `Update` aufrufen (außer nach einem `AddNew` aufrufen), die Felddatenmembern behalten ihre neuen Werte.  
  
- Rufen Sie `Move` (einschließlich `Move` mit dem Parameter AFX_MOVE_REFRESH oder 0), die alle leert ändert und beendet alle `AddNew` oder `Edit` Modus aktiv.  
  
### <a name="update-and-delete"></a>Update- und Delete  

Dieser Abschnitt gilt für beide `Update` und `Delete`.  
  
Auf einem `Update` oder `Delete` -Vorgang nur ein Datensatz aktualisiert werden soll. Dieser Datensatz ist der aktuelle Datensatz, der die Datenwerte in den Feldern des Recordset-Objekts entspricht. Wenn aus irgendeinem Grund keine Datensätze oder betroffen sind mehr als einem Datensatz ist, eine Ausnahme ausgelöst wird, enthält die folgenden **"RETCODE"** Werte:  
  
- AFX_SQL_ERROR_NO_ROWS_AFFECTED  
  
- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED  
  
Wenn diese Ausnahmen ausgelöst werden, verbleiben Sie in der `AddNew` oder `Edit` Status Sie beim Aufrufen haben `Update` oder `Delete`. Hier sind die häufigsten Szenarien, in denen Sie diese Ausnahmen sehen würden. Sie haben wahrscheinlich finden Sie unter:  
  
- AFX_SQL_ERROR_NO_ROWS_AFFECTED Sie optimistisches Sperrverhalten verwenden und ein anderer Benutzer hat den Datensatz in einer Weise geändert, die das Framework daran hindert, den richtigen Datensatz zu aktualisieren oder löschen.  
  
- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED in der Tabelle, die Sie aktualisieren möchten, wurde kein Primärschlüssel oder eindeutigen Index, und Sie haben nicht genügend Spalten im Recordset, um eine Zeile einer Tabelle eindeutig identifizieren.  
  
## <a name="see-also"></a>Siehe auch  

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Wie Recordsets Datensätze auswählen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md)