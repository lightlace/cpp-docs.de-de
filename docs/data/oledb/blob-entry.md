---
title: BLOB_ENTRY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY macro
ms.assetid: 89e40678-0869-49ed-b502-0fa2630a9081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3922b82c53b5ace7a518893154b4f5e5b7c489f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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