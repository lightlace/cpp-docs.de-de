---
title: BLOB_ENTRY_LENGTH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_LENGTH
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_LENGTH macro
ms.assetid: 832d21ab-5fdd-49ad-af6e-4fca5722ec93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0de1707ab616aca49061590bfb76bf74360019ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrylength"></a>BLOB_ENTRY_LENGTH
Mit verwendet `BEGIN_COLUMN_MAP` und `END_COLUMN_MAP` binden ein binary large Object ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Ähnlich wie [BLOB_ENTRY](../../data/oledb/blob-entry.md), außer dass Sie dieses Makro auch die Länge in Bytes der BLOB-Spalte erhält.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BLOB_ENTRY_LENGTH(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
length  
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
  
 *length*  
 [out] Die (tatsächlich) Länge in Bytes der BLOB-Spalte.  
  
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
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)