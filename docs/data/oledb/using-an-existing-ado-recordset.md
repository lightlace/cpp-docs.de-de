---
title: Verwenden eines vorhandenen ADO-Recordsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d3a0b2d2da67e4db55dbf3a3f5b23c0c88797dd7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065340"
---
# <a name="using-an-existing-ado-recordset"></a>Verwenden eines vorhandenen ADO-Recordsets

Verwenden Sie zum Kombinieren von OLE DB-Consumervorlagen und Active Data Objects (ADO), ADO, um einem Recordset (entsprechend in ein Rowset in den OLE DB-Consumervorlagen) zu öffnen. Wenn Sie ein Recordset haben, gehen Sie zur Verbindung mit einem OLE DB-Rowset:  
  
1. Rufen Sie `QueryInterface` für die `IRowset` und `IAccessor` Zeiger.  
  
    ```cpp  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *LpUnk* verweist auf die `IUnknown` Objekt von der ADO-Recordset.  
  
1. Fügen Sie den Accessor und das Rowset an ihre entsprechenden OLE DB-Consumer-Vorlagenklassen an.  
  
    ```cpp  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## <a name="see-also"></a>Siehe auch  

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)