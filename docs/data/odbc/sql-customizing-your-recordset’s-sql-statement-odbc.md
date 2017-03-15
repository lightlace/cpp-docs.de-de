---
title: "SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)"
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
  - "Anpassen von SQL-Anweisungen"
  - "ODBC-Recordsets, SQL-Anweisungen"
  - "Überschreiben, SQL-Anweisungen"
  - "Recordsets, SQL-Anweisungen"
  - "SQL-Anweisungen, Anpassen"
  - "SQL-Anweisungen, Recordset"
  - "SQL, Öffnen von Recordsets"
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird Folgendes erläutert:  
  
-   Erstellen einer SQL\-Anweisung durch das Framework  
  
-   Überschreiben der SQL\-Anweisung  
  
> [!NOTE]
>  Diese Informationen beziehen sich auf die MFC\-ODBC\-Klassen.  Wenn Sie mit den MFC\-DAO\-Klassen arbeiten, lesen Sie in der DAO\-Hilfe das Thema "Vergleich von Microsoft Jet Database Engine\-SQL und ANSI\-SQL".  
  
## Generieren der SQL\-Anweisungen  
 Das Recordset führt die Auswahl von Datensätzen in erster Linie mit der SQL\-**SELECT**\-Anweisung durch.  Wenn Sie die Klasse mit einem Assistenten deklarieren, erstellt dieser eine überschreibende Version der `GetDefaultSQL`\-Memberfunktion, die etwa folgendermaßen aussieht \(für die Recordset\-Klasse mit der Bezeichnung `CAuthors`\).  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 Standardmäßig gibt diese überschriebene Funktion den Tabellennamen zurück, den Sie mit dem Assistenten spezifiziert haben.  In diesem Beispiel lautet der Tabellenname "AUTHORS". Wenn Sie später die **Open**\-Memberfunktion des Recordsets aufrufen, generiert **Open** die fertige **SELECT**\-Anweisung in folgender Form:  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 Hierbei wird `table-name` durch Aufruf von `GetDefaultSQL` ermittelt und `rfx-field-list` durch RFX\-Funktionsaufrufe in **DoFieldExchange** ermittelt.  Dies ist das Ergebnis einer **SELECT**\-Anweisung, sofern Sie diese nicht zur Laufzeit durch eine überschreibende Version ersetzen. Die Standardanweisung kann außerdem mit Parametern oder einem Filter verändert werden.  
  
> [!NOTE]
>  Falls Sie einen Spaltennamen angeben, der Leerzeichen enthält \(oder enthalten könnte\), müssen Sie den Namen in eckige Klammern einschließen.  Die Spalte mit dem Namen "First Name" muss also z. B. als Zeichenfolge "\[First Name\]" angegeben werden.  
  
 Um die Standard\-**SELECT**\-Anweisung zu überschreiben, übergeben Sie beim Aufruf von **Open** eine Zeichenfolge, die eine vollständige **SELECT**\-Anweisung enthält.  Statt eine eigene Zeichenfolge zu generieren, verwendet das Recordset die von Ihnen übergebene Zeichenfolge.  Spezifizieren Sie keinen Filter in m\_strFilter, falls die alternative Anweisung eine WHERE\-Klausel enthält, da in diesem Fall zwei Filteranweisungen vorlägen.  Ebenso dürfen Sie in `m_strSort` keine Sortierreihenfolge angeben, wenn die alternative Anweisung eine **ORDER BY**\-Klausel enthält, da sonst zwei Sortieranweisungen vorhanden wären.  
  
