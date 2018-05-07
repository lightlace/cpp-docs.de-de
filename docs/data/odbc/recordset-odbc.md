---
title: Recordset (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c59de3c5db2e1ec658a09279cb42e2833a4109e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-odbc"></a>Recordset (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Ein [CRecordset](../../mfc/reference/crecordset-class.md) Objekt stellt eine Reihe von Datensätzen, die aus einer Datenquelle ausgewählt. Die Datensätze möglich aus:  
  
-   Eine Tabelle.  
  
-   Eine Abfrage.  
  
-   Eine gespeicherte Prozedur, die eine oder mehrere Tabellen zugreift.  
  
 Ein Beispiel für ein Recordset basierend auf einer Tabelle ist "all Customers", das eine Customer-Tabelle zugegriffen wird. Ein Beispiel einer Abfrage ist "alle Rechnungen für Joe Smith". Ein Beispiel für ein Recordset basierend auf einer gespeicherten Prozedur (manchmal auch als eine vordefinierte Abfrage bezeichnet) ist "alle Konten rechnungszahlungen," dem ruft einer gespeicherten Prozedur in der Back-End-Datenbank. Ein Recordset kann zwei oder mehr Tabellen aus derselben Datenquelle, jedoch nicht die Tabellen aus unterschiedlichen Datenquellen verknüpfen.  
  
> [!NOTE]
>  Informationen zum Ableiten des Recordset-Klassen mit den Assistenten finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) und [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
> [!NOTE]
>  Einige ODBC-Treiber unterstützt die Ansichten der Datenbank. Eine Ansicht in diesem Sinn ist eine Abfrage erstellt wurde ursprünglich mit dem SQL- `CREATE VIEW` Anweisung. Die Assistenten unterstützen derzeit keine Sichten, aber es ist möglich, diese Unterstützung selbst code.  
  
##  <a name="_core_recordset_capabilities"></a> Recordset-Funktionen  
 Alle Recordset-Objekte freigeben, die folgenden Funktionen:  
  
-   Wenn die Datenquelle nicht schreibgeschützt ist, können Sie angeben, dass das Recordset [aktualisierbare](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [erweiterbar](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), oder schreibgeschützt. Wenn das Recordset aktualisierbar ist, können Sie auswählen, entweder eingeschränkte oder vollständige [Sperren](../../data/odbc/recordset-locking-records-odbc.md) bereitgestellte Methoden, die Treiber bereitstellt, die entsprechende Unterstützung. Wenn die Datenquelle schreibgeschützt ist, wird das Recordset schreibgeschützt ist.  
  
-   Sie können auf Memberfunktionen aufrufen [Scroll](../../data/odbc/recordset-scrolling-odbc.md) durch die ausgewählten Datensätze.  
  
-   Sie können [Filter](../../data/odbc/recordset-filtering-records-odbc.md) der Datensätze einschränken, welche Datensätze aus den verfügbaren ausgewählt werden.  
  
-   Sie können [sortieren](../../data/odbc/recordset-sorting-records-odbc.md) die Datensätze in aufsteigender oder absteigender Reihenfolge auf Grundlage einer oder mehreren Spalten.  
  
-   Sie können [parametrisieren](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Recordset, um die Auswahl des Recordsets zur Laufzeit zu qualifizieren.  
  
##  <a name="_core_snapshots_and_dynasets"></a> Momentaufnahmen und Dynasets  
 Es gibt zwei unterschiedliche Arten von Recordsets: [Momentaufnahmen](../../data/odbc/snapshot.md) und [Dynasets](../../data/odbc/dynaset.md). Beide werden von der Klasse unterstützt `CRecordset`. Jede teilt die allgemeinen Eigenschaften des Recordsets, aber jede auch die allgemeine Funktionalität auf spezielle Weise erweitert. Momentaufnahmen stellen eine statische Ansicht der Daten und eignen sich für Berichte und anderen Situationen, in denen Sie eine Ansicht der Daten möchten, wie sie zu einem bestimmten Zeitpunkt vorhanden waren. Dynasets sind nützlich, wenn Updates, die von anderen Benutzern an ohne requery oder aktualisieren das Recordset im Recordset angezeigt werden sollen. Momentaufnahmen und Dynasets können aktualisierbar oder schreibgeschützt sein. Entsprechen Datensätze hinzugefügt wurden, oder rufen Sie von anderen Benutzern gelöschten [CRecordset](../../mfc/reference/crecordset-class.md#requery).  
  
 `CRecordset` Darüber hinaus können zwei Arten von Recordsets: dynamische Recordsets und Vorwärts-Recordsets. Dynamische Recordsets ähneln Dynasets; Dynamische Recordsets widerspiegeln jedoch keine Datensätze hinzufügen oder löschen, ohne Aufruf von `CRecordset::Requery`. Aus diesem Grund dynamische Recordsets in Bezug auf die Verarbeitungszeit für das DBMS im Allgemeinen teuer sind und viele ODBC-Treiber unterstützen. Im Gegensatz dazu bieten die Forward-only-Recordsets die effizienteste Methode des Datenzugriffs für Recordsets, die keine Updates und Bildlauf rückwärts erforderlich sind. Ein Forward-only-Recordset können Sie z. B. Daten aus einer Datenquelle in eine andere migrieren, müssen Sie nur durch die Daten vorwärts zu bewegen. Um einen Forward-only-Recordset zu verwenden, müssen Sie beide der folgenden Aktionen ausführen:  
  
-   Übergeben Sie die Option **CRecordset:: forwardOnly** als die `nOpenType` Parameter von der [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion.  
  
-   Geben Sie **CRecordset:: ReadOnly** in der `dwOptions` Parameter **öffnen**.  
  
    > [!NOTE]
    >  Informationen zu ODBC-treiberanforderungen für Dynaset unterstützen, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md). Eine Liste der in dieser Version von Visual C++ mitgelieferten ODBC-Treiber sowie Informationen über den Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC-Treiber](../../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_your_recordsets"></a> Die Recordsets  
 Für jede Tabelle, Sicht oder gespeicherte Prozedur, die Sie zugreifen möchten, definieren Sie in der Regel eine abgeleitete Klasse `CRecordset`. (Die Ausnahme ist ein Datenbank-Join, in dem ein Recordset Spalten aus zwei oder mehr Tabellen darstellt.) Wenn Sie eine Recordset-Klasse ableiten, können Sie die Datensatzfeldaustausch (RFX)-Mechanismus oder der Bulk Datensatzfeldaustausch (Bulk-RFX)-Mechanismus, die dem Dialogfeld Daten Dialogdatenaustausch (DDX)-Mechanismus ähnlich sind. RFX und Bulk-RFX vereinfachen die Übertragung von Daten aus der Datenquelle in das Recordset; RFX überträgt außerdem Daten aus dem Recordset mit der Datenquelle ein. Weitere Informationen finden Sie unter [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Einem Recordset-Objekt erhalten Sie Zugriff auf die ausgewählten Datensätze. Sie führen Sie einen Bildlauf durch die ausgewählten Datensätze mit `CRecordset` Memberfunktionen, z. B. `MoveNext` und `MovePrev`. Zur gleichen Zeit stellt nur einen der ausgewählten Datensätze, den aktuellen Datensatz einem Recordset-Objekt dar. Deklarieren von Recordset-Klasse Membervariablen, die Spalten der Tabelle oder der Datensätze, die von der Datenbankabfrage entsprechen, um die Felder des aktuellen Datensatzes überprüfen. Informationen zu Recordset Datenmembern finden Sie unter [Recordset: Architektur (ODBC)](../../data/odbc/recordset-architecture-odbc.md).  
  
 Die folgenden Themen erläutern die Details der Verwendung des Recordset-Objekte. Die Themen sind in Funktionskategorien und natürliche in der angegebenen Reihenfolge sequenzielle Lesevorgänge aufgeführt.  
  
### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Themen über das Öffnen, lesen und Schließen von recordsets  
  
-   [Recordset: Architektur (ODBC)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [Recordset: Lesezeichen und absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Themen über das Ändern von recordsets  
  
-   [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### <a name="topics-about-somewhat-more-advanced-techniques"></a>Themen zu wenig erweiterten Techniken  
  
-   [Recordset: Ausführen eines Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [Recordset: Arbeiten mit großen Datenelementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### <a name="topics-about-how-recordsets-work"></a>Themen zur Funktionsweise von recordsets  
  
-   [Recordset: Wie Recordsets Datensätze auswählen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [Recordset: Wie Recordsets Datensätze aktualisieren (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Open Sie Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)