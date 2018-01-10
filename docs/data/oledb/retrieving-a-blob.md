---
title: Abrufen eines BLOBs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36ffc4fca7859b49067517e1085e1d854f733e24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
CTable<CAccessor<CCategories> > categories;  
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