---
title: COLUMN_NAME_TYPE_STATUS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME_TYPE_STATUS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_TYPE_STATUS macro
ms.assetid: 72ad3728-5b3e-4131-9f38-835d776529d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a6c0c4f0e0f36b7ec0fa5eda059e9ed6d0e22c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="columnnametypestatus"></a>COLUMN_NAME_TYPE_STATUS
Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass Sie dieses Makro nimmt auch Daten-Typ und die Spalte Status.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszName`  
 [in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies bewerkstelligen, verlegen Sie eine "L" vor dem Namen, z. B.: `L"MyColumn"`.  
  
 `wType`  
 [in] Der Datentyp.  
  
 *status*  
 [in] Die Variable an folgender Spaltenstatus gebunden werden.  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [COLUMN_NAME](../../data/oledb/column-name.md) Informationen darüber, wie die **COLUMN_NAME_\***  Makros verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE DB-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)