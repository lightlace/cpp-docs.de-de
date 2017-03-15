---
title: "Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Recordsets, Abrufen von SQL-Aggregatwerten"
  - "Recordsets, Abrufen von SQL-Aggregatwerten"
  - "Abrufen von SQL-Aggregatwerten aus Recordsets"
  - "SQL-Aggregatwerte"
  - "SQL-Aggregatwerte, Abrufen von Recordsets"
  - "SQL Server-Projekte, Abrufen von Aggregatwerten aus Recordsets"
  - "SQL, Abrufen von Aggregatwerten aus Recordsets"
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset: Abrufen von Summen und anderen Aggregatergebnissen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie mit folgenden [SQL](../../data/odbc/sql.md)\-Schlüsselwörtern Aggregatergebnisse abrufen:  
  
-   **SUM** Berechnet die Summe der Werte in einer Spalte mit einem numerischen Datentyp.  
  
-   **MIN** Gibt den kleinsten Wert aus einer Spalte mit einem numerischen Datentyp zurück.  
  
-   **MAX** Gibt den größten Wert aus einer Spalte mit einem numerischen Datentyp zurück.  
  
-   **AVG** Berechnet den Durchschnitt aller Werte aus einer Spalte mit einem numerischen Datentyp.  
  
-   **COUNT** Zählt die Datensätze in einer Spalte mit einem beliebigen Datentyp.  
  
 Sie können mit diesen SQL\-Funktionen statistische Informationen über die Datensätze in einer Datenquelle abrufen, ohne die Datensätze aus der Datenquelle abrufen zu müssen.  Das für diesen Zweck erstellte Recordset besteht normalerweise aus einem einzigen Datensatz \(falls alle Spalten Aggregate sind\) mit einem Wert. \(Falls Sie eine **GROUP BY**\-Klausel verwenden, kann es auch mehrere Datensätze geben.\) Dieser Wert ist das Ergebnis der Berechnung oder Suche, die von der SQL\-Funktion durchgeführt wurde.  
  
> [!TIP]
>  Um eine SQL\-**GROUP BY**\-Klausel \(und unter Umständen eine **HAVING**\-Klausel\) in die SQL\-Anweisung einzufügen, hängen Sie diese an das Ende von **m\_strFilter** an.  Beispiel:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 Sie können die Anzahl der Datensätze begrenzen, mit denen Sie Aggregatergebnisse ermitteln, indem Sie die Spalten filtern und sortieren.  
  
> [!CAUTION]
>  Einige Aggregatoperatoren geben einen anderen Datentyp zurück als den der Spalten, über die sie ausgeführt werden.  
  
-   **SUM** und **AVG** geben unter Umständen den nächstgrößeren Datentyp zurück \(z. B. erfolgt beim Aufruf von `int` eine Rückgabe von **LONG** oder **double**\).  
  
-   **COUNT** gibt unabhängig vom Typ der Zielspalte in den meisten Fällen **LONG** zurück.  
  
-   **MAX** und **MIN** geben den Datentyp der Spalten zurück, die sie berechnen.  
  
     Der Assistent zum **Hinzufügen von Klassen** könnte z. B. für eine Umsatzspalte den Datenmember `long` `m_lSales` erstellen. Sie müssen diesen Datenmember jedoch durch `double m_dblSumSales` ersetzen, um das Aggregatergebnis zu unterstützen.  \(Siehe nachstehendes Beispiel.\)  
  
#### So ermitteln Sie ein Aggregatergebnis für ein Recordset  
  
1.  Erstellen Sie ein Recordset \(wie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) beschrieben\) mit den Spalten, für die Sie Aggregatergebnisse abrufen möchten.  
  
2.  Ändern Sie die [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Funktion des Recordsets.  Ersetzen Sie die Zeichenfolge mit dem Spaltennamen \(das zweite Argument der [RFX](../../data/odbc/record-field-exchange-using-rfx.md)\-Funktionsaufrufe\) durch eine Zeichenfolge, die die Aggregatfunktion für die Spalte enthält.  Ersetzen Sie z. B.  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     durch  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  Öffnen Sie das Recordset.  Das Ergebnis der Aggregatoperation wird in `m_dblSumSales` abgelegt.  
  
> [!NOTE]
>  Der Assistent verwendet Datenmembernamen ohne ungarische Präfixe.  Der Assistent legt z. B. für eine Spalte mit dem Namen Sales das Datenelement `m_Sales` an, und nicht das in diesem Beispiel verwendete `m_lSales`.  
  
 Wenn die Daten mithilfe einer [CRecordView](../../mfc/reference/crecordview-class.md)\-Klasse angezeigt werden, müssen Sie den DDX\-Funktionsaufruf ändern, um den neuen Datenmemberwert darzustellen. Ändern Sie den Aufruf in diesem Fall von  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 To:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)