---
title: Abrufen eines BLOBs
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: 365b2e5636ecc65ea334730a92953070edd104ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453208"
---
# <a name="retrieving-a-blob"></a>Abrufen eines BLOBs

Sie können ein binary large Object (BLOB) auf verschiedene Weise abrufen. Sie können `DBTYPE_BYTES` Abrufen von BLOBs als eine Folge von Bytes oder einer Schnittstelle wie `ISequentialStream`. Weitere Informationen finden Sie unter [BLOBS und OLE-Objekte](/previous-versions/windows/desktop/ms711511) in die **OLE DB-Programmierreferenz**.

Der folgende Code zeigt, wie Sie ein BLOB mit abrufen `ISequentialStream`. Das Makro [BLOB_ENTRY](../../data/oledb/blob-entry.md) können Sie die Schnittstelle und die Flags, die die Schnittstelle zum angeben. Nach dem Öffnen der Tabelle an, der Code ruft `Read` wiederholt auf `ISequentialStream` , Bytes aus dem BLOB zu lesen. Der Code ruft `Release` auf den Schnittstellenzeiger vor dem Aufruf von dispose `MoveNext` zum Abrufen des nächsten Datensatzes.

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

Klicken Sie dann verwendet mit dem folgenden Code:

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

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

Weitere Informationen zu Makros, die BLOB-Daten behandelt, finden Sie unter **Spaltenzuordnungsmakros** in [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)<br/>
[Makros und globale Funktionen für OLE-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
