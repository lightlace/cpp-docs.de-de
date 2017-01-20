---
title: "Recordset (ODBC)"
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
  - "Dynamische Recordsets"
  - "Dynasets"
  - "Vorwärts-Recordsets"
  - "ODBC-Recordsets"
  - "ODBC-Recordsets, CRecordset-Objekte"
  - "Recordsets, Informationen über Recordsets"
  - "Recordsets, Erstellen"
  - "Recordsets, Dynasets"
  - "Recordsets, Snapshots"
  - "Snapshots, ODBC-Recordsets"
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Ein [CRecordset](../../mfc/reference/crecordset-class.md)\-Objekt repräsentiert eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt wurden.  Die Datensätze können aus folgenden Objekten stammen:  
  
-   aus einer Tabelle,  
  
-   aus einer Abfrage  
  
-   oder aus einer gespeicherten Prozedur, die auf eine oder mehrere Tabellen zugreift.  
  
 Ein Beispiel für ein Recordset, das auf einer Tabelle basiert, ist das Recordset "Alle Kunden", das auf eine Tabelle mit Kunden zugreift.  Ein Beispiel für eine Abfrage ist "Alle Rechnungen an Joe Smith". Ein Beispiel für ein Recordset, das auf einer gespeicherten Prozedur \(manchmal auch als vordefinierte Abfrage bezeichnet\) basiert, ist "Alle Konten des Zahlungsunwilligen". Hiermit wird eine gespeicherte Prozedur in der Back\-End\-Datenbank aufgerufen.  Ein Recordset kann zwei oder mehrere Tabellen derselben Datenquelle miteinander verknüpfen, allerdings keine Tabellen verschiedener Datenquellen.  
  
