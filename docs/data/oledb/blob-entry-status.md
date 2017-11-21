---
title: BLOB_ENTRY_STATUS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_STATUS
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_STATUS macro
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0cc0805147908703b880cb826b0363acecfa4902
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrystatus"></a>BLOB_ENTRY_STATUS
Mit verwendet `BEGIN_COLUMN_MAP` oder `BEGIN_ACCESSOR_MAP` binden ein binary large Object ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), mit dem Unterschied, dass dieses Makro auch den Status der BLOB-Spalte erhält.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BLOB_ENTRY_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
status  
 )  
  
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
  
 *status*  
 [out] Der Status des BLOB-Felds.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [wie können Sie einen BLOB abgerufen?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)