---
title: Verwenden eines vorhandenen ADO-Recordsets
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 62e56b818a766bf3b7efddf9243ffd47ad2cb46f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610599"
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
    > *LpUnk* verweist auf die `IUnknown` Objekt von der ADO-Recordset.

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