> [!NOTE]
>  Wenn Sie in Filtern \(oder in anderen Teilen der SQL\-Anweisung\) Zeichenfolgenliterale verwenden, müssen Sie diese Zeichenfolgen unter Umständen in spezielle, DBMS\-spezifische literale Begrenzungszeichen einschließen.  
  
 Abhängig vom verwendeten DBMS gelten möglicherweise auch besondere syntaktische Anforderungen für Vorgänge wie äußere Joins.  Sie können diese Informationen mithilfe der ODBC\-Funktionen des DBMS\-Treibers abrufen.  Rufen Sie z. B. **::SQLGetTypeInfo** für einen bestimmten Datentyp, wie **SQL\_VARCHAR**, auf, um das **LITERAL\_PREFIX**\-Zeichen und das **LITERAL\_SUFFIX**\-Zeichen abzurufen.  Falls Sie datenbankunabhängigen Code erstellen, finden Sie im Anhang C von *ODBC SDK* *Programmer's Reference* auf der MSDN Library\-CD detaillierte Informationen zur Syntax.  
  
 Ein Recordset\-Objekt erstellt die SQL\-Anweisung, mit der Datensätze ausgewählt werden, sofern Sie keine selbstdefinierte SQL\-Anweisung übergeben.  Wie Sie dies tun, hängt in erster Linie von dem Wert ab, den Sie im `lpszSQL`\-Parameter der **Open**\-Memberfunktion übergeben.  
  
 Die allgemeine Form einer SQL\-**SELECT**\-Anweisung sieht folgendermaßen aus:  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 Eine Möglichkeit, das Schlüsselwort **DISTINCT** in die SQL\-Anweisung des Recordsets einzufügen, ist das Einbetten des Schlüsselworts in den ersten RFX\-Funktionsaufruf in `DoFieldExchange`.  Beispiel:  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  Verwenden Sie diese Methode ausschließlich mit einem Recordset, das schreibgeschützt geöffnet wird.  
  
## Überschreiben der SQL\-Anweisung  
 In der folgenden Tabelle wird erläutert, welche Argumente Sie in dem Parameter `lpszSQL` an **Open** übergeben können.  Die in der Tabelle bezeichneten Fälle werden im Anschluss an die Tabelle erläutert.  
  
 **Der lpszSQL\-Parameter und die resultierende SQL\-Zeichenfolge**  
  
|Case|In lpszSQL übergebener Wert|Resultierende SELECT\-Anweisung|  
|----------|---------------------------------|-------------------------------------|  
|1|**NULL**|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> `CRecordset::Open` ruft `GetDefaultSQL` auf, um den Tabellennamen zu ermitteln.  Die resultierende Zeichenfolge entspricht einem der Fälle 2 bis 5, abhängig vom Rückgabewert von `GetDefaultSQL`.|  
|2|Tabellenname|**SELECT** *rfx\-field\-list* **FROM** *table\-name*<br /><br /> Die Feldliste wird den RFX\-Anweisungen in `DoFieldExchange` entnommen.  Falls **m\_strFilter** und `m_strSort` nicht leer sind, wird die **WHERE**\-Klausel und\/oder die **ORDER BY**\-Klausel hinzugefügt.|  
|3 \*|Eine vollständige **SELECT**\-Anweisung, aber ohne die **WHERE**\-Klausel bzw. die **ORDER BY**\-Klausel|Wie übergeben.  Falls **m\_strFilter** und `m_strSort` nicht leer sind, wird die **WHERE**\-Klausel und\/oder die **ORDER BY**\-Klausel hinzugefügt.|  
|4 \*|Eine vollständige **SELECT**\-Anweisung mit **WHERE**\-Klausel und\/oder **ORDER BY**\-Klausel|Wie übergeben.  **m\_strFilter** und\/oder `m_strSort` müssen leer bleiben, andernfalls würden zwei Filter\- und\/oder Sortieranweisungen erstellt.|  
|5 \*|Ein Aufruf einer gespeicherten Prozedur|Wie übergeben.|  
  
 \*`m_nFields` muss kleiner oder gleich der Anzahl der Spalten sein, die in der **SELECT**\-Anweisung angegeben werden.  Der Datentyp jeder in der **SELECT**\-Anweisung spezifizierten Spalte muss der gleiche sein wie der Datentyp der zugehörigen RFX\-Ausgabespalte.  
  
### Fall 1   lpszSQL \= NULL  
 Die Auswahl des Recordsets hängt von dem Wert ab, den `GetDefaultSQL` beim Aufruf durch `CRecordset::Open` zurückliefert.  Die Fälle 2 bis 5 beschreiben mögliche Zeichenfolgen.  
  
