---
title: "Recordset: Erstellen und Schließen von Recordsets (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ec09c08aa4730c11960d675aef68c8a1007c900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Recordset: Erstellen und Schließen von Recordsets (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Um ein Recordset zu verwenden, erstellen Sie ein Recordset-Objekt, und rufen Sie anschließend die **öffnen** Member-Funktion, um das Recordset-Abfrage auszuführen und Auswählen von Datensätzen. Wenn Sie das Recordset abgeschlossen haben, schließen Sie und zerstören Sie das Objekt.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wann und wie Sie einem Recordset-Objekt erstellen](#_core_creating_recordsets_at_run_time).  
  
-   [Wann und wie können Sie das Verhalten des Recordsets durch Parametrisieren, filtern, sortieren oder Sperren qualifizieren](#_core_setting_recordset_options).  
  
-   [Wann und wie Sie einem Recordset-Objekt schließen](#_core_closing_a_recordset).  
  
##  <a name="_core_creating_recordsets_at_run_time"></a>Erstellen von Recordsets zur Laufzeit  
 Bevor Sie in Ihrem Programm Recordset-Objekte erstellen können, Schreiben Sie in der Regel anwendungsspezifische Recordset-Klassen. Weitere Informationen über dieses vorausgehenden Schritts finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Öffnen Sie ein Dynaset oder Snapshot-Objekt, wenn Sie zum Auswählen von Datensätzen aus einer Datenquelle benötigen. Hängt von der Typ des zu erstellenden Objekts Sie müssen mit den Daten in der Anwendung und auf welche die ODBC-Treiber unterstützt. Weitere Informationen finden Sie unter [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).  
  
#### <a name="to-open-a-recordset"></a>Öffnen Sie ein recordset  
  
1.  Erstellen Sie ein Objekt von Ihr `CRecordset`-abgeleitete Klasse.  
  
     Sie können das Objekt auf dem Heap oder auf den Stapelrahmen, der eine Funktion erstellen.  
  
2.  Ändern Sie optional das Standardverhalten für das Recordset. Die verfügbaren Optionen finden Sie unter [Recordset Einstellungsoptionen](#_core_setting_recordset_options).  
  
3.  Rufen Sie des Objekts [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion.  
  
 Übergeben Sie im Konstruktor einen Zeiger auf eine `CDatabase` Objekt auf oder übergeben **NULL** verwendet eine temporäre Datenbankobjekt, das Framework erstellt und öffnet, auf Grundlage der Verbindungszeichenfolge zurückgegebenes der [GetDefaultConnect ](../../mfc/reference/crecordset-class.md#getdefaultconnect) Memberfunktion. Die `CDatabase` Objekt möglicherweise bereits mit einer Datenquelle verbunden werden.  
  
 Der Aufruf von **öffnen** SQL zum Auswählen von Datensätzen aus der Datenquelle verwendet. Der erste Datensatz ausgewählt (sofern vorhanden) ist der aktuelle Datensatz. Die Werte der Felder dieses Datensatzes werden in die Felddatenmember der Recordset-Objekts gespeichert. Wenn keine Datensätze ausgewählt wurden, sowohl die `IsBOF` und `IsEOF` Memberfunktionen geben 0 zurück.  
  
 In Ihrem [öffnen](../../mfc/reference/crecordset-class.md#open) aufrufen, können Sie:  
  
-   Geben Sie an, ob das Recordset ein Dynaset oder eine Momentaufnahme ist. Recordsets, die als Momentaufnahmen standardmäßig geöffnet werden. Oder Sie können einen Vorwärtscursor-Recordset, das ermöglicht, nur den Bildlauf vorwärts, einen Datensatz zu einem Zeitpunkt angeben.  
  
     Standardmäßig verwendet ein Recordset den Standardtyp gespeichert, der `CRecordset` Datenmember **M_nDefaultType**. Assistenten schreiben Sie Code zum Initialisieren **M_nDefaultType** in den Recordsettyp, die Sie im Assistenten auswählen. Anstatt diese Standardeinstellung wird akzeptiert, können Sie einen anderen Recordsettyp ersetzen.  
  
-   Geben Sie eine Zeichenfolge zum Ersetzen von Standard-SQL **wählen** -Anweisung, die vom Recordset erstellt.  
  
-   Geben Sie an, ob das Recordset schreibgeschützt oder nur zum Anhängen ist. Recordsets ermöglichen eine vollständige Aktualisierung standardmäßig, aber Sie können einschränken, um nur neue Datensätze hinzufügen oder Sie können verhindern, dass alle Updates.  
  
 Im folgende Beispiel wird gezeigt, wie ein nur-Lese Momentaufnahmeobjekt der Klasse öffnen `CStudentSet`, eine anwendungsspezifische-Klasse:  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 Nach dem Aufruf **öffnen**, verwenden Sie die Member-Funktionen und Datenmember des Objekts, um mit den Datensätzen arbeiten. In einigen Fällen möchten Sie möglicherweise erneut Abfragen oder aktualisieren Sie das Recordset, um die Änderungen einzubeziehen, die für die Datenquelle aufgetreten sind. Weitere Informationen finden Sie unter [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).  
  
> [!TIP]
>  Die Verbindungszeichenfolge, die Sie während der Entwicklung verwenden möglicherweise nicht die gleiche Verbindungszeichenfolge, die Ihre endgültigen Benutzer benötigen. Ideen zu verallgemeinern Ihre Anwendung in dieser Hinsicht, finden Sie unter [Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).  
  
##  <a name="_core_setting_recordset_options"></a>Festlegen von Optionen für Recordsets  
 Wenn Sie das Recordset-Objekt erstellt haben, aber vor dem Aufruf **öffnen** zum Auswählen von Datensätzen, sollten Sie einige Optionen steuern das Verhalten des Recordsets. Für alle Recordsets können Sie folgende Aktionen ausführen:  
  
-   Geben Sie einen [Filter](../../data/odbc/recordset-filtering-records-odbc.md) Datensatzauswahl.  
  
-   Geben Sie einen [sortieren](../../data/odbc/recordset-sorting-records-odbc.md) Reihenfolge für die Datensätze.  
  
-   Geben Sie [Parameter](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Sie Datensätze mithilfe der Informationen abgerufen oder berechnet, die zur Laufzeit auswählen können.  
  
 Sie können auch die folgende Option festlegen, wenn die Bedingungen sind:  
  
-   Wenn das Recordset aktualisierbar ist, und Sperre werden Optionen unterstützt, geben Sie die [Sperren](../../data/odbc/recordset-locking-records-odbc.md) Methode, die für Updates verwendet.  
  
> [!NOTE]
>  Um das Datensatzauswahl auswirken können, müssen Sie diese Optionen festlegen, vor dem Aufrufen der **öffnen** Memberfunktion.  
  
##  <a name="_core_closing_a_recordset"></a>Schließen ein Recordset  
 Wenn Sie das Recordset abgeschlossen haben, müssen Sie davon dispose und dafür belegten Speicher.  
  
#### <a name="to-close-a-recordset"></a>Zum Schließen eines Recordsets  
  
1.  Rufen Sie die [schließen](../../mfc/reference/crecordset-class.md#close) Memberfunktion.  
  
2.  Zerstören Sie das Recordsetobjekt.  
  
     Wenn Sie es auf den Stapelrahmen einer Funktion deklariert, das Objekt automatisch zerstört, wenn das Objekt den Gültigkeitsbereich verlässt. Verwenden Sie andernfalls die **löschen** Operator.  
  
 **Schließen** freigegeben des Recordsets **Befehls beschäftigt** behandeln. Die C++-Objekt zerstört nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)