---
title: 'SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f385127d1b61e1453eb7a079963da727f82f1874
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)
In diesem Thema wird Folgendes erläutert:  
  
-   Wie das Framework eine SQL­Anweisung erstellt  
  
-   Gewusst wie: Überschreiben von der SQL-Anweisung  
  
> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im Thema "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" DAO-Hilfe.  
  
## <a name="sql-statement-construction"></a>Generieren von SQL-Anweisungen  
 Recordset Basen Datensatzauswahl in erster Linie auf einer SQL **wählen** Anweisung. Wenn Sie eine Klasse mit einem Assistenten deklarieren, schreibt er eine überschreibende Version der der `GetDefaultSQL` Memberfunktion, die etwa wie folgt aussieht (für ein Recordset-Klasse aufgerufen `CAuthors`).  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 Standardmäßig gibt diese Überschreibung der Tabellenname mit dem Assistenten angegebene zurück. Im Beispiel ist der Tabellenname "Autoren". Wenn Sie des Recordsets später Aufrufen **öffnen** Memberfunktion **öffnen** erstellt eine endgültige **wählen** -Anweisung der Form:  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 wobei `table-name` durch Aufruf von `GetDefaultSQL` und `rfx-field-list` stammt von der RFX-Funktionsaufrufe in `DoFieldExchange`. Dies ist das Ergebnis für eine **wählen** Anweisung, wenn Sie es durch eine überschreibende Version zur Laufzeit zu ersetzen, obwohl Sie auch die Standard-Anweisung mit Parametern oder einen Filter ändern können.  
  
> [!NOTE]
>  Wenn Sie einen Spaltennamen angeben, der Leerzeichen enthält (oder enthalten kann), müssen Sie den Namen in eckige Klammern einschließen. Beispielsweise sollte der Name "Vorname", "[Vorname]" sein.  
  
 Zum Überschreiben der standardmäßigen **wählen** -Anweisung, übergeben Sie eine Zeichenfolge, enthält eine vollständige **wählen** Anweisung beim Aufrufen **öffnen**. Statt einen eigenen Standardzeichenfolge verwendet das Recordset die Zeichenfolge, die Sie angeben. Wenn die Austausch-Anweisung enthält einen **, in denen** -Klausel, geben Sie einen Filter in nicht **M_strFilter** da dann müsste Filtern zwei Anweisungen. Auf ähnliche Weise, wenn die Austausch-Anweisung enthält eine **ORDER BY** -Klausel, geben Sie einen Sortiervorgang in keine `m_strSort` , damit kein Sortieren zwei Anweisungen.  
  
> [!NOTE]
>  Wenn Sie Literalzeichenfolgen in Filtern (oder in anderen Teilen der SQL-Anweisung) verwenden, müssen Sie möglicherweise "Angebot" (Begrenzungszeichen einschließen) diese Zeichenfolgen mit einer DBMS-spezifische Literalpräfix suffix Zeichen (oder Zeichen).  
  
 Je nach Ihrer DBMS können Sie auch besondere syntaktische Anforderungen für Vorgänge wie das äußere Joins auftreten. Verwenden Sie ODBC-Funktionen, um diese Informationen aus der Treiber für das DBMS zu erhalten. Rufen Sie z. B. **:: SQLGetTypeInfo** für einen bestimmten Datentyp z. B. **SQL_VARCHAR**auf und fordert die **LITERAL_PREFIX-Zeichen** und **LITERAL_SUFFIX** Zeichen. Wenn Sie Datenbank-unabhängigen Code schreiben, finden Sie im Anhang C die *ODBC SDK ** Programmer's Reference* auf der MSDN Library-CD für ausführliche Informationen zur Syntax.  
  
 Einem Recordset-Objekt erstellt, die SQL-Anweisung, die zum Auswählen von Datensätzen, es sei denn, Sie eine benutzerdefinierte SQL­Anweisung übergeben verwendet wird. Vorgehensweise hängt hauptsächlich den übergebenen Wert die `lpszSQL` Parameter von der **öffnen** Memberfunktion.  
  
 Das allgemeine Format einer SQL **wählen** -Anweisung ist:  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 Eine Möglichkeit zum Hinzufügen der **DISTINCT** Schlüsselwort, um SQL-Anweisung eines Recordsets ist das Schlüsselwort in der ersten RFX-Funktionsaufruf in einbetten `DoFieldExchange`. Zum Beispiel:  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  Verwenden Sie dieses Verfahren nur mit einem Recordset als schreibgeschützt geöffnet.  
  
