---
title: CMyProviderRowset (MyProviderRS.H) | Microsoft Docs
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
ms.openlocfilehash: 7bfd7c927342790fee3be2b5a7d48bccba3ea168
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)
Der Assistent generiert einen Eintrag für die Rowset-Objekte. In diesem Fall wird der Name `CMyProviderRowset` zugewiesen Die `CMyProviderRowset` Klasse erbt von einer OLE DB-Anbieter-Klasse namens `CRowsetImpl`, die alle erforderlichen Schnittstellen für Rowset-Objekte implementiert. Der folgende Code zeigt die Vererbungskette für `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
 `CRowsetImpl` verwendet auch die `IAccessor` und `IColumnsInfo` Schnittstellen. Diese Schnittstellen verwendet für die Ausgabefelder in Tabellen. Die Klasse bietet auch eine Implementierung für **IRowsetIdentity**, dadurch wird den Consumer bestimmt, ob zwei Zeilen identisch sind. Die `IRowsetInfo` Schnittstelle implementiert Eigenschaften für das Rowsetobjekt. Die **IConvertType** Schnittstelle ermöglicht es den Anbieter, Unterschiede zwischen den Datentypen, die vom Consumer angefordert und vom Anbieter verwendeten aufzulösen.  
  
 Die `IRowset` Schnittstelle tatsächlich Datenabruf behandelt. Zunächst ruft der Consumer eine Methode namens `GetNextRows` zurückzugebenden ein Handle für eine Zeile, bekannt als ein **HROW**. Der Consumer ruft dann **IRowset:: GetData** , **HROW** zum Abrufen der angeforderten Daten.  
  
 `CRowsetImpl` Außerdem akzeptiert es mehrere Vorlagenparameter. Mit diesen Parametern können Sie bestimmen, wie die `CRowsetImpl` Klasse verarbeitet Daten. Die `ArrayType` Argument können Sie bestimmen, welche Speichermechanismus zum Speichern von Daten aus der Zeile verwendet wird. Die **RowClass** Parameter gibt an, welche Klasse enthält eine **HROW**.  
  
 Die **RowsetInterface** Parameter können Sie auch die `IRowsetLocate` oder `IRowsetScroll` Schnittstelle. Die `IRowsetLocate` und `IRowsetScroll` Schnittstellen beide von erben `IRowset`. Deshalb müssen der OLE DB-Anbietervorlagen Sonderbehandlung für diese Schnittstellen bereitstellen. Wenn Sie eine dieser Schnittstellen verwenden möchten, müssen Sie diesen Parameter verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)