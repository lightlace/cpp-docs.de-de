---
title: "&#39;&lt;nullkonstante&gt;&#39; wurde nicht deklariert"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30822"
  - "vbc30822"
helpviewer_keywords: 
  - "BC30822"
ms.assetid: dda0e2c1-46a3-4cc4-b36c-0858a5259bac
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nullkonstante&gt;&#39; wurde nicht deklariert
'\<nullkonstante\>' wurde nicht deklariert. Nullkonstanten werden nicht mehr unterstützt. Verwenden Sie stattdessen System.DBNull.  
  
 Eine Anweisung verwendet das Schlüsselwort `Null`, das in Visual Basic nicht mehr unterstützt wird.  
  
 **Fehler\-ID:** BC30822  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie <xref:System.DBNull> anstelle von `Null`. Das folgende Beispiel veranschaulicht das.  
  
    ```  
    Sub TestDBNull() Dim t As DataTable ' Assume the DataGrid is bound to a DataTable. t = CType(DataGrid1.DataSource, DataTable) Dim r As DataRow r = t.Rows(datagrid1.CurrentCell.RowNumber) r.BeginEdit r(1) = System.DBNull.Value ' Assign DBNull to the record. r.EndEdit r.AcceptChanges If r.IsNull(1) Then MsgBox("") End If End Sub  
    ```  
  
2.  Verwenden Sie da Schlüsselwort [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) für Zuweisungen und Vergleiche, wenn Sie Objektvariablen verwenden. Das folgende Beispiel veranschaulicht das.  
  
    ```  
    Sub TestNothing() Dim cls As Object ' cls is Nothing if it has not been assigned using the New keyword. If (cls Is Nothing) Then MsgBox("cls is Nothing") End If cls = Nothing ' Assign Nothing to the class variable cls. End Sub  
    ```  
  
## Siehe auch  
 <xref:System.DBNull>   
 [Nothing](../Topic/Nothing%20\(Visual%20Basic\).md)   
 [Programming Element Support Changes Summary](assetId:///0483590a-6309-449c-a2fa-effa26a03b95)