### Fall 2   lpszSQL \= ein Tabellenname  
 Das Recordset macht vom Datensatzfeldaustausch \(RFX\) Gebrauch, um die Spaltenliste aus den Spaltennamen zu erstellen, die bei den RFX\-Funktionsaufrufen in der `DoFieldExchange`\-Überschreibung der Recordset\-Klasse zurückgegeben werden.  Wenn Sie die Recordset\-Klasse mit einem Assistenten deklariert haben, führt dieser Fall zum selben Ergebnis wie Fall 1 \(sofern Sie denselben Tabellennamen übergeben, den Sie im Assistenten angegeben haben\).  Wenn Sie die Klasse nicht mit einem Assistenten erstellen möchten, ist Fall 2 die einfachste Methode zum Konstruieren der SQL\-Anweisung.  
  
 Im folgenden Beispiel wird eine SQL\-Anweisung konstruiert, durch die Datensätze aus einer MFC\-Datenbankanwendung ausgewählt werden.  Wenn das Framework die `GetDefaultSQL`\-Memberfunktion aufruft, gibt die Funktion den Namen der Tabelle \(`SECTION`\) zurück.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 Um für die SQL\-**SELECT**\-Anweisung die Namen der Spalten zu ermitteln, ruft das Framework die `DoFieldExchange`\-Memberfunktion auf.  
  
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
  
 Die fertige SQL\-Anweisung sieht folgendermaßen aus:  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### Fall 3   lpszSQL \= eine SELECT\/FROM\-Anweisung  
 Sie spezifizieren die Spaltenliste von Hand, statt sich auf die automatische Generierung durch RFX zu verlassen.  Sie können in folgenden Fällen auf diese Methode zurückgreifen:  
  
-   Wenn Sie nach **SELECT** das Schlüsselwort **DISTINCT** angeben möchten.  
  
     Die Spaltenliste muss den Namen und Typen der Spalten in der Reihenfolge entsprechen, in der sie in `DoFieldExchange` aufgeführt sind.  
  
-   Wenn Sie Spaltenwerte von Hand mit der ODBC\-Funktion **::SQLGetData** abrufen müssen, statt sich beim Binden und Abrufen der Spalten auf RFX zu verlassen.  
  
     Manchmal müssen Sie z. B. neue Spalten unterstützen, die ein Benutzer der Anwendung den Datenbanktabellen hinzugefügt hat, nachdem die Anwendung ausgeliefert wurde.  Sie müssen diese zusätzlichen Felddatenmember hinzufügen, die zu dem Zeitpunkt, als Sie die Klasse mit einem Assistenten deklariert haben, noch nicht bekannt waren.  
  
     Die Spaltenliste muss den Namen und Typen der Spalten in der Reihenfolge entsprechen, in der sie in `DoFieldExchange` aufgelistet sind, gefolgt von den Namen der manuell gebundenen Spalten.  Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
-   Wenn Sie Tabellen verknüpfen möchten, indem Sie mehrere Tabellen in der **FROM**\-Klausel angeben.  
  
     Weitere Informationen und ein Beispiel finden Sie unter [Recordset: Ausführen einer Verknüpfung \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
### Fall 4   lpszSQL  \= SELECT\/FROM sowie WHERE und\/oder ORDER BY  
 Sie machen alle Angaben: die Spaltenliste \(basierend auf den RFX\-Aufrufen in DoFieldExchange\), die Tabellenliste und den Inhalt der WHERE\-Klausel und\/oder der ORDER BY\-Klausel.  Falls Sie die **WHERE**\-Klausel und\/oder die **ORDER BY**\-Klausel auf diese Art spezifizieren, dürfen Sie **m\_strFilter** und\/oder `m_strSort` nicht verwenden.  
  
### Fall 5   lpszSQL \= ein Aufruf einer gespeicherten Prozedur  
 Falls Sie eine vordefinierte Abfrage aufrufen möchten \(z. B. die gespeicherte Prozedur in einer Microsoft SQL Server\-Datenbank\), müssen Sie in der Zeichenfolge, die Sie an *lpszSQL* übergeben, eine **CALL**\-Anweisung einfügen.  Die Assistenten bieten keine Unterstützung bei der Deklaration einer Recordset\-Klasse für den Aufruf einer vordefinierten Abfrage.  Nicht alle vordefinierten Abfragen geben Datensätze zurück.  
  
 Wenn eine vordefinierte Abfrage keine Datensätze zurückgibt, können Sie die `CDatabase`\-Memberfunktion `ExecuteSQL` direkt aufrufen.  Für eine vordefinierte Abfrage, die Datensätze zurückgibt, müssen Sie in `DoFieldExchange` von Hand die RFX\-Aufrufe für alle von der Prozedur zurückgegebenen Spalten erstellen.  Die RFX\-Aufrufe müssen in derselben Reihenfolge sein und dieselben Typen zurückgeben wie die vordefinierte Abfrage.  Weitere Informationen finden Sie unter [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).  
  
## Siehe auch  
 [SQL: SQL\- und C\+\+\-Datentypen \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: Durchführen direkter SQL\-Aufrufe \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)