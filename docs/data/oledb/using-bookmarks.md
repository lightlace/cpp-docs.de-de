---
title: Verwenden von Lesezeichen | Microsoft-Dokumentation
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
ms.openlocfilehash: 8643b8150f08191fa041107fa4a88e3cbcf2964a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042259"
---
# <a name="using-bookmarks"></a>Verwenden von Lesezeichen

Vor dem Öffnen des Rowsets, müssen Sie dem Anbieter mitteilen, dass Sie Lesezeichen verwenden möchten. Zu diesem Zweck legen Sie die `DBPROP_BOOKMARKS` Eigenschaft **"true"** in die Eigenschaft festgelegt. Der Anbieter Lesezeichen als Spalte 0 (null), abruft, daher müssen Sie das spezielle Makro BOOKMARK_ENTRY verwenden und die `CBookmark` Klasse, wenn Sie einen statischen Accessor verwenden. `CBookmark` ist eine Vorlagenklasse, in dem das Argument die Länge in Bytes des Lesezeichenpuffers ist. Die Länge des Puffers für die ein Lesezeichen erforderlich sind, hängt von den Anbieter ab. Wenn Sie den ODBC-OLE DB-Anbieter, wie im folgenden Beispiel gezeigt verwenden, muss der Puffer 4 Byte sein.  
  
```cpp  
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
  
Bei Verwendung von `CDynamicAccessor`, der Puffer wird zur Laufzeit dynamisch zugewiesen. In diesem Fall können Sie eine spezialisierte Version der `CBookmark` für die Sie eine Pufferlänge nicht angeben. Verwenden Sie die Funktion `GetBookmark` das Lesezeichen aus dem aktuellen Datensatz, abrufen, wie in diesem Codebeispiel gezeigt:  
  
```cpp  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
Informationen zur Unterstützung von Lesezeichen in Anbieter finden Sie unter [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Siehe auch  

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)