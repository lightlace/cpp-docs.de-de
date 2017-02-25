---
title: "Verwenden eines vorhandenen ADO-Recordsets | Microsoft Docs"
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
  - "ADO-Recordsets [C++]"
  - "OLE DB-Consumervorlagen, ADO-Recordsets"
  - "Recordsets [C++], Verwenden in OLE DB"
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden eines vorhandenen ADO-Recordsets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um OLE DB\-Consumervorlagen und Active Data Objects \(ADO\) zu kombinieren, verwenden Sie ADO zum Öffnen eines Recordsets \(entspricht einem Rowset in den OLE DB\-Consumervorlagen\).  Wenn Sie über ein Recordset verfügen, führen Sie die folgenden Schritte aus, um eine Verbindung zu einem OLE DB\-Rowset herzustellen:  
  
1.  Rufen Sie `QueryInterface` für den `IRowset`\-Zeiger und den `IAccessor`\-Zeiger auf.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* zeigt auf das **IUnknown**\-Objekt des ADO\-Recordsets.  
  
2.  Fügen Sie den Accessor und das Rowset den entsprechenden OLE DB\-Consumervorlagen\-Klassen hinzu.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)