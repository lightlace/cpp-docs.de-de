---
title: BEGIN_SCHEMA_MAP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_SCHEMA_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_SCHEMA_MAP macro
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ab6caf2e84f84731439b899b271817b57c550c77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="beginschemamap"></a>BEGIN_SCHEMA_MAP
Kennzeichnet den Beginn einer schemazuordnung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      BEGIN_SCHEMA_MAP(  
   SchemaClass   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *SchemaClass*  
 Die Klasse, die die Zuordnung enthält. Dies wird in der Regel die Sitzungsklasse sein.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in das Windows SDK für Weitere Informationen zu Schemarowsets.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)   
 [IDBSchemaRowsetImpl-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)