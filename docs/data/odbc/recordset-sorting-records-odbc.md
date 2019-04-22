---
title: 'Recordset: Sortieren von Datensätzen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 831f21901186ed0ae010b0f332327eefcba94b51
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024659"
---
# <a name="recordset-sorting-records-odbc"></a>Recordset: Sortieren von Datensätzen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird erläutert, wie das Recordset sortiert wird. Sie können angeben, dass eine oder mehrere Spalten auf dem die Sortierung basieren, und Sie können angeben, auf- oder absteigender Reihenfolge (**ASC** oder **DESC**; **ASC** ist die Standardeinstellung) für jede Spalte angegeben. Z. B. Wenn Sie zwei Spalten angeben, werden die Datensätze zuerst in der ersten Spalte, die mit dem Namen, und klicken Sie dann auf der zweiten Spalte, die mit dem Namen sortiert. Eine SQL **ORDER BY** -Klausel definiert eine Sortierung. Wenn das Framework fügt der **ORDER BY** -Klausel, um dem Recordset SQL-Abfragen, die Klausel-Steuerelemente, die die Auswahl der Sortierung.

Sie müssen ein Recordset Sortierreihenfolge einrichten, nach dem Erstellen des Objekts, aber vor dem Aufruf der `Open` Member-Funktion (oder vor dem Aufruf der `Requery` Memberfunktion für ein bereits vorhandenes Recordset-Objekt, dessen `Open` Memberfunktion wurde zuvor aufgerufen).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Eine Sortierreihenfolge für ein Recordset-Objekt an

1. Erstellen Sie ein neues Recordsetobjekt (oder aufrufen vorbereiten `Requery` für ein bereits vorhandenes).

1. Legen Sie den Wert des Objekts des [M_strSort](../../mfc/reference/crecordset-class.md#m_strsort) -Datenmember.

   Die Sortierung ist eine Null-terminierte Zeichenfolge. Es enthält den Inhalt der **ORDER BY** -Klausel jedoch nicht das Schlüsselwort **ORDER BY**. Beispielsweise verwenden:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Legen Sie ggf. Weitere Optionen, die Sie benötigen, die können Sie z. B. einen Filter, Sperrmodus oder Parameter.

1. Rufen Sie `Open` für das neue Objekt (oder `Requery` für ein vorhandenes Objekt).

Die ausgewählten Datensätze werden sortiert nach den Angaben. Um eine Gruppe von Datensätzen für Schüler und Studenten, in absteigender Reihenfolge nach Nachnamen und dann die Vornamen sortieren möchten, führen Sie z. B. folgende ein:

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

Das Recordset enthält alle Studentendatensätze, sortiert in absteigender Reihenfolge (Z bis A) nach dem Nachnamen, klicken Sie dann nach Vornamen.

> [!NOTE]
>  Wenn Sie auswählen, um dem Recordset Standard-SQL-Zeichenfolge zu überschreiben, indem Sie eine eigene SQL-Zeichenfolge zu übergeben `Open`, eine Sortierung ist nicht festgelegt werden, wenn die benutzerdefinierte Zeichenfolge enthält eine **ORDER BY** Klausel.

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)