## <a name="overriding-the-sql-statement"></a>Überschreiben die SQL-Anweisung  
 Die folgende Tabelle zeigt die Möglichkeiten für die `lpszSQL` Parameter **öffnen**. Die Fälle in der Tabelle werden nach der Tabelle erläutert.  
  
 **Der LpszSQL-Parameter und die resultierende SQL-Zeichenfolge**  
  
|Case|Was Sie LpszSQL übergeben|Die resultierenden SELECT-Anweisung|  
|----------|------------------------------|------------------------------------|  
|1|**NULL**|**Wählen Sie** *Rfx Feldliste* **FROM** *Tabellenname*<br /><br /> `CRecordset::Open` Aufrufe `GetDefaultSQL` zum Abrufen des Namens der Tabelle. Die resultierende Zeichenfolge ist ein Fall 2 bis 5, je nachdem, was `GetDefaultSQL` zurückgibt.|  
|2|Ein Tabellenname|**Wählen Sie** *Rfx Feldliste* **FROM** *Tabellenname*<br /><br /> Die Feldliste stammt aus der RFX-Anweisungen in `DoFieldExchange`. Wenn **M_strFilter** und `m_strSort` nicht leer sind, fügt die **, in denen** und/oder **ORDER BY** Klauseln.|  
|3 *|Eine vollständige **wählen** Anweisung aber ohne eine **, in denen** oder **ORDER BY** Klausel|Als erfolgreich. Wenn **M_strFilter** und `m_strSort` nicht leer sind, fügt die **, in denen** und/oder **ORDER BY** Klauseln.|  
|4 *|Eine vollständige **wählen** -Anweisung mit einem **, in denen** und/oder **ORDER BY** Klausel|Als erfolgreich. **M_strFilter** und/oder `m_strSort` muss leer oder zwei Filter bleiben und/oder Sortierung-Anweisungen erstellt werden.|  
|5 *|Ein Aufruf einer gespeicherten Prozedur|Als erfolgreich.|  
  
 \* `m_nFields` muss kleiner oder gleich der Anzahl der Spalten in der **wählen** Anweisung. Der Datentyp jeder Spalte im angegebenen der **wählen** -Anweisung muss der Datentyp der entsprechenden Spalte der RFX-Ausgabe identisch sein.  
  
### <a name="case-1---lpszsql--null"></a>Fall 1 LpszSQL = NULL  
 Die Auswahl des Recordsets hängt von was `GetDefaultSQL` gibt zurück, wenn `CRecordset::Open` wird aufgerufen. Fällen 2 bis 5 werden die möglichen Zeichenfolgen beschrieben.  
  
### <a name="case-2---lpszsql--a-table-name"></a>Fall 2 LpszSQL = einen Tabellennamen  
 Das Recordset-Datensatzfeldaustausch (RFX) verwendet, um die Liste der Spalten aus den Spaltennamen zu erstellen, Funktionsaufrufen in der RFX in die Recordset-Klasse: f Überschreibung von `DoFieldExchange`. Wenn Sie einen Assistenten verwendet, um Recordset-Klasse deklarieren, hat diese Anfrage zum gleiche Ergebnis wie Fall 1 (vorausgesetzt, dass Sie den gleichen Tabellennamen, den Sie im Assistenten angegeben übergeben). Wenn Sie einen Assistenten zum Erstellen die Klasse nicht verwenden, ist der Fall 2 die einfachste Methode zum Erstellen der SQL-Anweisung.  
  
 Das folgende Beispiel erstellt eine SQL-Anweisung, die Datensätze aus einer MFC-datenbankanwendung auswählt. Wenn das Framework Ruft die `GetDefaultSQL` Memberfunktion, die Funktion gibt den Namen der Tabelle `SECTION`.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 Zum Abrufen der Namen der Spalten für die SQL **wählen** -Anweisung, die das Framework Ruft die `DoFieldExchange` Memberfunktion.  
  
