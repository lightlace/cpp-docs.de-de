---
title: Ändern der Vererbung von RCustomRowset
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: 34eb07611ebfff09918d62273d4ca4a8c9cf4f7b
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265151"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>Ändern der Vererbung von RCustomRowset

Hinzufügen der `IRowsetLocate` im Beispiel des einfachen schreibgeschützten Anbieters Schnittstelle, ändern Sie die Vererbung von `CCustomRowset`. Zunächst `CCustomRowset` erbt `CRowsetImpl`. Sie ändern das erben müssen `CRowsetBaseImpl`.

Zu diesem Zweck erstellen Sie eine neue Klasse `CCustomRowsetImpl`im *benutzerdefinierte*RS.h:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

Bearbeiten Sie nun die COM-schnittstellenzuordnung in *benutzerdefinierte*RS.h wie folgt sein:

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Dieser Code erstellt eine Zuordnung der COM-Schnittstelle, der angibt, `CMyRowsetImpl` aufzurufende `QueryInterface` für beide die `IRowset` und `IRowsetLocate` Schnittstellen. Zum Abrufen aller die Implementierung für das Rowset von anderen Klassen, die zuordnungslinks die `CMyRowsetImpl` Klasse zurück, an die `CRowsetBaseImpl` Klasse durch den OLE DB-Vorlagen definiert; die Karte verwendet-Makro ein, der darüber informiert werden, überprüfen die COM-Zuordnung im OLE DB-Vorlagen `CRowsetBaseImpl` als Reaktion auf eine `QueryInterface` aufrufen.

Verknüpfen Sie abschließend `CCustomRowset` zu `CMyRowsetBaseImpl` szenariooptionen passen die `CCustomRowset` das erben `CMyRowsetImpl`wie folgt:

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` Nun können Sie die `IRowsetLocate` Schnittstelle profitieren Sie von den Rest der Implementierung für die Rowsetklasse.

Wenn dies geschehen ist, können Sie [an den Consumer zurückgegebene Spalten dynamisch bestimmen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Siehe auch

[Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
