---
title: CCustomRowset (CustomRS.H) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211c83ec63611c493f03e48b58619caca373ce65
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216356"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Der Assistent generiert einen Eintrag für die Rowset-Objekt. In diesem Fall heißt es `CCustomRowset`. Die `CCustomRowset` Klasse erbt von einer OLE DB-Anbieter-Klasse namens `CRowsetImpl`, die alle erforderlichen Schnittstellen für Rowset-Objekt implementiert. Der folgende Code zeigt die Vererbungskette für `CRowsetImpl`:

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` verwendet auch die `IAccessor` und `IColumnsInfo` Schnittstellen. Diese Schnittstellen verwendet für die Ausgabe-Felder in Tabellen. Die Klasse bietet auch eine Implementierung für `IRowsetIdentity`, sodass den Consumer feststellen, ob zwei Zeilen identisch sind. Die `IRowsetInfo` -Schnittstelle implementiert Eigenschaften für das Rowsetobjekt. Die `IConvertType` Schnittstelle ermöglicht es, den Anbieter, die Unterschiede zwischen Datentypen, die vom Consumer angeforderte und die vom Anbieter verwendeten aufzulösen.

Die `IRowset` Schnittstelle tatsächlich verarbeitet den Datenabruf. Zunächst ruft der Consumer eine Methode namens `GetNextRows` ein Handle zurück, um eine Zeile, bekannt als ein `HROW`. Der Consumer ruft dann `IRowset::GetData` , `HROW` um die angeforderten Daten abzurufen.

`CRowsetImpl` nimmt auch einige Vorlagenparameter. Mit diesen Parametern können Sie bestimmen, wie die `CRowsetImpl` Klasse verarbeitet die Daten. Die `ArrayType` Arguments können Sie bestimmen, welche-Mechanismus zum Speichern von Daten aus der Zeile verwendet wird. Die *RowClass* Parameter gibt an, welche Klasse enthält eine `HROW`.

Die *RowsetInterface* Parameter können Sie auch die `IRowsetLocate` oder `IRowsetScroll` Schnittstelle. Die `IRowsetLocate` und `IRowsetScroll` Schnittstellen beide von erben `IRowset`. Aus diesem Grund müssen der OLE DB-Anbietervorlagen besondere Behandlung für diese Schnittstellen bereitstellen. Wenn Sie eine dieser Schnittstellen verwenden möchten, müssen Sie diesen Parameter verwenden.

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)<br/>
