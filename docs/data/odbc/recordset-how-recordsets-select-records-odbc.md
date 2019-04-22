---
title: 'Recordset: Datensatzauswahl durch Recordsets (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
ms.openlocfilehash: 310481a6ea6637de817bf29d528cbdfe70ae70db
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041324"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Recordset: Datensatzauswahl durch Recordsets (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird Folgendes erläutert:

- [Ihre Rolle und die Optionen bei der Auswahl von Datensätzen](#_core_your_options_in_selecting_records).

- [Wie ein Recordset erstellt die SQL-Anweisung, und wählt die Datensätze](#_core_how_a_recordset_constructs_its_sql_statement).

- [Was Sie tun können, um die Auswahl anpassen](#_core_customizing_the_selection).

Durch Recordsets wählen Datensätze aus einer Datenquelle über einen ODBC-Treiber per SQL-Anweisungen an den Treiber. Die SQL-Anweisung gesendet hängt davon ab, wie Sie entwerfen, und Öffnen des Recordset-Klasse.

##  <a name="_core_your_options_in_selecting_records"></a> Optionen bei der Auswahl von Datensätzen

Die folgende Tabelle zeigt die Optionen bei der Auswahl von Datensätzen.

### <a name="how-and-when-you-can-affect-a-recordset"></a>Wie und wann Sie ein Recordset beeinflussen können

|Wenn Sie|Sie haben folgende Möglichkeiten:|
|--------------|-------------|
|Recordset-Klasse mit deklarieren die **Klasse hinzufügen** Assistenten|Geben Sie die Tabelle aus.<br /><br /> Geben Sie an, welche Spalten einbezogen werden sollen.<br /><br /> Finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|
|Führen Sie Ihre Implementierung des Recordset-Klasse|Überschreiben Sie die Member-Funktionen wie z. B. `OnSetOptions` (Erweitert), um anwendungsspezifische Optionen zu festzulegen oder um Standardwerte zu ändern. Geben Sie Parameterdatenmember, wenn Sie eine parametrisierte Abfrage soll.|
|Erstellen Sie ein Recordset-Objekt (vor dem Aufruf `Open`)|Geben Sie eine Suchbedingung, die für die Verwendung im (möglicherweise kombiniertes) eine **, in denen** -Klausel, die die Datensätze zu filtern. Finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Geben Sie eine Sortierreihenfolge für die Verwendung in einer **ORDER BY** -Klausel, die die Datensätze sortiert. Finden Sie unter [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Geben Sie Parameterwerte für alle Parameter, die Sie der Klasse hinzugefügt. Finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|

| Führen Sie die Abfrage des Recordsets durch Aufrufen von `Open`| Geben Sie eine benutzerdefinierte SQL-Zeichenfolge zum Ersetzen der standardmäßigen SQL-Zeichenfolge, die vom Assistenten zum einrichten. Finden Sie unter [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) in die *Class Library Reference* und [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |

| Rufen Sie `Requery` auf das Recordset mit den aktuellen Werten in der Datenquelle aktualisieren | Geben Sie die neuen Parametern, filtern oder sortieren. Finden Sie unter [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |

##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Wie die SQL-Anweisung erstellt ein Recordset

Beim Aufruf eines Recordset-Objekts [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion `Open` erstellt eine SQL-Anweisung, die mit einige oder alle der folgenden Bestandteile:

- Die *LpszSQL* übergebene Parameter `Open`. Falls ungleich NULL, gibt dieser Parameter eine benutzerdefinierte SQL-Zeichenfolge oder einen Teil eines. Das Framework analysiert die Zeichenfolge an. Wenn die Zeichenfolge eine SQL **wählen** -Anweisung oder einer ODBC- **Aufrufen** der Framework-Anweisung verwendet die Zeichenfolge als SQL-Anweisung eines Recordsets. Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, wird das Framework verwendet, die zum Erstellen einer SQL bereitgestellte **FROM** Klausel.

- Die Zeichenfolge, die vom [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql). Standardmäßig Dies ist der Name der Tabelle, die Sie für das Recordset im Assistenten angegeben haben, aber Sie können ändern, was die Funktion zurückgibt. Das Framework ruft `GetDefaultSQL` – Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, wird der Wert um einen Tabellennamen ein, zu sein, die zum Erstellen einer SQL-Zeichenfolge verwendet wird.


- Die Felddatenmember des Recordset-Objekts, die auf bestimmte Spalten der Tabelle gebunden werden. Das Framework bindet an die Adressen dieser Member, die als Puffer. Das Framework stellt die Korrelation der Felddatenmember Tabellenspalten aus der [RFX](../../data/odbc/record-field-exchange-using-rfx.md) oder der Bulk-RFX-Funktionsaufrufe in der Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) Member-Funktion.

- Die [Filter](../../data/odbc/recordset-filtering-records-odbc.md) für das Recordset, sofern vorhanden, innerhalb der [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) -Datenmember. Das Framework verwendet diese Zeichenfolge, um eine SQL-Konstrukt **, in denen** Klausel.

- Die [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md) Reihenfolge für das Recordset, falls vorhanden, die in enthaltenen der [M_strSort](../../mfc/reference/crecordset-class.md#m_strsort) -Datenmember. Das Framework verwendet diese Zeichenfolge, um eine SQL-Konstrukt **ORDER BY** Klausel.

   > [!TIP]
   > Zur Verwendung der SQL **GROUP BY** Klausel (und möglicherweise die **HAVING** Klausel), fügen Sie die Klauseln an das Ende der Filterzeichenfolge.

- Die Werte eines beliebigen [Parameterdatenmember](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Sie für die Klasse angegeben. Legen Sie Parameterwerte nur vor dem Aufruf `Open` oder `Requery`. Das Framework bindet die Parameterwerte, "?" Platzhalter in der SQL-Zeichenfolge. Geben Sie zum Zeitpunkt der Kompilierung eine Zeichenfolge mit Platzhaltern. Zur Laufzeit füllt das Framework die Details basierend auf den Parameterwerten, die Sie übergeben.

`Open` erstellt eine SQL- **wählen** hieraus Anweisung. Finden Sie unter [Anpassen der Auswahl](#_core_customizing_the_selection) Einzelheiten darüber, wie das Framework die Zutaten zusammen verwendet.

Nach dem Erstellen der Anweisung `Open` sendet die SQL-Anweisung der ODBC-Treiber-Manager (und die ODBC-Cursorbibliothek, wenn es im Speicher befindet), der es sich bei den ODBC-Treiber für ein bestimmtes DBMS sendet. Der Treiber kommuniziert mit dem DBMS, um die Auswahl für die Datenquelle auszuführen und den ersten Datensatz abgerufen. Das Framework lädt den Datensatz in den Felddatenmembern des Recordset-Objekts.

Sie können eine Kombination dieser Techniken um zu öffnen [Tabellen](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) und zum Erstellen einer Abfrage, die basierend auf einer [Join](../../data/odbc/recordset-performing-a-join-odbc.md) von mehreren Tabellen. Mit zusätzliche Anpassungen vorzunehmen, können Sie aufrufen [vordefinierte Abfragen](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (gespeicherte Prozeduren), wählen Sie Spalten, die zur Entwurfszeit nicht bekannt. der Tabelle und [binden](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) Recordset-Feldern oder Sie können die meisten anderen ausführen Datenzugriffsaufgaben. Aufgaben, die Sie durch das Anpassen von Recordsets erledigen können nicht weiterhin ausgeführt werden können [ODBC-API-Funktionen aufrufen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) oder Ausführen von SQL-Anweisungen direkt [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).

##  <a name="_core_customizing_the_selection"></a> Anpassen der Auswahl

Neben der Angabe eines Filters, eine Sortierreihenfolge oder Parametern, können Sie die folgenden Aktionen zum Anpassen der Auswahl des Recordsets ausführen:

- Übergeben Sie eine benutzerdefinierte SQL-Zeichenfolge in *LpszSQL* beim Aufruf [öffnen](../../mfc/reference/crecordset-class.md#open) für das Recordset. Alles was Sie übergeben *LpsqSQL* hat Vorrang vor was die [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) Memberfunktion zurückgegeben.

   Weitere Informationen finden Sie unter [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), das beschreibt der Types des SQL-Anweisungen (oder teilweise Anweisungen), die Sie an übergeben können `Open` und welche Aktionen das Framework mit ihnen ausgeführt.

    > [!NOTE]
    >  Wenn die benutzerdefinierte Zeichenfolge, die Sie übergeben nicht mit "SELECT" oder "{CALL" beginnt, wird MFC davon ausgegangen, dass sie einen Tabellennamen enthält. Dies gilt auch für das nächste Aufzählungselement zu finden.

- Ändern Sie die Zeichenfolge, die der Assistent in des Recordsets schreibt `GetDefaultSQL` Member-Funktion. Bearbeiten Sie den Code der Funktion zum Ändern der Rückgabewerte. Standardmäßig schreibt der Assistent eine `GetDefaultSQL` Funktion, die Namen einer einzelnen Tabelle zurückgibt.

   Sie haben `GetDefaultSQL` Zurückgeben der Elemente, die Sie übergeben können die *LpszSQL* Parameter `Open`. Wenn Sie nicht in eine benutzerdefinierte SQL-Zeichenfolge übergeben *LpszSQL*, verwendet das Framework die Zeichenfolge, die `GetDefaultSQL` zurückgibt. Mindestens `GetDefaultSQL` muss den Namen einer einzelnen Tabelle zurückgeben. Aber Sie können mehrere Tabellennamen, einen vollständigen zurückgegeben haben **auswählen** einen ODBC-Anweisung **Aufrufen** -Anweisung und So weiter. Eine Liste der Elemente, die Sie an übergeben können *LpszSQL* – oder `GetDefaultSQL` zurückgeben, finden Sie unter [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

   Wenn Sie einen Join der zwei oder mehr Tabellen ausführen, Schreiben Sie `GetDefaultSQL` zum Anpassen von der Tabellenliste in der SQL **FROM** Klausel. Weitere Informationen finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).


- Binden Sie manuell zusätzliche Felddatenmember, z. B. anhand von Informationen, die Sie erhalten über das Schema der Datenquelle zur Laufzeit. Fügen Sie Felddatenmember der Recordset-Klasse [RFX](../../data/odbc/record-field-exchange-using-rfx.md) oder der Bulk-RFX-Funktion aufruft, bis sie die [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) Member-Funktion, und Initialisierungen Datenmember im Konstruktor Klasse. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Überschreiben Sie das Recordset-Member-Funktionen, z. B. `OnSetOptions`, um anwendungsspezifische Optionen festzulegen oder um Standardwerte zu überschreiben.

Wenn das Recordset als Grundlage für eine komplexe SQL­Anweisung werden sollen, müssen Sie eine Kombination dieser Techniken für die Anpassung zu verwenden. Z. B. möglicherweise SQL-Klauseln verwendet werden sollen, und Schlüsselwörter, die von Recordsets oder vielleicht nicht direkt unterstützt werden mehrere Tabellen verknüpft.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)