---
title: Verwenden eines vorhandenen ADO-Recordsets | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a819a0f292951060f4dc6b9fdda580db8f0d2127
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="using-an-existing-ado-recordset"></a>Verwenden eines vorhandenen ADO-Recordsets
Verwenden von ADO zum Mischen von OLE DB-Consumervorlagen und Active Data Objects (ADO) um zu einem Recordset (Dies entspricht in ein Rowset in der OLE DB-Consumervorlagen) zu öffnen. Wenn Sie ein Recordset haben, gehen Sie für die Verbindung zu einem OLE DB-Rowset:  
  
1.  Rufen Sie `QueryInterface` für die `IRowset` und `IAccessor` Zeiger.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *LpUnk* verweist auf die **IUnknown** Objekt von der ADO-Recordset.  
  
2.  Fügen Sie der Accessor und das Rowset an ihre entsprechenden OLE DB-Consumer-Vorlagenklassen an.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)