```  
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Text(pFX, "CourseID", m_strCourseID);  
    RFX_Text(pFX, "InstructorID", m_strInstructorID);  
    RFX_Text(pFX, "RoomNo", m_strRoomNo);  
    RFX_Text(pFX, "Schedule", m_strSchedule);  
    RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 Nach Abschluss des Vorgangs, sieht die SQL-Anweisung wie folgt:  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Fall 3 LpszSQL = eine SELECT-Anweisung bzw. Sie daraus-Anweisung  
 Angabe die Spaltenliste per hand katalogisiert wird anstelle der vertrauenden Seite auf RFX, automatisch zu erstellen. Möglicherweise möchten ist erforderlich, diese wenn:  
  
-   Sollen die **DISTINCT** Schlüsselwort im Anschluss **wählen**.  
  
     Die Liste der Spalten übereinstimmen, die Spaltennamen und Datentypen in der gleichen Reihenfolge wie in der sie aufgelistet sind `DoFieldExchange`.  
  
-   Sie haben Grund manuell abrufen von Spaltenwerten mithilfe der ODBC-Funktion **:: SQLGetData** anstelle der vertrauenden Seite auf RFX zu binden und Abrufen der Spalten.  
  
     Sie sollten z. B. neue Spalten unterstützen, die den Datenbanktabellen ein Kunde der Anwendung hinzugefügt werden, nachdem die Anwendung bereitgestellt wurde. Sie müssen diese zusätzlichen Felddatenmember hinzufügen, die zur Zeit nicht bekannt waren Sie die Klasse mit einem Assistenten deklariert.  
  
     Die Liste der Spalten übereinstimmen, die Spaltennamen und Datentypen in der gleichen Reihenfolge wie in der sie aufgelistet sind `DoFieldExchange`, gefolgt von den Namen der manuell gebundenen Spalten. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Sie möchten zum Verknüpfen von Tabellen durch Angeben von mehreren Tabellen in der **FROM** Klausel.  
  
     Weitere Informationen und ein Beispiel finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Fall 4 LpszSQL = SELECT / FROM sowie WHERE und/oder ORDER BY  
 Angabe, dass alles: der Liste der Spalten (basierend auf der RFX-Aufrufe in `DoFieldExchange`), die Tabellenliste und den Inhalt der eine **, in dem** und/oder ein **ORDER BY** Klausel. Bei Angabe der **, in denen** und/oder **ORDER BY** Klauseln auf diese Weise verwenden Sie keine **M_strFilter** und/oder `m_strSort`.  
  
### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Fall 5 LpszSQL = Aufruf einer gespeicherten Prozedur  
 Wenn Sie eine vordefinierte Abfrage (z. B. eine gespeicherte Prozedur in einer Microsoft SQL Server-Datenbank) aufrufen, müssen Sie schreiben eine **Aufrufen** Anweisung in der Zeichenfolge, um übergeben `lpszSQL`. Die Assistenten unterstützen keine Deklarieren einer Recordsetklasse für eine vordefinierte Abfrage aufrufen. Nicht alle vordefinierten Abfragen geben Datensätze zurück.  
  
 Wenn eine vordefinierte Abfrage keine Datensätze zurückgibt, können Sie mithilfe der `CDatabase` Memberfunktion `ExecuteSQL` direkt. Für eine vordefinierte Abfrage, die Datensätze zurückgibt, Sie müssen auch manuell schreiben der RFX-Aufrufe `DoFieldExchange` für alle Spalten der Prozedur zurückgibt. RFX-Aufrufe müssen in der gleichen Reihenfolge sein und dieselben Typen wie die vordefinierte Abfrage zurückzugeben. Weitere Informationen finden Sie unter [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
