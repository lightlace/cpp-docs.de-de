---
title: "Recordset: Erstellen und Schlie&#223;en von Recordsets (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Recordsets, Schließen"
  - "ODBC-Recordsets, Erstellen"
  - "ODBC-Recordsets, Öffnen"
  - "Recordsets, Schließen"
  - "Recordsets, Erstellen"
  - "Recordsets, Öffnen"
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset: Erstellen und Schlie&#223;en von Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Wenn Sie ein Recordset verwenden möchten, erstellen Sie ein Recordset\-Objekt und rufen dann die zugehörige **Open**\-Memberfunktion auf, um die Recordset\-Abfrage auszuführen und Datensätze auszuwählen.  Wenn Sie das Recordset nicht mehr benötigen, schließen und zerstören Sie das Objekt.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Wann und wie Sie ein Recordset\-Objekt erstellen](#_core_creating_recordsets_at_run_time).  
  
-   [Wann und wie Sie das Verhalten des Recordsets durch Parametrisieren, Filtern, Sortieren oder Sperren beeinflussen können](#_core_setting_recordset_options).  
  
-   [Wann und wie Sie ein Recordset\-Objekt schließen](#_core_closing_a_recordset).  
  
##  <a name="_core_creating_recordsets_at_run_time"></a> Erstellen von Recordsets zur Laufzeit  
 Bevor Sie im Programm Recordset\-Objekte erstellen können, müssen Sie anwendungsspezifische Recordset\-Klassen generieren.  Weitere Informationen hierzu finden Sie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Öffnen Sie ein Dynaset\-Objekt oder ein Momentaufnahme\-Objekt, wenn Sie Datensätze aus einer Datenquelle auswählen möchten.  Welchen Objekttyp Sie erstellen sollten, hängt davon ab, wofür Sie die Daten in der Anwendung benötigen und ob der ODBC\-Treiber diesen Typ unterstützt.  Weitere Informationen finden Sie unter [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).  
  
#### So öffnen Sie ein Recordset  
  
1.  Konstruieren Sie ein Objekt der von `CRecordset` abgeleiteten Klasse.  
  
     Sie können das Objekt entweder auf dem Heap oder auf dem Stapelrahmen einer Funktion konstruieren.  
  
2.  Ändern Sie bei Bedarf das Standardrecordsetverhalten.  Informationen über die zur Verfügung stehenden Optionen finden Sie in [Festlegen von Recordset\-Optionen](#_core_setting_recordset_options).  
  
3.  Rufen Sie die [Open](../Topic/CRecordset::Open.md)\-Memberfunktion des Objekts auf.  
  
 Übergeben Sie im Konstruktor entweder einen Zeiger auf ein `CDatabase`\-Objekt oder den Wert **NULL**. Im zweiten Fall wird ein temporäres Datenbankobjekt verwendet, das das Framework aufgrund der Verbindungszeichenfolge erstellt und öffnet, die von der [GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md)\-Memberfunktion zurückgegeben wird.  Das `CDatabase`\-Objekt könnte bereits mit einer Datenquelle verbunden sein.  
  
 Während des Aufrufs von **Open** werden mithilfe von SQL Datensätze aus der Datenquelle ausgewählt.  Der erste ausgewählte Datensatz \(falls vorhanden\) ist der aktuelle Datensatz.  Die Werte der Felder dieses Datensatzes werden in den Felddatenmembern des Recordset\-Objekts gespeichert.  Falls ein Datensatz ausgewählt wurde, geben die `IsBOF`\-Memberfunktion und die `IsEOF`\-Memberfunktion den Wert 0 \(null\) zurück.  
  
 Im [Open](../Topic/CRecordset::Open.md)\-Aufruf können Sie einige Punkte festlegen:  
  
-   Sie geben an, ob das Recordset ein Dynaset oder eine Momentaufnahme ist.  Recordsets werden standardmäßig als Momentaufnahmen geöffnet.  Sie können auch ein Vorwärts\-Recordset angeben, mit dem immer nur zum jeweils nächsten Datensatz gewechselt werden kann.  
  
     Standardmäßig verwendet ein Recordset den Standardtyp, der im `CRecordset`\-Datenmember **m\_nDefaultType** gespeichert ist.  Wenn Sie in einem Assistenten einen Recordsettyp auswählen, schreibt der Assistent Code, um **m\_nDefaultType** mit dem entsprechenden Wert zu initialisieren.  Sie müssen diese Vorgabe nicht übernehmen, sondern können sie durch einen anderen Recordsettyp ersetzen.  
  
-   Sie legen eine Zeichenfolge fest, die die Standard\-SQL\-**SELECT**\-Anweisung ersetzt, die vom Recordset erstellt wird.  
  
-   Sie geben an, ob das Recordset schreibgeschützt ist oder ob nur Datensätze angehängt werden dürfen.  Recordsets ermöglichen standardmäßig eine vollständige Aktualisierung. Sie können diese aber auf das Hinzufügen neuer Datensätze beschränken oder sogar jede Aktualisierung deaktivieren.  
  
 Das folgende Beispiel zeigt, wie Sie ein schreibgeschütztes Momentaufnahme\-Objekt der Klasse `CStudentSet` öffnen, einer anwendungsspezifischen Klasse:  
  
```  
// Construct the snapshot object  
CStudentSet rsStudent( NULL );  
// Set options if desired, then open the recordset  
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))  
    return FALSE;  
// Use the snapshot to operate on its records...  
```  
  
 Nach dem Aufruf von **Open** arbeiten Sie mit den Datensätzen, indem Sie auf die Memberfunktionen und Datenmember des Objekts zugreifen.  In manchen Fällen sollten Sie das Recordset neu abfragen oder aktualisieren, um die inzwischen in der Datenquelle vorgenommenen Änderungen widerzuspiegeln.  Weitere Informationen hierzu finden Sie unter [Recordset: Erneutes Abfragen eines Recordsets \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).  
  
> [!TIP]
>  Die Verbindungszeichenfolge, die Sie während der Entwicklung verwenden, kann sich von der unterscheiden, die der Benutzer der Anwendung benötigt.  Hinweise zur Generalisierung der Anwendung in diesem Punkt finden Sie unter [Datenquelle: Verwalten von Verbindungen \(ODBC\)](../../data/odbc/data-source-managing-connections-odbc.md).  
  
##  <a name="_core_setting_recordset_options"></a> Festlegen von Recordset\-Optionen  
 Nachdem Sie das Recordset\-Objekt konstruiert haben, aber noch bevor Sie zur Auswahl von Datensätzen **Open** aufrufen, können Sie einige Optionen festlegen, um das Verhalten des Recordsets zu steuern.  Die folgenden Punkte sind für alle Recordsets möglich:  
  
-   Sie können einen [Filter](../../data/odbc/recordset-filtering-records-odbc.md) festlegen, der die Datensatzauswahl einschränkt.  
  
-   Sie können eine [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md) für die Datensätze festlegen.  
  
-   Sie können [Parameter](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) angeben, mit denen Sie Datensätze aufgrund von Informationen auswählen können, die zur Laufzeit ermittelt oder berechnet werden.  
  
 Unter bestimmten Bedingungen können Sie folgende Option festlegen:  
  
-   Falls das Recordset aktualisierbar ist und Sperroptionen unterstützt, können Sie das [Sperrverhalten](../../data/odbc/recordset-locking-records-odbc.md) bei Aktualisierungen festlegen.  
  
> [!NOTE]
>  Damit sich diese Optionen auf die Auswahl von Datensätzen auswirken, müssen sie vor Aufruf der **Open**\-Memberfunktion festgelegt werden.  
  
##  <a name="_core_closing_a_recordset"></a> Schließen eines Recordsets  
 Wenn Sie das Recordset nicht mehr benötigen, müssen Sie es löschen und den dafür belegten Speicher freigeben.  
  
#### So schließen Sie ein Recordset  
  
1.  Rufen Sie die zugehörige Memberfunktion [Close](../Topic/CRecordset::Close.md) auf.  
  
2.  Zerstören Sie das Recordset\-Objekt.  
  
     Falls Sie das Objekt auf dem Stapelrahmen einer Funktion deklariert haben, wird das Objekt beim Verlassen des Gültigkeitsbereichs automatisch zerstört.  Andernfalls müssen Sie den Operator **delete** verwenden.  
  
 Durch **Close** wird das **HSTMT**\-Handle des Recordsets freigegeben.  Close zerstört nicht das C\+\+\-Objekt.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Scrollen \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)