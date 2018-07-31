---
title: CColumnAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c55b2e10112c38835bb1f230970db56a6f53d4e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341061"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor-Klasse
Generiert Consumercode für eingefügte.  
  
## <a name="syntax"></a>Syntax

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Hinweise  
 In den injizierten Code verwenden wird jede Spalte als einen separaten Accessor gebunden. Sie sollten bedenken, dass diese Klasse in den injizierten Code verwendet wird (z. B. stoßen sollten sie beim Debuggen), aber Sie in der Regel nie direkt sie oder ihre Methoden zu verwenden.  
  
 `CColumnAccessor` implementiert die folgenden Stubmethoden, von denen jede an der Funktionalität und der andere Accessor-Klassenmethoden entsprechen:  
  
-   `CColumnAccessor` Der Konstruktor; instanziiert und initialisiert die `CColumnAccessor` Objekt.  
  
-   `CreateAccessor` Belegt Speicher für die Spalte bindungsstrukturen aus, und der Spaltenelemente für die Daten initialisiert.  
  
-   `BindColumns` Bindet Spalten Accessoren.  
  
-   `SetParameterBuffer` Ordnet Puffer für Parameter.  
  
-   `AddParameter` Die Parameter-Eintrag-Strukturen wird ein Parametereintrag hinzugefügt.  
  
-   `HasOutputColumns` Bestimmt, ob der Accessor Spalten ausgegeben hat  
  
-   `HasParameters` Bestimmt, ob der Accessor über Parameter verfügt.  
  
-   `BindParameters` Wird die erstellte Parameter an Spalten gebunden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)