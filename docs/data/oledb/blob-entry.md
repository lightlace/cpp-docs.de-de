---
title: BLOB_ENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY macro
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46a2a095b08640701630647ca4fe916926085c3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="blobentry"></a>BLOB_ENTRY
Mit verwendet `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP` binden ein binary large Object ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `nOrdinal`  
 [in] Die Nummer der Spalte.  
  
 *IID*  
 [in] Schnittstellen-GUID, wie z. B. **IDD_ISequentialStream**, mit denen das BLOB abrufen.  
  
 `flags`  
 [in] Vom OLE Structured Storage Modell definierte Speichermodus flags (z. B. **STGM_READ**).  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [wie können Sie einen BLOB abgerufen?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)