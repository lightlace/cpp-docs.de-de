---
title: COLUMN_ENTRY_TYPE_SIZE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_TYPE_SIZE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_TYPE_SIZE macro
ms.assetid: d8b169e8-af22-464b-8cb3-eaa346f7a739
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1acb969015acda4213532cac3e185bf97a3ac31d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="columnentrytypesize"></a>COLUMN_ENTRY_TYPE_SIZE
Stellt eine Bindung an die spezifische Spalte in der Datenbank dar. Unterstützt `type` und `size` Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `nOrdinal`  
 [in] Die Nummer der Spalte.  
  
 `wType`  
 [in] Der Datentyp der Eintrag in der Spalte.  
  
 `nLength`  
 [in] Die Größe der Eintrag in der Spalte in Bytes.  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
## <a name="remarks"></a>Hinweise  
 Dieses Makro ist eine spezielle Variante des der [COLUMN_ENTRY](../../data/oledb/column-entry.md) Makro, das eine Methode zur Angabe der Datengröße und den Typ enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)