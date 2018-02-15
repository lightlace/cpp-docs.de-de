---
title: CNoAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9c609a3e15f40311984308c48efbf24d931e188
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cnoaccessor-class"></a>CNoAccessor-Klasse
Kann als ein Vorlagenargument verwendet werden (`TAccessor`) für Vorlagenklassen, z. B. `CCommand` und `CTable`, erfordern, dass ein Argument der Accessor-Klasse.  
  
## <a name="syntax"></a>Syntax

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CNoAccessor` als ein Vorlagenargument, wenn Sie nicht die Klasse zur Unterstützung von Parametern oder Spalten ausgeben möchten.  
  
 `CNoAccessor` implementiert die folgenden Stubmethoden, von denen jedes anderen Methoden des Eigenschaftenaccessors Klasse entsprechen:  
  
-   **BindColumns** -Spalten Accessoren gebunden.  
  
-   `BindParameters` -Die erstellte Parameter an Spalten gebunden.  
  
-   **Binden Sie** -Bindungen erstellt.  
  
-   **Schließen** -schließt die Zugriffsmethode.  
  
-   `ReleaseAccessors` -Gibt die Accessoren erstellt, die von der Klasse frei.  
  
-   `FreeRecordMemory` -Gibt alle Spalten im aktuellen Datensatz, der freigegeben werden müssen.  
  
-   `GetColumnInfo` -Ruft Spalteninformationen aus dem Rowset geöffnet.  
  
-   `GetNumAccessors` -Ruft die Anzahl der Accessoren erstellt, die von der Klasse ab.  
  
-   `IsAutoAccessor` -"Wahr" zurückgegeben, wenn Daten bei einem Verschiebevorgang automatisch für den Accessor abgerufen werden.  
  
-   `GetHAccessor` -Ruft die Accessorhandle für einen angegebenen Accessor ab.  
  
-   `GetBuffer` -Ruft die Zeiger auf den Puffer Lesezeichen ab.  
  
-   **NoBindOnNullRowset** -verhindert die Datenbindung für leere Rowsets.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)