> [!NOTE]
>  Informationen über das Ableiten von Recordset\-Klassen mit den Assistenten finden Sie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) und [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
> [!NOTE]
>  Einige ODBC\-Treiber unterstützen Datenbankansichten.  In diesem Zusammenhang steht der Begriff Ansicht für eine Abfrage, die mit der SQL\-`CREATE VIEW`\-Anweisung erstellt wurde.  Die Assistenten unterstützen derzeit keine Ansichten, Sie können den entsprechenden Code aber selbst entwickeln.  
  
##  <a name="_core_recordset_capabilities"></a> Fähigkeiten der Recordset\-Objekte  
 Alle Recordset\-Objekte unterstützen die folgenden Fähigkeiten:  
  
-   Falls das Recordset nicht schreibgeschützt ist, können Sie festlegen, dass das Recordset [aktualisierbar](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [erweiterbar](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md) oder schreibgeschützt ist.  Falls das Recordset aktualisierbar ist, haben Sie die Wahl zwischen vollständigen oder eingeschränkten [Sperrmethoden](../../data/odbc/recordset-locking-records-odbc.md), wenn der Treiber die entsprechende Unterstützung anbietet.  Falls die Datenquelle schreibgeschützt ist, ist auch das Recordset schreibgeschützt.  
  
-   Sie können Memberfunktionen aufrufen, um durch die ausgewählten Datensätze zu [scrollen](../../data/odbc/recordset-scrolling-odbc.md).  
  
-   Sie können die Datensätze [filtern](../../data/odbc/recordset-filtering-records-odbc.md), um aus den verfügbaren Datensätzen nur bestimmte auszuwählen.  
  
-   Sie können die Datensätze in aufsteigender oder absteigender Reihenfolge [sortieren](../../data/odbc/recordset-sorting-records-odbc.md), in einer oder in mehreren Spalten.  
  
-   Sie können das Recordset [parametrisieren](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md), um die Auswahl des Recordsets zur Laufzeit anzupassen.  
  
##  <a name="_core_snapshots_and_dynasets"></a> Momentaufnahmen und Dynasets  
 Es gibt zwei unterschiedliche Arten von Recordsets: [Momentaufnahmen](../../data/odbc/snapshot.md) und [Dynasets](../../data/odbc/dynaset.md).  Beide werden von der **CRecordset\-**Klasse unterstützt.  Beide Typen beherrschen die gemeinsamen Fähigkeiten aller Recordsets, jeder Typ erweitert den allgemeinen Funktionsumfang aber auf spezielle Weise.  Momentaufnahmen stellen eine statische Ansicht der Daten zur Verfügung. Sie eignen sich gut für Berichte und andere Situationen, in denen Sie eine Ansicht der Daten in der Form benötigen, in der sie zu einem bestimmten Zeitpunkt vorlagen.  Dynasets sind praktisch, wenn Sie möchten, dass von anderen Benutzern vorgenommene Änderungen sich im Recordset widerspiegeln, ohne dass Sie dieses erneut abfragen oder aktualisieren müssen.  Momentaufnahmen und Dynasets können aktualisierbar oder schreibgeschützt sein.  Wenn sich in dem Recordset widerspiegeln soll, welche Datensätze von anderen Benutzern hinzugefügt oder gelöscht wurden, rufen Sie [CRecordset::Requery](../Topic/CRecordset::Requery.md) auf.  
  
 `CRecordset` unterstützt daneben noch zwei weitere Typen von Recordsets: dynamische Recordsets und Vorwärts\-Recordsets.  Dynamische Recordsets ähneln Dynasets. Diese spiegeln jedoch alle hinzugefügten oder gelöschten Datensätze wider, ohne dass Sie dafür `CRecordset::Requery` aufrufen müssen.  Aus diesem Grund erfordern dynamische Recordsets viel Verarbeitungszeit des DBMS und werden von wenigen ODBC\-Treibern unterstützt.  Vorwärts\-Recordsets stellen dagegen die effizienteste Methode für den Zugriff auf Daten von Recordsets dar, für die Sie Aktualisierung oder Rückwärtsscrollen nicht benötigen.  Sie können ein Vorwärts\-Recordset z. B. bei der Migration von Daten von einer Datenquelle in eine andere verwenden. Dabei müssen Sie nur vorwärts durch die Daten navigieren.  Führen Sie folgende Schritte durch, um ein Vorwärts\-Recordset zu verwenden:  
  
-   Übergeben Sie die Option **CRecordset::forwardOnly** als `nOpenType`\-Parameter der [Open](../Topic/CRecordset::Open.md)\-Memberfunktion.  
  
-   Geben Sie für **Open** im Parameter `dwOptions` das Argument **CRecordset::readOnly** an.  
  
    > [!NOTE]
    >  Informationen darüber, welche Anforderungen ODBC\-Treiber zur Dynasetunterstützung erfüllen müssen, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md).  Eine Liste der in dieser Version von Visual C\+\+ mitgelieferten ODBC\-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC\-Treiber](../../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_your_recordsets"></a> Recordset\-Klassen  
 Normalerweise definieren Sie für jede Tabelle, Ansicht oder gespeicherte Prozedur, auf die Sie zugreifen möchten, eine von `CRecordset` abgeleitete Klasse. \(Eine Ausnahme ist ein Datenbankjoin, bei dem ein Recordset Spalten aus zwei oder mehr Tabellen repräsentiert.\) Wenn Sie eine Recordset\-Klasse ableiten, aktivieren Sie den Datensatzfeldaustausch\-Mechanismus \(Record Field Exchange, RFX\) oder den Sammel\-Datensatzfeldaustausch\-Mechanismus \(Sammel\-RFX\), die dem Mechanismus des Dialogdatenaustauschs \(Dialog Data Exchange, DDX\) ähneln.  RFX und Sammel\-RFX vereinfachen den Datentransfer von der Datenquelle in das Recordset. RFX überträgt außerdem Daten aus dem Recordset zur Datenquelle.  Weitere Informationen finden Sie unter [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Mit einem Recordset\-Objekt haben Sie die Möglichkeit, auf alle ausgewählten Datensätze zuzugreifen.  Sie scrollen durch die ausgewählten Datensätze mithilfe der `CRecordset`\-Memberfunktionen, z. B. mit `MoveNext` oder `MovePrev`.  Ein Recordset\-Objekt repräsentiert einen einzelnen dieser Datensätze, den so genannten aktuellen Datensatz.  Sie können die Felder des aktuellen Datensatzes untersuchen, indem Sie in der Recordset\-Klasse Membervariablen deklarieren, die den Spalten der Tabelle oder der Datensätze entsprechen, die bei einer Datenbankabfrage zurückgegeben werden.  Informationen über Recordsetdatenmember finden Sie unter [Recordset: Architektur \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md).  
  
 In den folgenden Themen wird die Verwendung der Recordset\-Objekte ausführlich erläutert.  Die Themen sind in Funktionskategorien unterteilt und sollten möglichst in der angegebenen Reihenfolge gelesen werden.  
  
### Themen über das Öffnen, Lesen und Schließen von Recordsets  
  
-   [Recordset: Architektur \(ODBC\)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [Recordset: Deklarieren einer Klasse für eine Tabelle \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [Recordset: Erstellen und Schließen von Recordsets \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [Recordset: Scrollen \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [Recordset: Lesezeichen und absolute Positionen \(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [Recordset: Sortieren von Datensätzen \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### Themen über das Ändern von Recordsets  
  
-   [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [Recordset: Sperren von Datensätzen \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [Recordset: Erneutes Abfragen eines Recordsets \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### Themen über komplexere Einsatzmöglichkeiten  
  
-   [Recordset: Ausführen eines Joins \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [Recordset: Arbeiten mit großen Datenelementen \(ODBC\)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [Recordset: Abrufen von SUMs und anderen Aggregatergebnissen \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### Themen über die Funktionsweise von Recordsets  
  
-   [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Nutzen von MFC\-ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md)