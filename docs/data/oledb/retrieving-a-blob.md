---
title: "Abrufen eines BLOBs"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB (Binary Large Object), Abrufen"
  - "OLE DB, BLOB (Binary Large Object)"
  - "Abrufen von BLOBs"
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Abrufen eines BLOBs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt verschiedene Möglichkeiten zum Abrufen eines Binary Large Object \(BLOB\).  Sie können **DBTYPE\_BYTES** verwenden, um das BLOB als Bytesequenz abzurufen, oder Sie können eine Schnittstelle wie `ISequentialStream` verwenden.  Weitere Informationen finden Sie unter [BLOBS und OLE\-Objekte](https://msdn.microsoft.com/en-us/library/ms711511.aspx) in der *OLE\-Programmierreferenz*.  
  
 Der folgende Code veranschaulicht, wie Sie ein BLOB mithilfe von `ISequentialStream` abrufen können.  Das Makro [BLOB\_ENTRY](../../data/oledb/blob-entry.md) ermöglicht es Ihnen, die Schnittstelle sowie die für die Schnittstelle verwendeten Flags festzulegen.  Nach dem Öffnen der Tabelle ruft der Code in `ISequentialStream` wiederholt **Read** auf, damit Bytes aus dem BLOB gelesen werden.  Der Code ruft **Release** auf, um den Schnittstellenzeiger zu verwerfen, bevor `MoveNext` aufgerufen wird, um den nächsten Datensatz zu beziehen.  
  
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
  
 Weitere Informationen zu Makros, mit denen BLOB\-Daten behandelt werden können, finden Sie unter "Spaltenzuordnungsmakros" in [Makros und globale Funktionen für OLE DB\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)