---
title: "Verwenden von Lesezeichen"
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
  - "Lesezeichen, OLE DB"
  - "OLE DB-Anbietervorlagen, Lesezeichen"
  - "OLE DB-Anbieter, Lesezeichenunterstützung"
  - "Rowsets, Lesezeichen"
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Lesezeichen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bevor Sie das Rowset öffnen, müssen Sie dem Anbieter mitteilen, dass Sie Lesezeichen verwenden möchten.  Legen Sie hierzu die Eigenschaft **DBPROP\_BOOKMARKS** im Eigenschaftenset auf **true** fest.  Der Anbieter ruft Lesezeichen als Spalte 0 ab, daher müssen Sie das Spezialmakro `BOOKMARK_ENTRY` und die `CBookmark`\-Klasse verwenden, wenn Sie einen statischen Accessor verwenden.  Bei `CBookmark` handelt es sich um eine Vorlagenklasse, in der das Argument die Länge des Lesezeichenpuffers in Bytes ist.  Die für ein Lesezeichen benötigte Pufferlänge ist vom Anbieter abhängig.  Wenn Sie, wie im folgenden Beispiel dargestellt, den ODBC\-OLE DB\-Anbieter verwenden, muss der Puffer 4 Bytes umfassen.  
  
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
  
CTable<CAccessor<CProducts> > product;  
product.Open(session, "Products", &propset);  
```  
  
 Wenn Sie `CDynamicAccessor` verwenden, wird der Puffer zur Laufzeit dynamisch zugewiesen.  In diesem Fall können Sie eine spezialisierte Version von `CBookmark` verwenden, für die keine Pufferlänge festgelegt werden muss.  Verwenden Sie die Funktion `GetBookmark`, um das Lesezeichen aus dem aktuellen Datensatz abzurufen, wie in diesem Codebeispiel gezeigt:  
  
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
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)