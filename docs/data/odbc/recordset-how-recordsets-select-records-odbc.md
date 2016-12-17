---
title: "Recordset: Datensatzauswahl durch Recordsets (ODBC)"
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
  - "ODBC-Recordsets, Auswählen von Datensätzen"
  - "Datensatzauswahl, ODBC-Recordsets"
  - "Datensätze, Auswählen"
  - "Recordsets, Erstellen von SQL-Anweisungen"
  - "Recordsets, Auswählen von Datensätzen"
  - "SQL-Anweisungen, Recordset"
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Datensatzauswahl durch Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Aufgaben und Optionen bei der Auswahl von Datensätzen](#_core_your_options_in_selecting_records).  
  
-   [Wie ein Recordset seine SQL\-Anweisung zusammenstellt und Datensätze auswählt](#_core_how_a_recordset_constructs_its_sql_statement).  
  
-   [Anpassungsmöglichkeiten bei der Auswahl](#_core_customizing_the_selection).  
  
 Recordsets wählen Datensätze aus einer Datenquelle aus, indem sie SQL\-Anweisungen an einen ODBC\-Treiber schicken.  Welche SQL\-Anweisungen übertragen werden, hängt davon ab, wie Sie die Recordset\-Klasse entwerfen und öffnen.  
  
##  <a name="_core_your_options_in_selecting_records"></a> Optionen bei der Auswahl von Datensätzen  
 Die folgende Tabelle zeigt, welche Optionen es bei der Auswahl von Datensätzen gibt.  
  
### Manipulation eines Recordsets  
  
|Wenn Sie|Können Sie|  
|--------------|----------------|  
|Eine Recordset\-Klasse mit dem Assistenten zum **Hinzufügen von Klassen** deklarieren|Festlegen, aus welcher Tabelle die Datensätze ausgewählt werden sollen.<br /><br /> Angeben, welche Spalten aufgenommen werden.<br /><br /> Siehe [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).|  
|Die Implementierung der Recordset\-Klasse fertig stellen|Überschreiben Sie Memberfunktionen, z. B. `OnSetOptions` \(weiterführendes Thema\), um anwendungsspezifische Optionen einzustellen oder Standardwerte zu ändern.  Geben Sie Parameterdatenmember an, falls Sie das Recordset parametrisieren möchten.|  
|Ein Recordset\-Objekt konstruieren \(bevor Sie **Open** aufrufen\)|Eine Suchbedingung \(eventuell aus mehreren Einzelbedingungen zusammengesetzt\) für eine **WHERE**\-Klausel angeben, der die Datensätze filtert.  Siehe [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md).<br /><br /> Eine Sortierreihenfolge für eine **ORDER BY**\-Klausel angeben, mit der die Datensätze sortiert werden.  Siehe [Recordset: Sortieren von Datensätzen \(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md).<br /><br /> Werte für alle Parameter angeben, die Sie der Klasse hinzugefügt haben.  Siehe [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).|  
|Die Abfrage des Recordsets durch Aufruf von **Open** ausführen|Eine benutzerdefinierte SQL\-Zeichenfolge angeben, die die Standard\-SQL\-Zeichenfolge ersetzt, die vom Assistenten erstellt wurde.  Siehe [CRecordset::Open](../Topic/CRecordset::Open.md) in der *Class Library Reference* und [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).|  
|**Requery** aufrufen, um das Recordset mit den neuesten Werten aus der Datenquelle zu aktualisieren|Neue Parameter angeben, filtern oder sortieren.  Siehe [Recordset: Erneutes Abfragen eines Recordsets \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md).|  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> Wie ein Recordset seine SQL\-Anweisung konstruiert  
 Wenn Sie die [Open](../Topic/CRecordset::Open.md)\-Memberfunktion eines Recordset\-Objekts aufrufen, erstellt **Open** eine SQL\-Anweisung mit einigen oder allen der folgenden Bestandteile:  
  
-   Der an **Open** übergebene **lpszSQL**\-Parameter.  Wenn er nicht **NULL** ist, enthält dieser Parameter eine benutzerdefinierte SQL\-Zeichenfolge oder einen Teil davon.  Das Framework durchsucht die Zeichenfolge.  Falls es sich um eine SQL\-SELECT\-Anweisung oder eine ODBC\-CALL\-Anweisung handelt, verwendet das Framework diese Zeichenfolge als SQL\-Anweisung des Recordsets.  Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, verwendet das Framework die bereitgestellte Zeichenfolge zum Aufbau einer SQL\-**FROM**\-Klausel.  
  
-   Die von [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) zurückgegebene Zeichenfolge.  Standardmäßig ist dies der Name der Tabelle, die Sie im Assistenten für das Recordset ausgewählt hatten. Sie können den Rückgabewert der Funktion jedoch ändern.  Das Framework ruft `GetDefaultSQL` auf. Wenn die Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, wird sie als Tabellenname interpretiert, mit dem eine SQL\-Zeichenfolge konstruiert wird.  
  
-   Die Felddatenmember des Recordsets, die an bestimmte Spalten der Tabelle gebunden werden sollen.  Das Framework bindet Datensatzspalten an die Adressen dieser Datenmember und setzt sie als Puffer ein.  Das Framework stellt die Zuordnungsart zwischen Felddatenmembern und Tabellenspalten fest, und zwar anhand der [RFX](../../data/odbc/record-field-exchange-using-rfx.md)\-Funktionsaufrufe oder RFX\-Sammelfunktionsaufrufe der [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Memberfunktion oder der [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)\-Memberfunktion des Recordsets.  
  
-   Der [Filter](../../data/odbc/recordset-filtering-records-odbc.md) des Recordsets, der \(falls vorhanden\) im [m\_strFilter](../Topic/CRecordset::m_strFilter.md)\-Datenmember angegeben ist.  Das Framework konstruiert mit dieser Zeichenfolge eine SQL\-**WHERE**\-Klausel.  
  
-   Die [Sortierreihenfolge](../../data/odbc/recordset-sorting-records-odbc.md) des Recordsets, die \(falls vorhanden\) im [m\_strSort](../Topic/CRecordset::m_strSort.md)\-Datenmember angegeben ist.  Das Framework konstruiert mit dieser Zeichenfolge eine SQL\-**ORDER BY**\-Klausel.  
  
    > [!TIP]
    >  Wenn Sie eine SQL\-**GROUP BY**\-Klausel und möglicherweise eine **HAVING**\-Klausel verwenden möchten, hängen Sie diese Klauseln an das Ende der Filterzeichenfolge an.  
  
-   Die Werte der [Parameterdatenmember](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md), die Sie für die Klasse angegeben haben.  Parameterwerte stellen Sie unmittelbar vor dem Aufruf von **Open** oder **Requery** ein.  Das Framework bindet die Parameterwerte an "?"\-Platzhalter in der SQL\-Zeichenfolge.  Zur Kompilierungszeit geben Sie eine Zeichenfolge an, die Platzhalter enthält.  Zur Laufzeit trägt das Framework die Details basierend auf den bereitgestellten Parameterwerten ein.  
  
 **Open** konstruiert hieraus eine SQL\-**SELECT**\-Anweisung.  Details darüber, wie das Framework diese Elemente verarbeitet, finden Sie unter [Anpassen der Auswahl](#_core_customizing_the_selection).  
  
 Nach dem Konstruieren der Anweisung überträgt **Open** die SQL\-Anweisung an den ODBC\-Treiber\-Manager \(und die ODBC\-Cursorbibliothek, falls diese geladen ist\), der sie an den ODBC\-Treiber für ein bestimmtes DBMS weitergibt.  Der Treiber kommuniziert mit dem DBMS, um die Auswahl in der Datenquelle durchzuführen, und ruft den ersten Datensatz ab.  Das Framework lädt den Datensatz in die Felddatenmember des Recordsets.  
  
 Sie können eine Kombination dieser Techniken verwenden, um [Tabellen](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) zu öffnen und eine Abfrage zu erstellen, die auf einem [Join](../../data/odbc/recordset-performing-a-join-odbc.md) mehrerer Tabellen basiert.  Durch eine erweiterte Anpassung können Sie auch [vordefinierte Abfragen](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) \(gespeicherte Prozeduren\) aufrufen, Tabellenspalten auswählen, die zur Entwurfszeit noch nicht bekannt waren, und diese an Recordsetfelder [binden](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) bzw. viele weitere Datenzugriffsaufgaben durchführen.  Aufgaben, die Sie durch Anpassen der Recordsets nicht durchführen können, können dennoch durch den [Aufruf von ODBC\-API\-Funktionen](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) oder die direkte Ausführung von SQL\-Anweisungen mit [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) realisiert werden.  
  
##  <a name="_core_customizing_the_selection"></a> Anpassen der Auswahl  
 Neben dem Einsatz eines Filters, einer Sortierreihenfolge oder von Parametern können Sie die Auswahl des Recordsets mit folgenden Maßnahmen anpassen:  
  
-   Übergeben Sie in **lpszSQL** eine benutzerdefinierte SQL\-Zeichenfolge, wenn Sie die [Open](../Topic/CRecordset::Open.md)\-Funktion für das Recordset aufrufen.  Die in **lpsqSQL** übergebene Zeichenfolge hat eine höhere Priorität als diejenige, die von der [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)\-Memberfunktion zurückgegeben wird.  
  
     Weitere Informationen finden Sie unter [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md). Hier werden die Typen der SQL\-Anweisungen \(oder teilweisen Anweisungen\) beschrieben, die Sie an **Open** übergeben können, und welche Operationen das Framework mit diesen Typen durchführt.  
  
    > [!NOTE]
    >  Sofern die von Ihnen übergebene benutzerdefinierte Zeichenfolge nicht mit "SELECT" oder "{CALL" beginnt, interpretiert MFC sie als Tabellennamen.  Dies gilt auch für das nächste Element in dieser Aufzählung.  
  
-   Ändern Sie die Zeichenfolge, die der Assistent in die `GetDefaultSQL`\-Memberfunktion des Recordsets geschrieben hat.  Bearbeiten Sie im Quellcode der Funktion den Rückgabewert.  Standardmäßig schreibt der Assistent eine `GetDefaultSQL`\-Funktion, die einen einzigen Tabellennamen zurückgibt.  
  
     Sie können `GetDefaultSQL` jedes der Elemente zurückgeben lassen, das Sie auch im **lpszSQL**\-Parameter an **Open** übergeben können.  Wenn Sie keine benutzerdefinierte SQL\-Zeichenfolge in **lpszSQL** übergeben, verwendet das Framework die von `GetDefaultSQL` zurückgegebene Zeichenfolge.  `GetDefaultSQL` muss zumindest den Namen einer einzigen Tabelle zurückgeben.  Es können aber auch mehrere Tabellennamen zurückgegeben werden, eine vollständige **SELECT**\-Anweisung, eine ODBC\-**CALL**\-Anweisung usw.  Eine Liste aller Elemente, die Sie an **lpszSQL** übergeben können oder die `GetDefaultSQL` zurückgeben kann, finden Sie unter [SQL: Anpassen der SQL\-Anweisung eines Recordsets \(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md).  
  
     Falls Sie einen Join über zwei oder mehr Tabellen ausführen möchten, schreiben Sie `GetDefaultSQL` um, um die Tabellenliste in der SQL\-**FROM**\-Klausel anzupassen.  Weitere Informationen hierzu finden Sie unter [Recordset: Ausführen eines Joins \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Binden Sie von Hand zusätzliche Felddatenmember, z. B. anhand von Informationen über das Schema der Datenquelle, die Sie erst zur Laufzeit ermitteln.  Fügen Sie der Recordset\-Klasse Felddatenmember hinzu, tragen Sie entsprechende [RFX](../../data/odbc/record-field-exchange-using-rfx.md)\-Funktionsaufrufe oder RFX\-Sammelfunktionsaufrufe in die [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Memberfunktion oder [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)\-Memberfunktion ein, und fügen Sie Initialisierungen der Datenmember im Klassenkonstruktor hinzu.  Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Überschreiben Sie Memberfunktionen der Recordset\-Klasse, z. B. `OnSetOptions`, um anwendungsspezifische Optionen einzustellen oder Standardwerte zu überschreiben.  
  
 Wenn das Recordset auf einer komplexen SQL\-Anweisung basieren soll, müssen Sie eine Kombination dieser Anpassungsmethoden verwenden.  Beispiele für solche Verwendungszwecke sind das Verwenden von SQL\-Klauseln und SQL\-Schlüsselwörtern, die von Recordsets nicht direkt unterstützt werden, oder ein Join mehrerer Tabellen.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [Recordset: Sperren von Datensätzen \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)