---
title: 'SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: eabaab019ee94b0c5617573c534d920ec710e9b2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036194"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)

In diesem Thema wird Folgendes erläutert:

- Wie wird eine SQL-Anweisung erstellt das framework

- Gewusst wie: Überschreiben von der SQL-Anweisung

> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" in-DAO-Hilfe.

## <a name="sql-statement-construction"></a>Generieren von SQL-Anweisungen

Das Recordset führt die Auswahl von Datensätzen in erster Linie auf einer SQL **wählen** Anweisung. Wenn Sie die Klasse mit einem Assistenten deklarieren, erstellt es eine überschreibende Version von der `GetDefaultSQL` Memberfunktion, die etwa wie folgt aussieht (für ein Recordset-Klasse aufgerufen `CAuthors`).

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

Standardmäßig gibt dieser Überschreibung den Tabellennamen, die, den Sie mit dem Assistenten angegeben haben. Im Beispiel ist der Tabellenname "Autoren". Wenn Sie später der Recordsets aufrufen `Open` Member-Funktion `Open` erstellt eine endgültige **wählen** -Anweisung der Form:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

wo `table-name` durch Aufruf von `GetDefaultSQL` und `rfx-field-list` aus einer RFX-Funktionsaufrufe in `DoFieldExchange`. Dies ist das Ergebnis für eine **wählen** Anweisung, wenn durch eine überschreibende Version zur Laufzeit ersetzt werden, obwohl Sie auch die Standard-Anweisung mit Parametern oder einen Filter ändern können.

> [!NOTE]
>  Wenn Sie einen Spaltennamen angeben, der Leerzeichen enthält (oder enthalten kann), müssen Sie den Namen in eckige Klammern einschließen. Beispielsweise sollte der Name "First Name", "[First Name]" sein.

Zum Überschreiben des Standardwerts **wählen** -Anweisung, übergeben Sie eine Zeichenfolge mit einer vollständigen **wählen** -Anweisung, wenn Sie aufrufen `Open`. Anstatt eine eigene Zeichenfolge erstellt wird, verwendet das Recordset die Zeichenfolge, die Sie angeben. Wenn die Ersatz-Anweisung enthält einen **, in denen** -Klausel, geben Sie einen Filter in nicht `m_strFilter` , da Sie sich dann müssten Filtern zwei Anweisungen. Auf ähnliche Weise, wenn die Ersatz-Anweisung enthält eine **ORDER BY** -Klausel, geben Sie eine Sortierung in nicht `m_strSort` , damit Sie keine werden zwei Arten Anweisungen.

> [!NOTE]
>  Wenn Sie Literalzeichenfolgen in Ihren Filtern (oder andere Teile der SQL-Anweisung) verwenden, müssen Sie möglicherweise "quote" (Begrenzungszeichen einschließen) diese Zeichenfolgen mit einer DBMS-spezifische Literalpräfix suffix Zeichen (oder Zeichen).

