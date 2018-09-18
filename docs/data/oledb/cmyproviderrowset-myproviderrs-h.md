---
title: CMyProviderRowset (MyProviderRS.H) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c7c9830970f6e09d1993ac2fd78510b84068efaa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021269"
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)

Der Assistent generiert einen Eintrag für die Rowset-Objekt. In diesem Fall wird der Name `CMyProviderRowset` zugewiesen Die `CMyProviderRowset` Klasse erbt von einer OLE DB-Anbieter-Klasse namens `CRowsetImpl`, die alle erforderlichen Schnittstellen für Rowset-Objekt implementiert. Der folgende Code zeigt die Vererbungskette für `CRowsetImpl`:  
  
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

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)