---
title: Mithilfe von Lesezeichen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5aa16d5f2a3a02d0e9fd6bb3dd5de71494e81d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104486"
---
# <a name="using-bookmarks"></a>Verwenden von Lesezeichen
Bevor Sie das Rowset zu öffnen, muss dem Anbieter Aufschluss darüber, dass Sie Lesezeichen verwenden möchten. Legen Sie hierzu die **DBPROP_BOOKMARKS** Eigenschaft **"true"** in Ihrer Eigenschaft festgelegt. Der Anbieter Lesezeichen als Spalte 0 (null), abruft, daher müssen Sie das spezielle Makro verwenden `BOOKMARK_ENTRY` und die `CBookmark` Klasse, wenn Sie einen statischen Accessor verwenden. `CBookmark` ist eine Vorlagenklasse, in dem das Argument die Länge in Bytes des Lesezeichenpuffers ist. Die Länge des Puffers für ein Lesezeichen benötigte hängt vom Anbieter ab. Wenn Sie den ODBC-OLE DB-Anbieter verwenden, wie im folgenden Beispiel gezeigt, muss der Puffer 4 Bytes.  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_BOOKMARKS, true);  
  

CTable<CAccessor<CProducts>> product;  
product.Open(session, "Products", &propset);  
```  
  
 Bei Verwendung von `CDynamicAccessor`, der Puffer zur Laufzeit dynamisch zugeordnet wird. In diesem Fall können Sie eine spezielle Version des `CBookmark` für die Sie eine Pufferlänge nicht angeben. Verwenden Sie die Funktion `GetBookmark` auf das Lesezeichen aus dem aktuellen Datensatz abzurufen, wie in diesem Codebeispiel gezeigt:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
 Informationen zur Unterstützung von Lesezeichen in Anbietern finden Sie unter [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)