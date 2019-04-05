---
title: Verwenden von Lesezeichen
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 579e67151858904e877a34bf30467e3cb97fe2c4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028492"
---
# <a name="using-bookmarks"></a>Verwenden von Lesezeichen

Vor dem Öffnen des Rowsets, müssen Sie dem Anbieter mitteilen, dass Sie Lesezeichen verwenden möchten. Zu diesem Zweck legen Sie die `DBPROP_BOOKMARKS` Eigenschaft **"true"** in die Eigenschaft festgelegt. Der Anbieter Lesezeichen als Spalte 0 (null), abruft, daher müssen Sie das spezielle Makro BOOKMARK_ENTRY verwenden und die `CBookmark` Klasse, wenn Sie einen statischen Accessor verwenden. `CBookmark` ist eine Vorlagenklasse, in dem das Argument die Länge in Bytes des Lesezeichenpuffers ist. Die Länge des Puffers für die ein Lesezeichen erforderlich sind, hängt von den Anbieter ab. Wenn Sie den ODBC-OLE DB-Anbieter, wie im folgenden Beispiel gezeigt verwenden, muss der Puffer 4 Byte sein.

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

Klicken Sie dann verwendet mit dem folgenden Code:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

Bei Verwendung von `CDynamicAccessor`, des Puffers zur Laufzeit dynamisch festgelegt ist. In diesem Fall können Sie eine spezialisierte Version der `CBookmark` Sie nicht angeben, für die Pufferlänge. Verwenden Sie die Funktion `GetBookmark` das Lesezeichen aus dem aktuellen Datensatz, abrufen, wie in diesem Codebeispiel gezeigt:

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

Informationen zur Unterstützung von Lesezeichen in Anbieter finden Sie unter [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Accessoren](../../data/oledb/using-accessors.md)