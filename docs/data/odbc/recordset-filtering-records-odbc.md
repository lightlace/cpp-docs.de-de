---
title: 'Recordset: Filtern von Datensätzen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 050524df840be28d661da89d04b685a44238f88c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397860"
---
# <a name="recordset-filtering-records-odbc"></a>Recordset: Filtern von Datensätzen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird erläutert, wie Sie ein Recordset filtern, damit nur eine bestimmte Teilmenge der verfügbaren Datensätze ausgewählt wird. Beispielsweise empfiehlt es sich um nur die Klasse Abschnitte für einen bestimmten Kurs, wie z. B. MATH101 auszuwählen. Ein Filter ist eine Suchbedingung, definiert durch den Inhalt einer SQL **, in denen** Klausel. Wenn das Framework für SQL-Anweisung des Recordsets, fügt die **, in denen** -Klausel schränkt die Auswahl.

Sie müssen einem Recordset-Objekt-Filter einrichten, nach dem Erstellen des Objekts, aber vor dem Aufruf der `Open` Member-Funktion (oder vor dem Aufruf der `Requery` Memberfunktion für ein bereits vorhandenes Recordset-Objekt, dessen `Open` Memberfunktion zuvor aufgerufen wurde).

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Ein Filter für ein Recordset-Objekt an

1. Erstellen Sie ein neues Recordsetobjekt (oder aufrufen vorbereiten `Requery` für ein vorhandenes Objekt).

1. Legen Sie den Wert des Objekts des [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) -Datenmember.

   Der Filter ist eine Null-terminierte Zeichenfolge mit dem Inhalt des SQL- **, in denen** -Klausel jedoch nicht das Schlüsselwort **, in denen**. Beispielsweise verwenden:

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  Das Zeichenfolgenliteral "MATH101" wird durch einfache Anführungszeichen oben angezeigt. In der ODBC-SQL-Spezifikation sind einfache Anführungszeichen verwendet, um ein Zeichenfolgenliteral zu kennzeichnen. Überprüfen der ODBC-Treiber-Dokumentation für die Anforderungen für das DBMS in dieser Situation. Diese Syntax wird ebenfalls erläutert weiter hinten in diesem Thema.

1. Legen Sie ggf. Weitere Optionen, die Sie benötigen, die können Sie z. B. die Sortierreihenfolge, Sperrmodus oder Parameter. Es ist besonders nützlich, einen Parameter angeben. Weitere Informationen zur Parametrisierung eines Filters finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. Rufen Sie `Open` für das neue Objekt (oder `Requery` für ein zuvor geöffneten Objekt).

> [!TIP]
>  Verwenden von Parametern in der Filter ist möglicherweise die effizienteste Methode zum Abrufen von Datensätzen.

> [!TIP]
>  Recordset-Filter eignen sich für [verknüpfen](../../data/odbc/recordset-performing-a-join-odbc.md) Tabellen und für die Verwendung von [Parameter](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) basierend auf Informationen, die abgerufen oder zur Laufzeit berechnet.

Das Recordset wählt nur die Datensätze, die die Suchbedingung erfüllen, die Sie angegeben haben. Beispielsweise oben an den Kurs-Filter (sofern eine Variable `strCourseID` derzeit festgelegt, z. B. "MATH101"), gehen Sie folgendermaßen vor:

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

Das Recordset enthält Einträge für alle Abschnitte der Klasse für MATH101.

Beachten Sie, wie die Filterzeichenfolge im Beispiel oben, verwenden eine String-Variable festgelegt wurde. Dies ist die typische Nutzung. Aber nehmen wir an, dass Sie den literalen Wert 100 für die Kurs-ID angeben. Der folgende Code zeigt, wie Sie die Filterzeichenfolge ordnungsgemäß mit einem Literalwert festlegen:

```
m_strFilter = "StudentID = '100'";   // correct
```

Beachten Sie die Verwendung der einfachen Anführungszeichen ein. Wenn Sie die Filterzeichenfolge direkt festlegen, wird die Filterzeichenfolge **nicht**:

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

Der ODBC-Spezifikation entspricht der Verwendung der Anführungszeichen, aber einige DBMS-Systeme möglicherweise andere Anführungszeichen erforderlich. Weitere Informationen finden Sie unter [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

> [!NOTE]
>  Möchten Sie das Recordset Standard-SQL-Zeichenfolge zu überschreiben, indem Sie eine eigene SQL-Zeichenfolge zu übergeben `Open`, einen Filter sollte nicht festgelegt werden, wenn die benutzerdefinierte Zeichenfolge enthält eine **, in denen** Klausel. Weitere Informationen zum Überschreiben der Standard-SQL finden Sie unter [SQL: Anpassen der SQL-Anweisung eines Recordsets (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)