Besondere syntaktische Anforderungen für Vorgänge wie das äußere Joins können auch je nach das DBMS auftreten. Verwenden Sie ODBC-Funktionen, um diese Informationen aus der Treiber für das DBMS zu erhalten. Rufen Sie z. B. `::SQLGetTypeInfo` für einen bestimmten Datentyp, z. B. `SQL_VARCHAR`, um die Zeichen LITERAL_PREFIX-Zeichen und LITERAL_SUFFIX anfordern. Wenn Sie Datenbank-unabhängige Code schreiben, finden Sie unter [Anhang C: SQL-Grammatik](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) in die [ODBC Programmer's Reference](/sql/odbc/reference/odbc-programmer-s-reference) für ausführliche Informationen zur Syntax.

Ein Recordset-Objekt erstellt, die SQL-Anweisung, die zum Auswählen von Datensätzen, es sei denn, Sie, benutzerdefinierte SQL-Anweisung übergeben verwendet wird. Vorgehensweise hängt hauptsächlich von den Wert, der Sie übergeben die *LpszSQL* Parameter, der die `Open` Member-Funktion.

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

Die folgende Tabelle zeigt die Möglichkeiten für die *LpszSQL* Parameter `Open`. Die Fälle in der Tabelle werden nach der Tabelle erläutert.

**Der LpszSQL-Parameter und die resultierende SQL-Zeichenfolge**

|Case|Was Sie in LpszSQL übergeben.|Die resultierenden SELECT-Anweisung|
|----------|------------------------------|------------------------------------|
|1|NULL|**SELECT** *rfx-field-list* **FROM** *table-name*<br /><br /> `CRecordset::Open` Aufrufe `GetDefaultSQL` um den Namen der Tabelle zu erhalten. Die resultierende Zeichenfolge ist ein Fall 2 bis 5, je nachdem, was `GetDefaultSQL` zurückgibt.|
|2|Ein Tabellenname|**SELECT** *rfx-field-list* **FROM** *table-name*<br /><br /> Die Feldliste stammt aus der RFX-Anweisungen in `DoFieldExchange`. Wenn `m_strFilter` und `m_strSort` nicht leer sind, fügt die **, in denen** und/oder **ORDER BY** Klauseln.|
|3 \*|Eine vollständige **wählen** Anweisung jedoch ohne eine **, in denen** oder **ORDER BY** Klausel|Wie übergeben. Wenn `m_strFilter` und `m_strSort` nicht leer sind, fügt die **, in denen** und/oder **ORDER BY** Klauseln.|
|4 \*|Eine vollständige **wählen** -Anweisung mit einem **, in denen** und/oder **ORDER BY** Klausel|Wie übergeben. `m_strFilter` und/oder `m_strSort` müssen bleibt leer, oder zwei Filter und/oder Sortierung-Anweisungen erstellt werden.|
|5 \*|Ein Aufruf einer gespeicherten Prozedur|Wie übergeben.|

\* `m_nFields` muss kleiner oder gleich der Anzahl der Spalten, angegeben der **wählen** Anweisung. Der Datentyp jeder Spalte im angegebenen die **wählen** -Anweisung muss den Datentyp der entsprechenden RFX Ausgabespalte identisch sein.

### <a name="case-1---lpszsql--null"></a>Fall 1 LpszSQL = NULL

Die Auswahl des Recordsets so hängt `GetDefaultSQL` gibt zurück, wenn `CRecordset::Open` von ihr aufgerufenen. Fällen 2 bis 5 werden die möglichen Zeichenfolgen beschrieben.

### <a name="case-2---lpszsql--a-table-name"></a>Fall 2 LpszSQL = Namen einer Tabelle

Das Recordset-Datensatzfeldaustausch (RFX) verwendet, um der Liste der Spalten aus den Spaltennamen zu erstellen, Funktionsaufrufen in die RFX in den Recordset die Überschreibung der `DoFieldExchange`. Wenn Sie einen Assistenten verwendet, um Recordset-Klasse zu deklarieren, muss diese Situation das gleiche Ergebnis wie Fall 1 (vorausgesetzt, dass Sie den gleichen Tabellennamen, die, den Sie im Assistenten angegebenen, übergeben). Wenn Sie einen Assistenten zum Erstellen Ihrer Klasse nicht verwenden, ist 2. Fall die einfachste Möglichkeit zum Erstellen der SQL-Anweisung.

Das folgende Beispiel erstellt eine SQL­Anweisung, die Datensätze aus einer MFC-datenbankanwendung auswählt. Wenn das Framework Ruft die `GetDefaultSQL` Member-Funktion, die Funktion gibt den Namen der Tabelle `SECTION`.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

Die Namen der Spalten für die SQL abgerufen **wählen** -Anweisung, die das Framework Ruft die `DoFieldExchange` Member-Funktion.

```cpp
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

Nach Abschluss des Vorgangs sieht die SQL-Anweisung wie folgt aus:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Fall 3 LpszSQL = SELECT / FROM-Anweisung

Sie geben Sie die Liste der Spalten manuell statt auf RFX ihn automatisch zu erstellen. Möglicherweise möchten diese Methode zurückgreifen:

- Sie angeben möchten, die **DISTINCT** Schlüsselwort im Anschluss **wählen**.

   Die Spaltenliste sollten die Spaltennamen und Datentypen in der gleichen Reihenfolge entsprechen, in der sie aufgeführt sind `DoFieldExchange`.

- Sie haben Grund manuell abrufen von Spaltenwerten mithilfe der ODBC-Funktion `::SQLGetData` statt auf RFX zu binden und Abrufen der Spalten.

   Sie könnten z. B. neue Spalten zu unterstützen, die den Datenbanktabellen ein Kunde der Anwendung hinzugefügt werden, nachdem die Anwendung verteilt wurde. Sie müssen diese zusätzlichen Felddatenmember, hinzufügen, die zur Zeit nicht bekannt waren Sie die Klasse mit einem Assistenten deklariert.

   Die Spaltenliste sollten die Spaltennamen und Datentypen in der gleichen Reihenfolge entsprechen, in der sie aufgeführt sind `DoFieldExchange`, gefolgt von den Namen der manuell gebundenen Spalten. Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Sie möchten zum Verknüpfen von Tabellen, durch Angeben von mehreren Tabellen in der **FROM** Klausel.

   Weitere Informationen und ein Beispiel finden Sie unter [Recordset: Ausführen einer Verknüpfung (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Fall 4 LpszSQL = SELECT / FROM sowie WHERE und/oder ORDER BY

Angabe, dass alles: der Liste der Spalten (basierend auf den RFX-Aufrufen in `DoFieldExchange`), die Tabellenliste, und der Inhalt des eine **, in denen** und/oder eine **ORDER BY** Klausel. Bei Angabe von Ihrem **, in denen** und/oder **ORDER BY** Klauseln auf diese Weise verwenden Sie keine `m_strFilter` und/oder `m_strSort`.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Fall 5 LpszSQL = Aufruf einer gespeicherten Prozedur

Wenn Sie eine vordefinierte Abfrage (z. B. eine gespeicherte Prozedur in einer Microsoft SQL Server-Datenbank) aufrufen möchten, müssen Sie schreiben eine **Aufrufen** -Anweisung in die Zeichenfolge, die Sie, um übergeben *LpszSQL*. Die Assistenten unterstützen keine Recordset-Klasse für den Aufruf einer vordefinierten Abfrage deklarieren. Nicht alle vordefinierten Abfragen Gibt Datensätze zurück.

Wenn eine vordefinierte Abfrage keine Datensätze zurückgibt, können Sie mithilfe der `CDatabase` Memberfunktion `ExecuteSQL` direkt. Für eine vordefinierte Abfrage, die Datensätze zurückgibt, müssen Sie auch manuell schreiben die RFX-Aufrufe `DoFieldExchange` für alle Spalten, die die Prozedur zurückgibt. Der RFX-Funktionen aufrufen müssen werden in der gleichen Reihenfolge und dieselben Typen wie die vordefinierte Abfrage zurückzugeben. Weitere Informationen finden Sie unter [Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

## <a name="see-also"></a>Siehe auch

[SQL: SQL- und C++-Datentypen (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
