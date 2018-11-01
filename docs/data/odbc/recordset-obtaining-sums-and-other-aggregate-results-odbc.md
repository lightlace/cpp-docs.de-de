---
title: 'Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
ms.openlocfilehash: 7a63e6b0e4ac26fb2806d8505e3fcd8f5daf0f10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491584"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.

In diesem Thema wird erläutert, wie zum Abrufen der Ergebnisse mit den folgenden [SQL](../../data/odbc/sql.md) Schlüsselwörter:

- **Summe** berechnet die Summe der Werte in einer Spalte mit einem numerischen Datentyp.

- **Min.** extrahiert den kleinsten Wert in einer Spalte mit einem numerischen Datentyp.

- **Max.** extrahiert den größten Wert in einer Spalte mit einem numerischen Datentyp.

- **Durchschn.** berechnet den Durchschnitt aller Werte in einer Spalte mit einem numerischen Datentyp.

- **Anzahl** zählt die Anzahl der Datensätze in einer Spalte eines beliebigen Datentyps.

Sie können diese SQL-Funktionen verwenden, um statistische Informationen zu den Datensätzen in einer Datenquelle abzurufen, statt zum Extrahieren von Datensätzen aus der Datenquelle. Das Recordset, das in der Regel erstellt wird, besteht aus einem einzelnen Datensatz (wenn alle Spalten Aggregate sind), die einen Wert enthält. (Es kann mehr als einem Datensatz sein, wenn Sie verwendet eine **GROUP BY** Klausel.) Dieser Wert ist das Ergebnis der Berechnung oder extrahieren, die von der SQL-Funktion ausgeführt wird.

> [!TIP]
>  Hinzufügen eine SQL **GROUP BY** Klausel (und möglicherweise eine **HAVING** Klausel) der SQL-Anweisung, fügen sie am Ende der `m_strFilter`. Zum Beispiel:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

Sie können die Anzahl der Datensätze einschränken, die Sie verwenden, um aggregierte Ergebnisse zu erhalten, durch Filtern und Sortieren nach Spalten.

> [!CAUTION]
>  Einige aggregationsoperatoren zurückgeben ein anderen Datentyps aus den Spalten, die über die sie ausgeführt werden.

- **Summe** und **AVG** möglicherweise den größeren Datentyp zurück (z. B. Aufrufen mit `int` gibt **lange** oder **doppelte**).

- **Anzahl** gibt i. d. r. **lange** unabhängig vom Typ der Zielspalte.

- **Max.** und **MIN** denselben Datentyp wie die Spalten, die berechnet, zurückgegeben.

     Z. B. die **Klasse hinzufügen** -Assistent erstellt `long` `m_lSales` eine Salesspalte, aber Sie berücksichtigen muss, ersetzen Sie dies mit einem `double m_dblSumSales` Datenmembers, der das aggregierte Ergebnis zu berücksichtigen. Weitere Informationen finden Sie im folgenden Beispiel.

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Um eine aggregierte Ergebnis für ein Recordset zu erhalten.

1. Erstellen Sie ein Recordset, wie im [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) mit den Spalten, die aus dem Aggregieren der Ergebnisse abgerufen werden sollen.

1. Ändern der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) -Funktion für das Recordset. Ersetzen Sie die Zeichenfolge, die den Namen der Spalte darstellt (das zweite Argument der der [RFX](../../data/odbc/record-field-exchange-using-rfx.md) Funktionsaufrufe) mit einer Zeichenfolge, die die Aggregatfunktion für die Spalte darstellt. Ersetzen Sie z. B.:

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     Durch:

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. Öffnen des Recordsets. Das Ergebnis des Aggregationsvorgangs verbleibt im `m_dblSumSales`.

> [!NOTE]
>  Der Assistent weist tatsächlich Datenmembernamen ohne Ungarisch Präfixe. Der Assistent wäre z. B. `m_Sales` für eine Spalte "Sales" anstelle der `m_lSales` Namen, die zuvor zur Veranschaulichung verwendet.

Bei Verwendung einer [CRecordView](../../mfc/reference/crecordview-class.md) Klasse, um die Daten anzuzeigen, müssen Sie so ändern den DDX-Funktionsaufruf zum Anzeigen des neuen Werts des Daten-Element; in diesem Fall Änderung von:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

Nach:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>Siehe auch

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Wie Recordsets Datensätze auswählen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)