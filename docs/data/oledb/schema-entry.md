---
title: SCHEMA_ENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eed324c184036262093e266c8d246874cd2865a7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
Ordnet eine GUID mit einer Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 Ein Schemarowset-GUID. Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB Programmer's Reference* eine Liste der Schemarowsets und ihren GUIDs.  
  
 *rowsetClass*  
 Die Klasse, die erstellt wird, um die Schemarowsets darstellen.  
  
## <a name="remarks"></a>Hinweise  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) können dann die Abfrage der Zuordnung für eine Liste von GUIDs, oder es kann ein Rowset erstellen, wenn sie eine GUID angegeben wird. Das Schemarowset `IDBSchemaRowsetImpl` erstellt ähnelt einer standardmäßigen `CRowsetImpl`-abgeleitete Klasse, mit der Ausnahme bereitgestellt werden müssen eine **Execute** Methode, die die folgende Signatur:  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 Dies **Execute** Funktion füllt das Rowset Daten. ATL-Projekt-Assistent erstellt, wie in beschrieben [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB Programmer's Reference*, drei ursprüngliche Schemarowsets in das Projekt, für jede der drei obligatorischen OLE DB-Schemas:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 Der Assistent fügt außerdem drei entsprechende Einträge in der schemazuordnung hinzu. Finden Sie unter [erstellen einen OLE DB-Anbieter für Vorlage](../../data/oledb/creating-an-ole-db-provider.md) für Weitere Informationen zum Verwenden des Assistenten zum Erstellen eines Anbieters.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)