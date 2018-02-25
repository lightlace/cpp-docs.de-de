---
title: PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_GN
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_GN macro
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff73cda1e676387b4f8ca79ce1ef7cbf8fce13e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="providercolumnentrygn"></a>PROVIDER_COLUMN_ENTRY_GN
Stellt eine bestimmte Spalte, die vom Anbieter unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 [in] Der Spaltenname.  
  
 `ordinal`  
 [in] Die Nummer der Spalte. Wenn die Spalte eine Lesezeichenspalte ist, muss die Nummer der Spalte nicht 0 sein.  
  
 `flags`  
 [in] Gibt an, wie Daten zurückgegeben werden. Finden Sie unter der `dwFlags` Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 [in] Die Größe der Spalte.  
  
 `dbtype`  
 [in] Gibt den Datentyp des Werts an. Finden Sie unter der **wType** Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *precision*  
 [in] Gibt an, die Genauigkeit zu verwendende für das Abrufen von Daten, wenn *DbType* ist `DBTYPE_NUMERIC` oder **DBTYPE_DECIMAL**. Finden Sie unter der **bPrecision** Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 [in] Gibt an, die zu verwendende beim Abrufen von Daten, wenn DbType ist Skala `DBTYPE_NUMERIC` oder **DBTYPE_DECIMAL**. Finden Sie unter der **bScale** Beschreibung im [DBBINDING-Strukturen](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Ein Schemarowset-GUID. Finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB Programmer's Reference* eine Liste der Schemarowsets und ihren GUIDs.  
  
## <a name="remarks"></a>Hinweise  
 Ermöglicht Ihnen das Festlegen der Größe, Datentyp, Genauigkeit, Dezimalstellen und Schemarowset-GUID der Spaltenwerts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)