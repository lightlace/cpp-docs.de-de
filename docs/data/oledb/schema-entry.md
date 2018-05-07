---
title: SCHEMA_ENTRY | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 665b337861959b28670a0b2e57649814853a7384
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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