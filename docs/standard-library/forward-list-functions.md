---
title: '&lt;forward_list&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: ce66354d2377e52043830925c3f4f880de996663
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt;-Funktionen
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 Tauscht die Elemente zweier Vorwärtslisten aus.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `forward_list`.|  
|`right`|Ein Objekt vom Typ `forward_list`.|  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion führt `left.swap(right)` aus.  
  
## <a name="see-also"></a>Siehe auch  
 [<forward_list>](../standard-library/forward-list.md)



