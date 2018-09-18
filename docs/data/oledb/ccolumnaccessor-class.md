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
ms.openlocfilehash: b1843b6279cb7c86762cc6d975a2a7e67d3d278d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055636"
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
  
- `CColumnAccessor` Der Konstruktor; instanziiert und initialisiert die `CColumnAccessor` Objekt.  
  
- `CreateAccessor` Belegt Speicher für die Spalte bindungsstrukturen aus, und der Spaltenelemente für die Daten initialisiert.  
  
- `BindColumns` Bindet Spalten Accessoren.  
  
- `SetParameterBuffer` Ordnet Puffer für Parameter.  
  
- `AddParameter` Die Parameter-Eintrag-Strukturen wird ein Parametereintrag hinzugefügt.  
  
- `HasOutputColumns` Bestimmt, ob der Accessor Spalten ausgegeben hat  
  
- `HasParameters` Bestimmt, ob der Accessor über Parameter verfügt.  
  
- `BindParameters` Wird die erstellte Parameter an Spalten gebunden.  
  
## <a name="requirements"></a>Anforderungen  

**Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)