---
title: COLUMN_NAME_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME_EX
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_EX macro
ms.assetid: 4f916a85-f6ae-464a-9cbe-0a56dbb274a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3992a727519ed83a0dbf4c570bad3bbf8d0404ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="columnnameex"></a>COLUMN_NAME_EX
Stellt eine Bindung für das Rowset für die spezifische Spalte des Rowsets dar. Ähnlich wie [COLUMN_NAME](../../data/oledb/column-name.md), außer dass dieses Makro auch Datentyp, Größe, Genauigkeit, Dezimalstellen, Spaltenlänge und Status in der Spalte verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszName`  
 [in] Ein Zeiger auf den Namen der Spalte. Der Name muss eine Unicode-Zeichenfolge sein. Sie können dies bewerkstelligen, verlegen Sie eine "L" vor dem Namen, z. B.: `L"MyColumn"`.  
  
 `wType`  
 [in] Der Datentyp.  
  
 `nLength`  
 [in] Die Datengröße in Byte.  
  
 `nPrecision`  
 [in] Die maximale Genauigkeit verwenden beim Abrufen von Daten und `wType` ist `DBTYPE_NUMERIC`. Andernfalls wird dieser Parameter ignoriert.  
  
 `nScale`  
 [in] Die Skalierung zu verwendende Daten abrufen und `wType` ist `DBTYPE_NUMERIC` oder **DBTYPE_DECIMAL**.  
  
 `data`  
 [in] Die entsprechenden Datenmember im Benutzerdatensatz.  
  
 *length*  
 [in] Die Variable, um die Länge der Spalte gebunden werden.  
  
 *status*  
 [in] Die Variable an folgender Spaltenstatus gebunden werden.  
  
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
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)