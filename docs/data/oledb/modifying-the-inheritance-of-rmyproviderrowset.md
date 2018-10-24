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
ms.openlocfilehash: a6f4827ecf0571878bc0eeaef5dce74326488c61
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990282"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>Ändern der Vererbung von RCustomRowset

Hinzufügen der `IRowsetLocate` im Beispiel des einfachen schreibgeschützten Anbieters Schnittstelle, ändern Sie die Vererbung von `RCustomRowset`. Zunächst `RCustomRowset` erbt `CRowsetImpl`. Sie ändern das erben müssen `CRowsetBaseImpl`.  
  
Zu diesem Zweck erstellen Sie eine neue Klasse `CMyRowsetImpl`im *benutzerdefinierte*RS.h:  
  
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
  
Dies erstellt eine Zuordnung der COM-Schnittstelle, der angibt, `CMyRowsetImpl` aufzurufende `QueryInterface` für beide die `IRowset` und `IRowsetLocate` Schnittstellen. Zum Abrufen aller die Implementierung für das Rowset von anderen Klassen, die zuordnungslinks die `CMyRowsetImpl` Klasse zurück, an die `CRowsetBaseImpl` Klasse durch den OLE DB-Vorlagen definiert; die Karte verwendet-Makro ein, der darüber informiert werden, überprüfen die COM-Zuordnung im OLE DB-Vorlagen `CRowsetBaseImpl` als Reaktion auf eine `QueryInterface` aufrufen.  
  
Verknüpfen Sie abschließend `RAgentRowset` zu `CMyRowsetBaseImpl` szenariooptionen passen die `RAgentRowset` das erben `CMyRowsetImpl`wie folgt:  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>  
```  
  
`RAgentRowset` Nun können Sie die `IRowsetLocate` Schnittstelle profitieren Sie von den Rest der Implementierung für die Rowsetklasse.  
  
Wenn dies geschehen ist, können Sie [an den Consumer zurückgegebene Spalten dynamisch bestimmen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Siehe auch  

[Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)