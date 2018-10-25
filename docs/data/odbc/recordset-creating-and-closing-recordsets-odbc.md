---
title: 'Recordset: Erstellen und Schließen von Recordsets (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4da86f43cf89720132aba0eaa611a01a3902fb1a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059024"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>Recordset: Erstellen und Schließen von Recordsets (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Um ein Recordset zu verwenden, erstellen Sie ein Recordset-Objekt, und rufen Sie dann die `Open` -Memberfunktion des Recordsets-Abfrage ausführen, und wählen Sie Datensätze. Wenn Sie mit dem Recordset fertig sind, schließen Sie und zerstören Sie das Objekt.

In diesem Thema wird Folgendes erläutert:

- [Wann und wie Sie einem Recordset-Objekt erstellen](#_core_creating_recordsets_at_run_time).

- [Wann und wie können Sie das Verhalten des Recordsets durch Parametrisieren, filtern, sortieren oder Sperren qualifizieren](#_core_setting_recordset_options).

- [Wann und wie Sie einem Recordset-Objekt schließen](#_core_closing_a_recordset).

##  <a name="_core_creating_recordsets_at_run_time"></a> Durch Recordsets erstellen zur Laufzeit

Bevor Sie Recordset-Objekte in Ihrem Programm erstellen können, müssen Sie anwendungsspezifische Recordset-Klassen. Weitere Informationen zu der dieses vorausgehenden Schritts, finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Öffnen Sie ein Dynaset oder Snapshot-Objekt, wenn Sie Datensätze aus einer Datenquelle auswählen möchten. Der Typ des zu erstellenden Objekts abhängig ist, auf was Sie tun müssen mit den Daten in Ihrer Anwendung auf Ihrer ODBC-Treiber unterstützt. Weitere Informationen finden Sie unter [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).

#### <a name="to-open-a-recordset"></a>Um ein Recordset zu öffnen.

1. Erstellen Sie ein Objekt von Ihr `CRecordset`-abgeleitete Klasse.

   Sie können das Objekt auf dem Heap oder auf den Stapelrahmen, der eine Funktion erstellen.

1. Ändern Sie optional das Standardverhalten für das Recordset. Die verfügbaren Optionen finden Sie unter [Recordset Festlegen von Optionen](#_core_setting_recordset_options).

1. Aufrufen des Objekts [öffnen](../../mfc/reference/crecordset-class.md#open) Member-Funktion.

Übergeben Sie im Konstruktor einen Zeiger auf eine `CDatabase` Objekt oder übergeben Sie NULL, um ein temporäres Objekt zu verwenden, die das Framework erstellt und öffnet basierend auf der Verbindungszeichenfolge, die vom der [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) Member-Funktion. Die `CDatabase` Objekt möglicherweise bereits eine Verbindung mit einer Datenquelle.

Der Aufruf von `Open` SQL verwendet, um Datensätze aus der Datenquelle auszuwählen. Der erste Datensatz ausgewählt wird (sofern vorhanden) ist der aktuelle Datensatz. Die Werte der Felder dieses Datensatzes werden in Felddatenmember der Recordset-Objekts gespeichert. Wenn ein Datensatz ausgewählt wurden, sowohl die `IsBOF` und `IsEOF` Member-Funktionen geben 0 zurück.

In Ihrer [öffnen](../../mfc/reference/crecordset-class.md#open) aufrufen, können Sie:

- Geben Sie an, ob das Recordset ein Dynaset oder eine Momentaufnahme ist. Durch Recordsets, die als Momentaufnahmen werden standardmäßig geöffnet werden. Alternativ können Sie eine vorwärts gerichtete-Recordset, das ermöglicht, nur den Bildlauf vorwärts, einen Datensatz zu einem Zeitpunkt angeben.

   Ein Recordset verwendet standardmäßig den Standardtyp gespeichert, der `CRecordset` Datenmember `m_nDefaultType`. Assistenten schreiben Code zum Initialisieren `m_nDefaultType` in den Recordsettyp, die Sie im Assistenten auswählen. Anstatt diese Standardeinstellung zugestimmt haben, können Sie einen anderen Recordsettyp ersetzen.

- Geben Sie eine Zeichenfolge zum Ersetzen von Standard-SQL **wählen** -Anweisung, die das Recordset wird erstellt.

- Geben Sie an, ob das Recordset, schreibgeschützt oder nur-Anhängen ist. Recordsets ermöglichen eine vollständige Aktualisierung in der Standardeinstellung jedoch können Sie einschränken, die auf nur neue Datensätze hinzufügen oder können Sie alle Updates verhindern.

Das folgende Beispiel zeigt, wie Sie eine schreibgeschützte Momentaufnahme-Objekt der Klasse öffnen `CStudentSet`, eine anwendungsspezifische Klasse:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

Nach dem Aufruf von `Open`, die Member-Funktionen und Datenmember des Objekts zum Arbeiten mit den Datensätzen verwenden. In einigen Fällen möchten Sie möglicherweise erneut Abfragen oder aktualisieren Sie das Recordset, damit Änderungen übernommen werden, die in der Datenquelle vorgenommen wurden. Weitere Informationen finden Sie unter [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).

> [!TIP]
>  Die Verbindungszeichenfolge, die Sie während der Entwicklung verwenden, möglicherweise nicht die gleiche Verbindungszeichenfolge, die letztlich Benutzer benötigen. Ideen zu verallgemeinern Ihre Anwendung in dieser Hinsicht finden Sie unter [Datenquelle: Verwalten von Verbindungen (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md).

##  <a name="_core_setting_recordset_options"></a> Festlegen von Optionen für Recordsets

Wenn Sie das Recordset-Objekt erstellt haben, aber vor dem Aufruf `Open` um Datensätze auszuwählen, sollten Sie einige Optionen steuern das Verhalten des Recordsets. Für alle Recordsets können Sie folgende Aktionen ausführen:

- Geben Sie einen [Filter](../../data/odbc/recordset-filtering-records-odbc.md) Datensatzauswahl.

- Geben Sie einen [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md) Reihenfolge für die Datensätze.

- Geben Sie [Parameter](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Sie Einträge mithilfe der Informationen abgerufen oder berechnet, die zur Laufzeit auswählen können.

Sie können auch die folgende Option festlegen, wenn Bedingungen geeignet sind:

- Wenn das Recordset aktualisierbar ist und Sperren unterstützt, geben Sie die [Sperren](../../data/odbc/recordset-locking-records-odbc.md) Methode, die für Updates verwendet wird.

> [!NOTE]
>  Um Datensatzauswahl zu beeinflussen, müssen Sie diese Optionen festlegen, vor dem Aufruf der `Open` Member-Funktion.

##  <a name="_core_closing_a_recordset"></a> Schließen eines Recordsets

Wenn Sie das Recordset abgeschlossen haben, müssen Sie löschen und dafür reservierten Speicher.

#### <a name="to-close-a-recordset"></a>Zum Schließen eines Recordsets

1. Rufen Sie die [schließen](../../mfc/reference/crecordset-class.md#close) Member-Funktion.

1. Zerstören des Recordset-Objekts.

   Wenn Sie sie auf dem Stapelrahmen einer Funktion deklariert, wird das Objekt automatisch zerstört, wenn das Objekt den Gültigkeitsbereich verlässt. Verwenden Sie andernfalls die **löschen** Operator.

`Close` frei des Recordsets `HSTMT` behandeln. Das C++-Objekt zerstört nicht.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)