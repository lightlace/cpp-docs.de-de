---
title: Abrufen von Daten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ae486150a23af4c1aa04177650d675087ce4e16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="fetching-data"></a>Abrufen von Daten
Nachdem Sie die Datenquelle, die Sitzung und die Rowset-Objekte geöffnet haben, können Sie Daten abrufen. Je nach Art der Zugriffsmethode, die Sie verwenden, müssen Sie die Spalten zu binden.  
  
### <a name="to-fetch-data"></a>Zum Abrufen von Daten  
  
1.  Öffnen Sie das Rowset mit dem entsprechenden **öffnen** Befehl.  
  
2.  Bei Verwendung von `CManualAccessor`, binden Sie die Ausgabespalten aus, wenn Sie nicht bereits geschehen. Rufen Sie zum Binden der Spalten `GetColumnInfo`, und erstellen Sie einen Accessor mit den Bindungen, wie im folgenden Beispiel gezeigt:  
  
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
  
3.  Schreiben einer `while` Schleife zum Abrufen der Daten. Rufen Sie in der Schleife `MoveNext` , setzen den Cursor und den Rückgabewert mit S_OK, testen, wie im folgenden Beispiel gezeigt:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  Innerhalb der `while` Schleife, können Sie die Daten gemäß Ihrer Accessortyp abzurufen.  
  
    -   Bei Verwendung der [CAccessor](../../data/oledb/caccessor-class.md) -Klasse, Sie müssen einen Benutzerdatensatz, der Datenmember enthält. Sie können Ihre Daten mit diesen Datenmember zugreifen, wie im folgenden Beispiel gezeigt:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   Bei Verwendung der `CDynamicAccessor` oder `CDynamicParameterAccessor` -Klasse, können Sie die Daten abzurufen, mit den Zugriff auf Funktionen `GetValue` und `GetColumn`, wie im folgenden Beispiel gezeigt. Wenn Sie den Typ der Daten bestimmen möchten, verwenden, verwenden Sie `GetType`.  
  
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
  
    -   Bei Verwendung von `CManualAccessor`, müssen Sie eigene Datenmember angeben, sie selbst binden und sie greifen direkt auf, wie im folgenden Beispiel gezeigt:  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Consumervorlagen](../../data/oledb/working-with-ole-db-consumer-templates.md)