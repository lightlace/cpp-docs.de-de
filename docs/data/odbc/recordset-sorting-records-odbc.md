---
title: "Recordset: Sortieren von Datens&#228;tzen (ODBC)"
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
  - "ODBC-Recordsets, Sortieren"
  - "Recordsets, Sortieren"
  - "Sortieren von Daten, Recordsetdaten"
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Sortieren von Datens&#228;tzen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie Recordsets sortieren.  Sie können eine oder mehrere Spalten bestimmen, nach denen sortiert wird. Außerdem können Sie für jede dieser Spalten festlegen, ob aufsteigend oder absteigend sortiert werden soll \(`ASC` oder **DESC**; `ASC` ist der Standardwert\).  Wenn Sie beispielsweise zwei Spalten festlegen, werden die Datensätze zuerst nach der ersten Spalte und dann nach der zweiten Spalte sortiert.  Eine SQL\-**ORDER BY**\-Klausel definiert eine Sortierreihenfolge.  Wenn das Framework die **ORDER BY**\-Klausel an die SQL\-Abfrage des Recordsets anhängt, steuert diese Klausel die Reihenfolge der ausgewählten Datensätze.  
  
 Sie müssen die Sortierreihenfolge eines Recordsets einrichten, nachdem Sie das Objekt konstruiert haben, aber noch bevor Sie seine **Open**\-Memberfunktion aufrufen \(oder bevor Sie für ein bereits vorhandenes Recordset\-Objekt, dessen **Open**\-Memberfunktion zuvor aufgerufen wurde, die **Requery**\-Memberfunktion aufrufen\).  
  
#### So legen Sie eine Sortierreihenfolge für ein Recordset\-Objekt fest  
  
1.  Konstruieren Sie ein neues Recordset\-Objekt \(oder bereiten Sie ein bereits vorhandenes Recordset\-Objekt für den Aufruf von **Requery** vor\).  
  
2.  Tragen Sie einen passenden Wert in den [m\_strSort](../Topic/CRecordset::m_strSort.md)\-Datenmember des Objekts ein.  
  
     Die Sortierzeichenfolge endet mit einer NULL.  Diese enthält den Inhalt der **ORDER BY**\-Klausel, allerdings ohne das Schlüsselwort **ORDER BY**.  Verwenden Sie z. B.  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Stellen Sie alle sonstigen benötigten Optionen, z. B. Filter, Sperrverhalten und Parameter ein.  
  
4.  Rufen Sie **Open** für das neue Objekt auf \(oder **Requery** bei einem bereits vorhandenen Objekt\).  
  
 Die ausgewählten Datensätze werden wie angegeben sortiert.  Um z. B. einen Satz von Studentendatensätzen in absteigender Reihenfolge erst nach dem Nachnamen und dann nach dem Vornamen zu sortieren, gehen Sie folgendermaßen vor:  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Das Recordset enthält alle Studentendatensätze, erst nach dem Nachnamen und dann nach dem Vornamen absteigend sortiert \(Z bis A\).  
  
> [!NOTE]
>  Wenn Sie die Standard\-SQL\-Zeichenfolge des Recordsets überschreiben, indem Sie eine eigene SQL\-Zeichenfolge an **Open** übergeben, dürfen Sie keine Sortierreihenfolge festlegen, sofern die benutzerdefinierte Zeichenfolge eine **ORDER BY**\-Klausel enthält.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset: Filtern von Datensätzen \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)