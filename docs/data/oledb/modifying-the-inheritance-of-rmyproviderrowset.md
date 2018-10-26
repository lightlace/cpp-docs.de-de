---
title: Ändern der Vererbung von RCustomRowset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a9b6e238d3824451ab0f820917c34c97826ffab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060389"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>Ändern der Vererbung von RCustomRowset

Hinzufügen der `IRowsetLocate` im Beispiel des einfachen schreibgeschützten Anbieters Schnittstelle, ändern Sie die Vererbung von `RCustomRowset`. Zunächst `RCustomRowset` erbt `CRowsetImpl`. Sie ändern das erben müssen `CRowsetBaseImpl`.

Zu diesem Zweck erstellen Sie eine neue Klasse `CCustomRowsetImpl`, im CustomRS.h:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CCustomRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

Bearbeiten Sie nun die COM-schnittstellenzuordnung in CustomRS.h wie folgt sein:

```cpp
BEGIN_COM_MAP(CCustomRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Dies erstellt eine Zuordnung der COM-Schnittstelle, der angibt, `CCustomRowsetImpl` aufzurufende `QueryInterface` für beide die `IRowset` und `IRowsetLocate` Schnittstellen. Zum Abrufen aller die Implementierung für das Rowset von anderen Klassen, die zuordnungslinks die `CCustomRowsetImpl` Klasse zurück, an die `CRowsetBaseImpl` Klasse durch den OLE DB-Vorlagen definiert; die Karte verwendet-Makro ein, der darüber informiert werden, überprüfen die COM-Zuordnung im OLE DB-Vorlagen `CRowsetBaseImpl` als Reaktion auf eine `QueryInterface` aufrufen.

Verknüpfen Sie abschließend `RAgentRowset` zu `CCustomRowsetBaseImpl` szenariooptionen passen die `RAgentRowset` das erben `CCustomRowsetImpl`wie folgt:

```cpp
class RAgentRowset : public CCustomRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>
```

`RAgentRowset` Nun können Sie die `IRowsetLocate` Schnittstelle profitieren Sie von den Rest der Implementierung für die Rowsetklasse.

Wenn dies geschehen ist, können Sie [an den Consumer zurückgegebene Spalten dynamisch bestimmen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Siehe auch

[Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)