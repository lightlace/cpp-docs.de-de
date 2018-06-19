---
title: Abrufen eines BLOBs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 420e863fcd5d4c666bf8e9a25a2f0f53e726c871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105204"
---
# <a name="retrieving-a-blob"></a>Abrufen eines BLOBs
Sie können ein binary large Object (BLOB) auf verschiedene Weise abrufen. Sie können **DBTYPE_BYTES** das BLOB als eine Folge von Bytes abzurufen, oder verwenden eine Schnittstelle wie `ISequentialStream`. Weitere Informationen finden Sie unter [BLOBS und OLE-Objekte](https://msdn.microsoft.com/en-us/library/ms711511.aspx) in der *OLE DB Programmer's Reference*.  
  
 Der folgende Code zeigt, wie ein BLOB mit abgerufen `ISequentialStream`. Das Makro [BLOB_ENTRY](../../data/oledb/blob-entry.md) können Sie die Schnittstelle und die Flags, die die Schnittstelle zum angeben. Nach dem Öffnen der Tabelle an, der Code ruft **lesen** wiederholt `ISequentialStream` , Bytes aus dem BLOB zu lesen. Der Code ruft **Release** zum Verwerfen des Schnittstellenzeigers vor dem Aufruf `MoveNext` zum Abrufen des nächsten Datensatzes.  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories>> categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  

while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
 Weitere Informationen zu Makros, die BLOB-Daten behandelt, finden Sie unter "Spaltenzuordnungsmakros" in [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [Makros und globale Funktionen für OLE-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)