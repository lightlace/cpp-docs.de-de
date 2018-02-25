---
title: max_unbounded-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96a4d8a295353f56f2c6b027f72e6353698afdf2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="maxunbounded-class"></a>max_unbounded-Klasse
Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt nicht auf eine maximale Länge begrenzt.  
  
## <a name="syntax"></a>Syntax  
  
```
class max_unbounded
```  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocated](#allocated)|Erhöht die Anzahl der zugeordneten Speicherblöcke.|  
|[deallocated](#deallocated)|Verringert die Anzahl der zugeordneten Speicherblöcke.|  
|[full](#full)|Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.|  
|[released](#released)|Verringert die Anzahl der Speicherblöcke auf der Freiliste.|  
|[saved](#saved)|Erhöht die Anzahl der Speicherblöcke auf der Freiliste.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocated"></a> max_unbounded::allocated  
 Erhöht die Anzahl der zugeordneten Speicherblöcke.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Nx`|Der Inkrementwert|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Sie wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` auf Operator `new` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `new` zugeordnet wurde.  
  
##  <a name="deallocated"></a> max_unbounded::deallocated  
 Verringert die Anzahl der zugeordneten Speicherblöcke.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Nx`|Der Inkrementwert|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Diese Memberfunktion wird nach jedem Aufruf von `cache_freelist::deallocate` auf Operator `delete` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `delete` verringert wurde.  
  
##  <a name="full"></a> max_unbounded::full  
 Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion gibt immer `false` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf `true` zurückgibt, setzt `deallocate` den Speicherblock auf die Freiliste. Wenn FALSE zurückgegeben wird, ruft `deallocate` den Operator `delete` auf, um die Zuordnung für den Block aufzuheben.  
  
##  <a name="released"></a> max_unbounded::released  
 Verringert die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void released();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wann immer ein Speicherblock aus der Freiliste entfernt wird.  
  
##  <a name="saved"></a> max_unbounded::saved  
 Erhöht die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Sie wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



