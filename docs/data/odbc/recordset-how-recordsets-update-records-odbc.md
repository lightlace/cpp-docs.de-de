---
title: 'Recordset: Datensatzaktualisierung durch Recordsets (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
ms.openlocfilehash: bf71f562714e2dacfe75540e1e532219b3eb307f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034481"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Recordset: Datensatzaktualisierung durch Recordsets (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

Neben ihrer Fähigkeit, um Datensätze aus einer Datenquelle auszuwählen können Recordsets (optional) aktualisieren oder löschen Sie die ausgewählten Datensätze oder neue Datensätze hinzufügen. Drei Faktoren bestimmen des Recordsets Updateability: Gibt an, ob die verbundenen Datenquelle aktualisierbar ist, sind die Optionen, die Sie angeben, bei der Erstellung eines Recordset-Objekts, und der SQL, das erstellt wird.

> [!NOTE]
>  Der SQL auf dem Ihre `CRecordset` Objekt basiert kann des Recordsets Updateability beeinträchtigen. Beispielsweise wenn Ihre SQL-Anweisung einen Join enthält oder ein **GROUP BY** -Klausel legt MFC die aktualisierbarkeit auf "false" fest.

> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie die gesammelte verwenden werden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

In diesem Thema wird Folgendes erläutert:

- [Ihre Rolle Aktualisieren eines Recordsets](#_core_your_role_in_recordset_updating) und welche Aktionen das Framework für Sie ausgeführt.

- [Das Recordset als Bearbeitungspuffer](#_core_the_edit_buffer) und [Unterschiede zwischen Dynasets und Momentaufnahmen](#_core_dynasets_and_snapshots).

[Recordset: Wie AddNew, Edit und Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) beschreibt die Aktionen dieser Funktionen aus der Perspektive des Recordset-Objekts.

[Recordset: Weitere Informationen zu Aktualisierungen (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) führt Sie das Recordset-Updateverlauf durch die Erläuterung der Auswirkungen von Transaktionen auf Aktualisierungen, Auswirkungen Schließen eines Recordsets oder fortlaufenden Updates werden ausgeführt, und wie Ihre Updates mit den Updates von anderen Benutzern interagieren.

##  <a name="_core_your_role_in_recordset_updating"></a> Ihre Rolle beim Aktualisieren von Recordsets

Die folgende Tabelle zeigt die Rolle bei der Verwendung von Recordsets zum Hinzufügen, bearbeiten oder Löschen von Datensätzen, zusammen mit der Funktionsweise von des Frameworks für Sie.

### <a name="recordset-updating-you-and-the-framework"></a>Recordset zu aktualisieren: Sie und das Framework

|Benutzer|Das Framework|
|---------|-------------------|
|Bestimmen Sie, ob die Datenquelle aktualisierbar (oder erweiterbar) ist.|Stellt [CDatabase](../../mfc/reference/cdatabase-class.md) Member-Funktionen für der Datenquelle aktualisierbar oder erweiterbar ist.|
|Öffnen Sie ein aktualisierbares Recordset (eines beliebigen Typs).||
|Bestimmen, ob das Recordset aktualisierbar, durch den Aufruf ist `CRecordset` Aktualisieren von Funktionen wie `CanUpdate` oder `CanAppend`.||
|Rufen Sie Recordset Memberfunktionen zum Hinzufügen, bearbeiten und Löschen von Datensätzen.|Verwaltet die Mechanismen zum Austausch von Daten zwischen Ihrem Recordsetobjekt und die Datenquelle an.|
|Verwenden Sie optional die Transaktionen zur Kontrolle des Update-Prozesses.|Stellt `CDatabase` Member-Funktionen zur Unterstützung von Transaktionen.|

Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="_core_the_edit_buffer"></a> Der Bearbeitungspuffer

Gemeinsam die Felddatenmembern eines Recordset-Objekts dienen als Bearbeitungspuffer, die einen Datensatz enthält, den aktuellen Datensatz. Update-Vorgänge verwenden Sie diesen Puffer für den aktuellen Datensatz ausgeführt werden.

- Wenn Sie einen Eintrag hinzufügen, wird im Bearbeitungspuffer verwendet, um einen neuen Datensatz zu erstellen. Wenn Sie den Datensatz hinzugefügt haben, wird der Datensatz, der zuvor aktuellen wurde wieder aktuelle.

- Bei der Aktualisierung ist (Bearbeiten), einen Datensatz, der die Bearbeitung-Puffer verwendet, die Felddatenmember der Recordset auf neue Werte festlegen. Wenn Sie fertig sind, aktualisieren, wird der aktualisierte Datensatz immer noch aktuell.

Beim Aufruf [AddNew](../../mfc/reference/crecordset-class.md#addnew) oder [bearbeiten](../../mfc/reference/crecordset-class.md#edit), ist der aktuelle Datensatz gespeichert, sodass sie später bei Bedarf wiederhergestellt werden kann. Beim Aufruf [löschen](../../mfc/reference/crecordset-class.md#delete), des aktuellen Datensatzes wird nicht gespeichert, sondern wird als gelöscht markiert, und Sie müssen einen Bildlauf zu einem anderen Datensatz durchführen.

> [!NOTE]
>  Bearbeitungspuffer spielt keine Rolle Löschen eines Datensatzes. Wenn Sie den aktuellen Datensatz löschen, wird der Datensatz als gelöscht markiert, und das Recordset ist "nicht in einem Datensatz", bis Sie einen Bildlauf zu einem anderen Datensatz durchführen.

##  <a name="_core_dynasets_and_snapshots"></a> Dynasets und Momentaufnahmen

[Dynasets](../../data/odbc/dynaset.md) aktualisieren Sie den Inhalt eines Datensatzes, wie Sie einen Bildlauf zu dem Datensatz nach. [Momentaufnahmen](../../data/odbc/snapshot.md) statische Repräsentation der Datensätze sind, damit Sie den Inhalt eines Datensatzes nicht aktualisiert werden, es sei denn, Sie rufen [Requery](../../mfc/reference/crecordset-class.md#requery). Um alle Funktionen der Dynasets verwenden zu können, müssen Sie mit einem ODBC-Treiber arbeiten, die das richtige Maß an Unterstützung für ODBC-API entspricht. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [Dynaset](../../data/odbc/dynaset.md).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Wie AddNew, bearbeiten und Löschen von Arbeit (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)