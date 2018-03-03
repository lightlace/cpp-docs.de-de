---
title: 'Recordset: Datensatzauswahl durch Recordsets (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8664c5732c0cdf1042b6af338ea388ab29ab7863
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>Recordset: Datensatzauswahl durch Recordsets (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Ihre Rolle und die Optionen bei der Auswahl von Datensätzen](#_core_your_options_in_selecting_records).  
  
-   [Wie ein Recordset seine SQL-Anweisung erstellt, und wählt die Datensätze](#_core_how_a_recordset_constructs_its_sql_statement).  
  
-   [Was Sie tun können, um die Auswahl anpassen](#_core_customizing_the_selection).  
  
 Recordsets werden Datensätze aus einer Datenquelle über einen ODBC-Treiber auszuwählen, durch Senden von SQL-Anweisungen an den Treiber. SQL gesendet hängt davon ab, wie Sie entwerfen, und Öffnen des Recordset-Klasse.  
  
##  <a name="_core_your_options_in_selecting_records"></a>Die Optionen bei der Auswahl von Datensätzen  
 Die folgende Tabelle zeigt, welche Optionen bei der Auswahl von Datensätzen.  
  
### <a name="how-and-when-you-can-affect-a-recordset"></a>Wie und wann ein Recordset auswirken können  
  
|Wenn Sie|Sie haben folgende Möglichkeiten:|  
|--------------|-------------|  
|Deklarieren von Recordset-Klasse mit dem **Klasse hinzufügen** Assistenten|Geben Sie die Tabelle aus.<br /><br /> Geben Sie an, welche Spalten einbezogen werden sollen.<br /><br /> Finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|  
|Führen Sie die Implementierung des Recordset-Klasse|Überschreiben von Memberfunktionen wie z. B. `OnSetOptions` (Erweitert), um anwendungsspezifische Optionen festzulegen oder Standardwerte zu ändern. Geben Sie Parameterdatenmember, wenn Sie das Recordset parametrisieren möchten.|  
|Erstellen Sie ein Recordset-Objekt (vor dem Aufruf **öffnen**)|Angeben eine Suchbedingung, die für die Verwendung im (möglicherweise zusammengesetzten) eine **, in dem** -Klausel, die die Datensätze filtert. Finden Sie unter [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Geben Sie eine Sortierreihenfolge für die Verwendung in einer **ORDER BY** -Klausel, die die Einträge sortiert. Finden Sie unter [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Geben Sie Parameterwerte für alle Parameter, die Sie der Klasse hinzugefügt. Finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|  

| Führen Sie die Abfrage des Recordsets durch Aufrufen von **öffnen**| Geben Sie eine benutzerdefinierte SQL-Zeichenfolge zum Ersetzen von Standard-SQL-Zeichenfolge, die vom Assistenten zum einrichten. Finden Sie unter [CRecordset](../../mfc/reference/crecordset-class.md#open) in der *Class Library Reference* und [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |  

| Rufen Sie **Requery** auf das Recordset mit den aktuellen Werten in der Datenquelle aktualisieren | Geben Sie neue Parameter, filtern oder sortieren. Finden Sie unter [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a>Wie die SQL-Anweisung erstellt ein Recordset  
 Beim Aufrufen des Recordset-Objekts [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion **öffnen** erstellt eine SQL-Anweisung mit einigen oder allen der folgenden Bestandteile:  
  
-   Die **LpszSQL** Parameter übergeben wird, um **öffnen**. Wenn dies nicht der **NULL**, dieser Parameter gibt an, eine benutzerdefinierte SQL-Zeichenfolge oder einen Teil einer. Das Framework analysiert die Zeichenfolge an. Wenn die Zeichenfolge eine SQL **wählen** -Anweisung oder eine ODBC- **Aufrufen** die Framework-Anweisung verwendet die Zeichenfolge als SQL-Anweisung eines Recordsets. Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, wird das Framework verwendet, was bereitgestellt wird, die zum Erstellen einer SQL **FROM** Klausel.  
  
-   Die zurückgegebene Zeichenfolge [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql). Standardmäßig Dies ist der Name der Tabelle, die Sie für das Recordset im Assistenten angegeben haben, aber Sie können ändern, was die Funktion zurückgibt. Das Framework ruft `GetDefaultSQL` – Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, wird davon ausgegangen, als einen Tabellennamen ein, die verwendet wird, eine SQL-Zeichenfolge erstellen.  
  

-   Die Felddatenmember der Recordset, die auf bestimmte Spalten der Tabelle gebunden werden. Das Framework bindet Datensatz Spalten mit den Adressen diesen Member lautet deren Verwendung als Puffer. Das Framework stellt die Korrelation der Felddatenmember Tabellenspalten aus der [RFX](../../data/odbc/record-field-exchange-using-rfx.md) oder Bulk-RFX-Funktionsaufrufe in des Recordsets [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) Memberfunktion.  
  
-   Die [Filter](../../data/odbc/recordset-filtering-records-odbc.md) für das Recordset, sofern vorhanden, enthalten der [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) -Datenmember. Das Framework verwendet diese Zeichenfolge um eine SQL-Konstrukt **, in denen** Klausel.  
  
-   Die [sortieren](../../data/odbc/recordset-sorting-records-odbc.md) Reihenfolge für das Recordset, wenn vorhanden, die in enthaltenen der [M_strSort](../../mfc/reference/crecordset-class.md#m_strsort) -Datenmember. Das Framework verwendet diese Zeichenfolge um eine SQL-Konstrukt **ORDER BY** Klausel.  

  
    > [!TIP]
    >  Mit der SQL- **GROUP BY** -Klausel (und möglicherweise die **HAVING** Klausel), fügen Sie die Klauseln an das Ende der Filterzeichenfolge.  
  
-   Die Werte eines beliebigen [Parameterdatenmember](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) Geben Sie für die Klasse. Nur vor dem aufrufen, legen Sie Parameterwerte **öffnen** oder **Requery**. Das Framework bindet die Parameterwerte "?"-Platzhalter in der SQL-Zeichenfolge. Zum Zeitpunkt der Kompilierung Geben Sie die Zeichenfolge mit Platzhaltern. Zur Laufzeit füllt das Framework die Details, die basierend auf den Parameterwerten, die Sie übergeben.  
  
 **Open** erstellt eine SQL- **wählen** hieraus Anweisung. Finden Sie unter [Anpassen der Auswahl](#_core_customizing_the_selection) Weitere Informationen darüber, wie das Framework der Bestandteile verwendet.  
  
 Nach dem Erstellen der Anweisung **öffnen** sendet den SQL ODBC-Treiber-Manager (und die ODBC-Cursorbibliothek ist im Arbeitsspeicher), der es sich bei dem ODBC-Treiber für ein bestimmtes DBMS sendet. Der Treiber kommuniziert mit dem DBMS, um die Auswahl in der Datenquelle durchzuführen und ruft den ersten Datensatz. Das Framework lädt den Datensatz in die Felddatenmember der Recordset.  
  
 Sie können eine Kombination dieser Techniken verwenden, öffnen [Tabellen](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) und erstellen eine Abfrage auf Grundlage einer [Join](../../data/odbc/recordset-performing-a-join-odbc.md) von mehreren Tabellen. Mit zusätzlichen Anpassung, rufen Sie [vordefinierte Abfragen](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (gespeicherte Prozeduren), wählen Sie Tabellenspalten zur Entwurfszeit nicht bekannt und [binden](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) diese Recordsetfelder, oder Sie können die meisten anderen ausführen Datenzugriffsaufgaben. Aufgaben, die durch das Anpassen von Recordsets kann nicht ausgeführt können weiterhin ausgeführt werden, indem [ODBC API-Funktionen aufrufen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) oder Ausführen von SQL-Anweisungen direkt [CDatabase:: ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
##  <a name="_core_customizing_the_selection"></a>Anpassen der Auswahl  
 Außer der Angabe eines Filters, eine Sortierreihenfolge oder Parametern, können Sie die folgenden Aktionen zum Anpassen der Auswahl des Recordsets ausführen:  
  
-   Übergeben Sie eine benutzerdefinierte SQL-Zeichenfolge in **LpszSQL** beim Aufruf [öffnen](../../mfc/reference/crecordset-class.md#open) für das Recordset. Nichts übergebenen **LpsqSQL** hat Vorrang vor was die [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) Memberfunktion gibt.  
  
     Weitere Informationen finden Sie unter [SQL: SQL-Anweisung Anpassen eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), das beschreibt der Types von SQL-Anweisungen (oder partielle-Anweisungen) können Sie übergeben **öffnen** und welche Aktion das Framework ausführt mit ihnen.  
  
    > [!NOTE]
    >  Wenn die benutzerdefinierte Zeichenfolge, die Sie übergeben nicht mit "SELECT" oder "{CALL" beginnt, wird MFC davon ausgegangen, dass es ein Tabellenname enthält. Dies gilt auch für die nächste Aufzählung Element.  
  
-   Ändern Sie die Zeichenfolge, die vom Assistenten, in des Recordsets geschrieben `GetDefaultSQL` Memberfunktion. Bearbeiten Sie die Funktion Code ändern, was zurückgegeben. Standardmäßig schreibt der Assistent eine `GetDefaultSQL` Funktion, die Namen einer einzelnen Tabelle zurückgibt.  
  
     Dass `GetDefaultSQL` jedes der Elemente, die Sie übergeben können Zurückgeben der **LpszSQL** Parameter **öffnen**. Wenn Sie nicht in eine benutzerdefinierte SQL-Zeichenfolge übergeben **LpszSQL**, verwendet das Framework die Zeichenfolge, die `GetDefaultSQL` zurückgibt. Mindestens `GetDefaultSQL` muss einen Namen für die einzelnen Tabelle zurückgeben. Aber mehrere Tabellennamen, einen vollständigen zurückgeben **auswählen** einen ODBC-Anweisung **Aufrufen** -Anweisung und So weiter. Eine Liste der Elemente, die Sie zum übergeben können **LpszSQL** – oder `GetDefaultSQL` zurück – finden Sie unter [SQL: SQL-Anweisung Anpassen eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
     Wenn Sie eine Verknüpfung von zwei oder mehr Tabellen ausführen, Schreiben Sie `GetDefaultSQL` zum Anpassen der Liste ' Tabelle ' verwendet werden, in der SQL **FROM** Klausel. Weitere Informationen finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  

-   Binden Sie manuell zusätzliche Felddatenmember, z. B. anhand von Informationen, die Sie erhalten das Schema der Datenquelle zur Laufzeit. Sie Felddatenmember der Recordset-Klasse hinzufügen [RFX](../../data/odbc/record-field-exchange-using-rfx.md) oder Bulk-RFX-Funktionsaufrufe sind, um die [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) oder [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) Memberfunktion ist, und Initialisierungen Datenmember im Klassenkonstruktor. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Recordset-Memberfunktionen, z. B. überschreiben `OnSetOptions`, anwendungsspezifische Optionen festlegen oder Standardwerte zu überschreiben.  
  
 Wenn Sie das Recordset als Grundlage für eine komplexe SQL­Anweisung möchten, müssen Sie eine Kombination dieser Anpassungsmethoden verwenden. Z. B. möglicherweise SQL-Klauseln können verwendet werden sollen, und Schlüsselwörter, die von Recordsets oder vielleicht nicht direkt unterstützt mehrere Tabellen verknüpft sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)