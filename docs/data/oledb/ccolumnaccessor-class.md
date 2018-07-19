---
title: CColumnAccessor-Klasse | Microsoft Docs
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
ms.openlocfilehash: 8d211277a8354d94f1892b97ea8f808cc0b22c30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095319"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor-Klasse
Generiert Consumercode eingefügten.  
  
## <a name="syntax"></a>Syntax

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Hinweise  
 In den eingefügten Code wird jede Spalte als eine separate Accessor gebunden. Sollten Sie bedenken, dass diese Klasse in den eingefügten Code verwendet wird (z. B. Sie rechnen müssen sie beim Debuggen), jedoch in der Regel nie müssen Sie es oder seine Methoden direkt verwenden.  
  
 `CColumnAccessor` implementiert die folgenden Stubmethoden, von denen jedes an der Funktionalität anderer Methoden des Eigenschaftenaccessors Klasse entsprechen:  
  
-   `CColumnAccessor` Der Konstruktor; instanziiert und initialisiert die `CColumnAccessor` Objekt.  
  
-   `CreateAccessor` Belegt Speicher für die Spalte bindungsstrukturen aus, und die spaltendatenmember initialisiert.  
  
-   **BindColumns** Spalten Accessoren gebunden.  
  
-   **SetParameterBuffer** weist Puffer für Parameter.  
  
-   `AddParameter` Die Parameter Eintrag Strukturen wird ein Parametereintrag eines hinzugefügt.  
  
-   **HasOutputColumns** bestimmt, ob der Accessor Ausgabespalten hat  
  
-   **HasParameters** bestimmt, ob der Accessor über Parameter verfügt.  
  
-   `BindParameters` Die erstellte Parameter an Spalten gebunden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)