---
title: 'Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4aa6de58e7e2c530a7a353281ba5af747f48cd4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie zum Abrufen von Aggregatergebnissen mithilfe des folgenden [SQL](../../data/odbc/sql.md) Schlüsselwörter:  
  
-   **Summe** berechnet die Summe der Werte in einer Spalte mit einem numerischen Datentyp.  
  
-   **MIN** extrahiert den kleinsten Wert in einer Spalte mit einem numerischen Datentyp.  
  
-   **Max.** extrahiert den größten Wert in einer Spalte mit einem numerischen Datentyp.  
  
-   **AVG** berechnet den Durchschnitt aller Werte in einer Spalte mit einem numerischen Datentyp.  
  
-   **Anzahl** zählt die Anzahl der Datensätze in einer Spalte eines beliebigen Datentyps.  
  
 Statistische Informationen zu den Datensätzen in einer Datenquelle abrufen, anstatt Datensätze aus der Datenquelle zu extrahieren, verwenden Sie diese SQL-Funktionen. Das Recordset, das in der Regel erstellt wird, besteht aus einem einzelnen Datensatz (wenn alle Spalten Aggregate sind), die einen Wert enthält. (Es kann mehr als ein Datensatz sein, wenn Sie verwendet ein **GROUP BY** Klausel.) Dieser Wert ist das Ergebnis der Berechnung oder extrahieren, die von der SQL-Funktion ausgeführt wird.  
  
> [!TIP]
>  Hinzufügen eine SQL **GROUP BY** -Klausel (und möglicherweise eine **HAVING** Klausel) in die SQL-Anweisung fügt diese am Ende der **M_strFilter**. Zum Beispiel:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 Sie können die Anzahl der Datensätze einschränken, die Sie verwenden, so aggregieren Sie Ergebnisse filtern und sortieren die Spalten erhalten.  
  
> [!CAUTION]
>  Einige Aggregation Operator gibt einen anderen Datentyp zurück, aus den Spalten, die über denen sie die Aggregation durchgeführt werden.  
  
-   **Summe** und **AVG** möglicherweise den größeren Datentyp zurück (z. B. Aufrufen mit `int` gibt **lange** oder **doppelte**).  
  
-   **Anzahl** in der Regel gibt **lange** unabhängig vom Typ der Zielspalte.  
  
-   **Max.** und **MIN** den gleichen Datentyp wie die Spalten, die sie berechnen zurückgeben.  
  
     Z. B. die **Klasse hinzufügen** -Assistent erstellt `long` `m_lSales` ersetzen Sie dabei auf eine Salesspalte, aber Sie müssen eine `double m_dblSumSales` Datenmember, um das aggregierte Ergebnis zu berücksichtigen. Weitere Informationen finden Sie im folgenden Beispiel.  
  
#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>Um eine aggregierte Ergebnis für ein Recordset zu erhalten  
  
1.  Erstellen Sie ein Recordset, wie beschrieben in [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) mit den Spalten, die von dem Sie aggregierte Ergebnisse abrufen möchten.  
  
2.  Ändern der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Funktion für das Recordset. Ersetzen Sie die Zeichenfolge, die den Namen der Spalte darstellt (das zweite Argument für die [RFX](../../data/odbc/record-field-exchange-using-rfx.md) Funktionsaufrufe) mit einer Zeichenfolge, die die Aggregatfunktion für die Spalte darstellt. Ersetzen Sie beispielsweise:  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     Mit:  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  Öffnen des Recordsets. Das Ergebnis des Aggregationsvorgangs verbleibt im `m_dblSumSales`.  
  
> [!NOTE]
>  Der Assistent weist tatsächlich den Datenmembernamen ohne Ungarisch Präfixe. Der Assistent wäre z. B. `m_Sales` für eine Salesspalte statt über das `m_lSales` Namen, die zuvor zur Veranschaulichung verwendet.  
  
 Bei Verwendung einer [CRecordView](../../mfc/reference/crecordview-class.md) Klasse, um die Daten anzuzeigen, müssen Sie den DDX-Funktionsaufruf. zum Anzeigen der neuen Daten Elementwert; ändern in diesem Fall ändern Sie es aus:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 Nach:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Wie Recordsets Datensätze auswählen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)