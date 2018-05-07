---
title: COLUMN_ENTRY_LENGTH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_LENGTH macro
ms.assetid: 1758babf-204c-4d1d-b82a-f9a607072e9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a923f4474f15ffbb2011611bc1f8de476fc399c7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="columnentrylength"></a>COLUMN_ENTRY_LENGTH
Stellt eine Bindung für das Rowset für die spezifische Spalte in der Datenbank dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in der *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 [in] Die Nummer der Spalte, beginnend bei eins. Lesezeichen entspricht Spalte 0 (null).  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 [in] Die Variable, um die Länge der Spalte gebunden werden.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro unterstützt die *Länge* Variable. Es wird in den folgenden Stellen verwendet:  
  
-   Zwischen der [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) und [END_COLUMN_MAP](../../data/oledb/end-column-map.md) Makros.  
  
-   Zwischen der [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) und [END_ACCESSOR](../../data/oledb/end-accessor.md) Makros.  
  
-   Zwischen der [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) und [END_PARAM_MAP](../../data/oledb/end-param-map.md) Makros.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)