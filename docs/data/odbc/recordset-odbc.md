---
title: Recordset (ODBC)
ms.date: 11/04/2016
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
ms.openlocfilehash: b201e152d83d3812253aa4803eebe715d726219d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034494"
---
# <a name="recordset-odbc"></a>Recordset (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Ein [CRecordset](../../mfc/reference/crecordset-class.md) Objekt stellt einen Satz von Datensätzen, ausgewählt aus einer Datenquelle dar. Die Datensätze aus sind möglich:

- Eine Tabelle.

- Eine Abfrage.

- Eine gespeicherte Prozedur, die eine oder mehrere Tabellen zugreift.

Ein Beispiel für ein Recordset basierend auf einer Tabelle ist "all Customers", die eine Customer-Tabelle zugreift. Ein Beispiel für eine Abfrage ist "alle Rechnungen für Joe Smith." Ein Beispiel für ein Recordset basierend auf einer gespeicherten Prozedur (manchmal auch als eine vordefinierte Abfrage bezeichnet) ist "alle Konten in Verzug," die ruft einer gespeicherten Prozedur in der Back-End-Datenbank. Ein Recordset kann zwei oder mehr Tabellen aus derselben Datenquelle, aber nicht die Tabellen aus unterschiedlichen Datenquellen miteinander verknüpfen.

> [!NOTE]
>  Informationen zum Ableiten des Recordset-Klassen mit den Assistenten, finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) und [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md).

> [!NOTE]
>  Einige ODBC-Treiber unterstützt die Ansichten der Datenbank. Eine Ansicht in diesem Sinn ist eine Abfrage, die ursprünglich erstellt, mit dem SQL- `CREATE VIEW` Anweisung. Die Assistenten unterstützen derzeit keine Sichten, aber es ist möglich, diese Unterstützung selbst programmieren.

##  <a name="_core_recordset_capabilities"></a> Recordset-Funktionen

Alle Recordset-Objekte freigeben, die folgenden Funktionen:

- Wenn die Datenquelle nicht schreibgeschützt ist, können Sie angeben, dass das Recordset [aktualisierbare](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [erweiterbar](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), oder schreibgeschützt. Wenn das Recordset aktualisierbar ist, können Sie entweder pessimistisch oder optimistisch [Sperren](../../data/odbc/recordset-locking-records-odbc.md) Methoden bereitgestellt, der Treiber stellt die entsprechende Unterstützung. Wenn die Datenquelle schreibgeschützt ist, wird das Recordset schreibgeschützt sein.

- Sie können Member-Funktionen zum Aufrufen [Scroll](../../data/odbc/recordset-scrolling-odbc.md) durch die ausgewählten Datensätze.

- Sie können [Filter](../../data/odbc/recordset-filtering-records-odbc.md) der Datensätze einschränken, welche Datensätze aus den verfügbaren ausgewählt werden.

- Sie können [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md) die Datensätze in aufsteigender oder absteigender Reihenfolge basierend auf einer oder mehreren Spalten.

- Sie können [parametrisieren](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Recordset, um die Auswahl des Recordsets zur Laufzeit.

##  <a name="_core_snapshots_and_dynasets"></a> Momentaufnahmen und Dynasets

Es gibt zwei unterschiedliche Arten von Recordsets: [Momentaufnahmen](../../data/odbc/snapshot.md) und [Dynasets](../../data/odbc/dynaset.md). Beide werden von der Klasse unterstützt `CRecordset`. Jede teilt die allgemeinen Merkmale von allen Recordsets, aber jede erweitert auch die allgemeine Funktionalität in seine eigenen speziellen Art und Weise. Momentaufnahmen stellen eine statische Ansicht der Daten und sind nützlich für Berichte und andere Situationen, in denen eine Ansicht der Daten sollen, wie sie zu einem bestimmten Zeitpunkt vorhanden waren. Dynasets sind nützlich, wenn Aktualisierungen, die von anderen Benutzern an ohne sich erneut Abfragen oder aktualisieren Sie das Recordset im Recordset angezeigt werden sollen. Momentaufnahmen und Dynasets können aktualisierbar oder schreibgeschützt sein. Einträgen hinzugefügt oder gelöscht, die von anderen Benutzern Aufrufen [CRecordset](../../mfc/reference/crecordset-class.md#requery).

`CRecordset` ermöglicht auch zwei andere Arten von Recordsets: dynamische Recordsets und Forward-only-Recordsets. Dynamische Recordsets sind mit Dynasets vergleichbar. Dynamische Recordsets entsprechen jedoch keine Datensätze hinzugefügt oder gelöscht werden, ohne `CRecordset::Requery`. Aus diesem Grund dynamische Recordsets sind in der Regel aufwendig in Bezug auf die Verarbeitungszeit für das DBMS, und viele ODBC-Treiber nicht unterstützen. Im Gegensatz dazu bieten die Forward-only-Recordsets die effizienteste Methode des Datenzugriffs für Recordsets, die keine Updates oder Bildlauf rückwärts erfordern. Ein Forward-only-Recordset können Sie beispielsweise Daten von einer Datenquelle zu einem anderen migrieren, müssen Sie nur die Daten vorwärts bewegen. Um eine Forward-only-Recordset zu verwenden, müssen Sie beide der folgenden Schritte ausführen:

- Übergeben Sie die Option `CRecordset::forwardOnly` als die *nOpenType* Parameter, der die [öffnen](../../mfc/reference/crecordset-class.md#open) Member-Funktion.

- Geben Sie `CRecordset::readOnly` in die *DwOptions* Parameter `Open`.

    > [!NOTE]
    >  Informationen zu ODBC-treiberanforderungen für Dynaset unterstützen, finden Sie unter [ODBC](../../data/odbc/odbc-basics.md). Eine Liste der in dieser Version von Visual C++ mitgelieferten ODBC-Treiber sowie Informationen zum Erwerb zusätzlicher Treiber finden Sie unter [Liste der ODBC-Treiber](../../data/odbc/odbc-driver-list.md).

##  <a name="_core_your_recordsets"></a> Die Recordsets

Für jede unterschiedliche Tabelle, Sicht oder gespeicherte Prozedur, die Sie zugreifen möchten, definieren Sie in der Regel eine Klasse, die von abgeleiteten `CRecordset`. (Die Ausnahme ist ein Datenbank-Join, in dem ein Recordset Spalten aus zwei oder mehr Tabellen darstellt.) Wenn Sie eine Recordset-Klasse ableiten, aktivieren Sie die Datensatzfeldaustausch (RFX)-Mechanismus oder der Bulk Datensatzfeldaustausch (Bulk-RFX)-Mechanismus, die ähnlich dem Dialogfeld Daten Dialogdatenaustausch (DDX)-Mechanismus. RFX und Bulk-RFX vereinfachen die Übertragung von Daten aus der Datenquelle in das Recordset; RFX überträgt Daten aus dem Recordset zudem mit der Datenquelle. Weitere Informationen finden Sie unter [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Ein Recordset-Objekt erhalten Sie Zugriff auf alle ausgewählten Datensätze an. Sie führen Sie einen Bildlauf durch die ausgewählten Datensätze mit `CRecordset` Memberfunktionen, z. B. `MoveNext` und `MovePrev`. Zur gleichen Zeit stellt nur eine der ausgewählten Datensätze, den aktuellen Datensatz einem Recordset-Objekt dar. Sie können die Felder des aktuellen Datensatzes untersuchen, durch die Deklaration Recordset Klassenmembervariablen, die Spalten der Tabelle oder der Datensätze, die aus der Datenbankabfrage zu entsprechen. Informationen über die Datenmember des Recordsets, finden Sie unter [Recordset: Architektur (ODBC)](../../data/odbc/recordset-architecture-odbc.md).

Die folgenden Themen erläutern die Details der Verwendung des Recordset-Objekte. In den Themen finden Sie in funktionale Kategorien und natürlich in der angegebenen Reihenfolge sequenzielles lesen.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Themen über die Funktionsweise der öffnen, lesen und Schließen von recordsets

- [Recordset: Architektur (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Themen über das Ändern von recordsets

- [Recordset: Hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Themen zu etwas erweiterten Techniken

- [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Recordset: Arbeiten mit großen Datenelementen (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Themen zur Funktionsweise von recordsets

- [Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Nutzen von MFC-ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Transaktion (ODBC)](../../data/odbc/transaction-odbc.md)