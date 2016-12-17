---
title: "Recordset: Weitere Informationen zu Aktualisierungen (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Mehrbenutzerumgebungen, Aktualisierungen von Recordsets"
  - "ODBC-Recordsets, Aktualisieren"
  - "Datensätze, Aktualisieren"
  - "Recordsets, Aktualisieren"
  - "Scrollen, Aktualisierungen von Recordsets"
  - "Transaktionen, Aktualisieren von Recordsets"
  - "Aktualisieren von Recordsets"
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Weitere Informationen zu Aktualisierungen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wie andere Operationen, z. B. Transaktionen, Aktualisierungen beeinflussen](#_core_how_transactions_affect_updates).  
  
-   [Zusammenhang zwischen Ihren Aktualisierungen und denen anderer Benutzer](#_core_your_updates_and_the_updates_of_other_users).  
  
-   [Weitere Informationen zu der Update\-Memberfunktionen und der Delete\-Memberfunktion](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Falls Sie das gesammelte Abrufen von Zeilen einsetzen, treffen einige dieser Informationen nicht zu.  Sie können z. B. nicht die Memberfunktionen `AddNew`, **Edit**, **Delete** und **Update** aufrufen. Sie können allerdings Transaktionen durchführen.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_how_other_operations_affect_updates"></a> Wie sich andere Operationen auf Aktualisierungen auswirken  
 Die vorgenommenen Aktualisierungen werden von Transaktionen beeinflusst, und zwar unmittelbar nachdem die Aktualisierung vorgenommen wurde, wenn das Recordset geschlossen wird, bevor eine Transaktion abgeschlossen wurde, und wenn gescrollt wird, bevor eine Transaktion abgeschlossen wurde.  
  
###  <a name="_core_how_transactions_affect_updates"></a> Wie sich Transaktionen auf Aktualisierungen auswirken  
 Neben der Funktionsweise von `AddNew`, **Edit** und **Delete** müssen Sie verstehen, wie die Memberfunktionen **BeginTrans**, **CommitTrans** und **Rollback** von [CDatabase](../../mfc/reference/cdatabase-class.md) mit den Aktualisierungsfunktionen von [CRecordset](../../mfc/reference/crecordset-class.md) zusammenwirken.  
  
 Standardmäßig wirken sich Aufrufe von `AddNew` und **Edit** auf die Datenquelle aus, unmittelbar nachdem Sie **Update** aufrufen.  Aufrufe von **Delete** wirken sich sofort auf die Datenquelle aus.  Sie können aber eine Transaktion einrichten und einen ganzen Batch solcher Aufrufe durchführen.  Die Aktualisierungen werden nicht dauerhaft übernommen, bevor Sie sie bestätigen.  Falls Sie es sich anders überlegen, können Sie die Transaktion zurücksetzen, statt sie zu bestätigen.  
  
 Weitere Informationen zu Transaktionen finden Sie unter [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> Wie sich das Schließen des Recordsets auf Aktualisierungen auswirkt  
 Wenn Sie ein Recordset oder das damit verknüpfte `CDatabase`\-Objekt schließen, während eine Transaktion durchgeführt wird \(d. h., [CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md) oder [CDatabase::Rollback](../Topic/CDatabase::Rollback.md) wurde noch nicht aufgerufen\), wird automatisch ein Rollback für die Transaktion ausgeführt \(es sei denn, bei dem Datenbank\-Back\-End handelt es sich um das Microsoft Jet\-Datenbankmodul\).  
  
> [!CAUTION]
>  Wenn Sie das Microsoft Jet\-Datenbankmodul verwenden und ein Recordset in einer expliziten Transaktion schließen, werden geänderte Zeilen oder gesetzte Sperren nicht freigegeben, bis die explizite Transaktion durchgeführt oder rückgängig gemacht wurde.  Sie sollten daher Recordsets entweder nur innerhalb oder nur außerhalb einer expliziten Jet\-Transaktion öffnen und schließen.  
  
###  <a name="_core_how_scrolling_affects_updates"></a> Wie sich Scrollen auf Aktualisierungen auswirkt  
 Wenn Sie in einem Recordset [Recordset: Scrollen \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md), wird der Bearbeitungspuffer jedes Mal mit dem neuen aktuellen Datensatz gefüllt \(der vorherige Datensatz wird dabei nicht zuerst gespeichert\).  Beim Scrollen werden vorher gelöschte Datensätze übersprungen.  Falls Sie zu einem `AddNew`\-Aufruf oder einem **Edit**\-Aufruf wechseln, ohne vorher **Update**, **CommitTrans** oder **Rollback** aufzurufen, gehen alle Änderungen ohne vorherige Warnung verloren, wenn der neue Datensatz in den Bearbeitungspuffer eingetragen wird.  Der Bearbeitungspuffer wird mit dem Zieldatensatz gefüllt und der gespeicherte Datensatz wird verworfen. An der Datenquelle werden keine Änderungen durchgeführt.  Dies gilt sowohl für `AddNew` als auch für **Edit**.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> Ihre Aktualisierungen und die Aktualisierungen anderer Benutzer  
 Wenn Sie Daten mithilfe eines Recordsets aktualisieren, wirken sich die von Ihnen vorgenommenen Änderungen auf andere Benutzer aus.  Genauso wirken sich auch Änderungen anderer Benutzer auf das Recordset aus, wenn sie während der Lebensdauer des Recordsets vorgenommen werden.  
  
 In einer Mehrbenutzerumgebung können andere Benutzer Recordsets öffnen, die einige der Datensätze enthalten, die auch Sie in dem Recordset ausgewählt haben.  Änderungen, die an einem Datensatz vorgenommen wurden, bevor Sie diesen abgerufen haben, werden im Recordset richtig widergespiegelt.  Dynasets rufen einen Datensatz jedes Mal neu ab und zeigen Änderungen an, wenn Sie zu einem Datensatz wechseln.  Momentaufnahmen fragen einen Datensatz ab, wenn Sie zum ersten Mal zu diesem wechseln. Momentaufnahmen spiegeln daher nur die Änderungen an einem Datensatz wider, die vorgenommen wurden, bevor Sie zum ersten Mal zu diesem Datensatz gewechselt haben.  
  
 Datensätze, die von anderen Benutzern hinzugefügt wurden, nachdem Sie das Recordset geöffnet hatten, werden im Recordset erst angezeigt, wenn Sie es neu abfragen.  Falls das Recordset ein Dynaset ist, werden Änderungen, die andere Benutzer an vorhandenen Datensätzen vornehmen, in diesem Dynaset wiedergegeben, wenn Sie zu dem betroffenen Datensatz wechseln.  Falls das Recordset eine Momentaufnahme ist, werden Änderungen so lange nicht angezeigt, bis Sie die Momentaufnahme neu abfragen.  Wenn Sie feststellen möchten, welche Datensätze aus der Momentaufnahme von anderen Benutzern hinzugefügt oder gelöscht oder welche Datensätze im Dynaset von anderen Benutzern neu hinzugefügt wurden, müssen Sie [CRecordset::Requery](../Topic/CRecordset::Requery.md) aufrufen und so das Recordset neu erstellen. \(Beachten Sie, dass sich von anderen Benutzern vorgenommene Löschoperationen in dem Dynaset widerspiegeln.\) Sie können **Requery** auch aufrufen, um von Ihnen hinzugefügte Datensätze anzuzeigen. Für gelöschte Datensätze ist dies nicht erforderlich.  
  
> [!TIP]
>  Um die Zwischenspeicherung einer gesamten Momentaufnahme zu erzwingen, rufen Sie `MoveLast` unmittelbar nach dem Öffnen der Momentaufnahme auf.  Rufen Sie dann **MoveFirst** auf, um mit den Datensätzen zu arbeiten.  `MoveLast` entspricht dem Abrufen aller Datensätze auf einmal.  Beachten Sie jedoch, dass hierdurch die Leistung beeinträchtigt werden kann und dieser Aufruf bei manchen Treibern nicht erforderlich ist.  
  
 Die Auswirkungen, die Ihre Änderungen auf andere Benutzer haben, ähneln den Auswirkungen, die deren Änderungen auf Ihr Recordset haben.  
  
##  <a name="_core_more_about_update_and_delete"></a> Update und Delete  
 Dieser Abschnitt enthält zusätzliche Informationen, die Ihnen bei der Arbeit mit **Update** und **Delete** helfen können.  
  
### Fehler bei der Ausführung von Update  
 Falls **Update** fehlerfrei ausgeführt wurde, wird der `AddNew`\-Modus oder der **Edit**\-Modus beendet.  Um erneut in den `AddNew`\-Modus oder den **Edit**\-Modus zu wechseln, rufen Sie `AddNew` oder **Edit** auf.  
  
 Falls bei der Ausführung von **Update** ein Fehler auftritt \(**Update** also **FALSE** zurückgibt oder eine Ausnahme auslöst\), bleiben Sie im `AddNew`\-Modus oder im Edit\-Modus, je nachdem, welche Funktion Sie zuletzt aufgerufen haben.  Sie haben dann folgende Möglichkeiten:  
  
-   Sie können einen Felddatenmember ändern und **Update** erneut aufrufen.  
  
-   Sie können `AddNew` aufrufen, um die Felddatenmember auf NULL zurückzusetzen, dann die Werte der Felddatenmember festlegen und schließlich erneut **Update** aufrufen.  
  
-   Sie können **Edit** aufrufen, um die Werte erneut zu laden, die vor dem ersten Aufruf von `AddNew` oder **Edit** im Recordset gespeichert waren, dann die Werte der Felddatenmember festlegen und schließlich erneut **Update** aufrufen.  Nach einem erfolgreichen Aufruf von **Update** behalten die Felddatenmember ihre neuen Werte \(außer nach einem `AddNew`\-Aufruf\).  
  
-   Sie können **Move** aufrufen \(z. B. mit dem Parameter **AFX\_MOVE\_REFRESH** oder 0\). So verwerfen Sie alle Änderungen und beenden den `AddNew`\-Modus oder **Edit**\-Modus.  
  
### Update und Delete  
 Dieser Abschnitt bezieht sich sowohl auf **Update** als auch auf **Delete**.  
  
 Bei einer **Update**\-Operation oder **Delete**\-Operation muss genau ein Datensatz aktualisiert werden.  Dieser aktualisierte Datensatz ist der aktuelle Datensatz, dessen Werte in den Feldern des Recordsets stehen.  Falls aus irgendwelchen Gründen keine oder mehrere Datensätze betroffen sind, wird eine Ausnahme ausgelöst, die einen der folgenden **RETCODE**\-Werte übergibt:  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED**  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED**  
  
 Wenn diese Ausnahmen ausgelöst werden, bleibt der `AddNew`\-Modus oder **Edit**\-Modus aktiv, der auch vor dem Aufruf von **Update** oder **Delete** aktiviert war.  Im Folgenden sehen Sie die häufigsten Ursachen für das Auftreten dieser Ausnahmen.  Die wahrscheinlichsten Ausnahmen sind:  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED**: Sie setzen ein optimistisches Sperrverhalten ein, und ein anderer Benutzer hat den Datensatz in einer Weise geändert, die das Framework daran hindert, den richtigen Datensatz zu aktualisieren oder zu löschen.  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED**: Die Tabelle, die Sie aktualisieren möchten, hat keinen Primärschlüssel oder eindeutigen Index, und Sie haben nicht genug Spalten im Recordset, um eine Tabellenzeile eindeutig zu identifizieren.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md)