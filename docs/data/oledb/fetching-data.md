---
title: "Abrufen von Daten | Microsoft Docs"
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
  - "Daten [C++], Abrufen"
  - "Abrufen"
  - "OLE DB-Consumervorlagen [C++], Abrufen von Daten"
  - "Rowsets [C++], Abrufen"
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Abrufen von Daten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie die Datenquelle, die Sitzung und die Rowset\-Objekte geöffnet haben, können Sie Daten abrufen.  Dabei hängt es vom verwendeten Accessortyp ab, ob Sie Spalten binden müssen.  
  
### So rufen Sie Daten ab  
  
1.  Öffnen Sie das Rowset mit dem entsprechenden Befehl zum **Öffnen**.  
  
2.  Wenn Sie `CManualAccessor` verwenden, binden Sie die Ausgabespalten, sofern Sie dies noch nicht getan haben.  Rufen Sie zum Binden der Spalten `GetColumnInfo` auf, und erstellen Sie anschließend einen Accessor mit den Bindungen, wie im folgenden Beispiel dargestellt:  
  
    ```  
    // From the DBViewer Sample CDBTreeView::OnQueryEdit  
    // Get the column information  
    ULONG ulColumns       = 0;  
    DBCOLUMNINFO* pColumnInfo  = NULL;  
    LPOLESTR pStrings      = NULL;  
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)  
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);  
    struct MYBIND* pBind = new MYBIND[ulColumns];  
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);  
    for (ULONG l=0; l<ulColumns; l++)  
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);  
    rs.Bind();  
    ```  
  
3.  Schreiben Sie eine `while`\-Schleife, um die Daten abzurufen.  Rufen Sie in der Schleife `MoveNext` auf, um die Einfügemarke zu verschieben, und vergleichen Sie den Rückgabewert mit S\_OK, wie im folgenden Beispiel dargestellt:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  Innerhalb der `while`\-Schleife können Sie Daten entsprechend dem verwendeten Accessortyp abrufen.  
  
    -   Wenn Sie die [CAccessor](../../data/oledb/caccessor-class.md)\-Klasse verwenden, sollten Sie über einen Benutzerdatensatz verfügen, der Datenmember enthält.  Mithilfe dieser Datenmember können Sie wie im folgenden Beispiel auf die Daten zugreifen:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Wenn Sie die Klassen `CDynamicAccessor` oder `CDynamicParameterAccessor` verwenden, können Sie Daten mithilfe der Zugriffsfunktionen `GetValue` und `GetColumn` abrufen \(siehe folgendes Beispiel\).  Wenn Sie bestimmen möchten, welchen Datentyp Sie verwenden, verwenden Sie `GetType`.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the dynamic accessor functions to retrieve your data.  
  
            ULONG ulColumns = rs.GetColumnCount();  
            for (ULONG i=0; i<ulColumns; i++)  
            {  
                rs.GetValue(i);  
            }  
        }  
        ```  
  
    -   Wenn Sie `CManualAccessor` verwenden, müssen Sie die eigenen Datenmember angeben, sie selbst binden und direkt auf sie zugreifen, wie im folgenden Beispiel dargestellt:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)