---
title: max_none Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ffa6da15f19d3215080d7a1e5355134409765da5
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="maxnone-class"></a>max_none-Klasse
Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt auf eine maximale Länge begrenzt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Max`|Die max-Klasse, die die maximale Anzahl von Elementen zum Speichern in der `freelist` bestimmt.|  
  
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
  
##  <a name="allocated"></a> max_none::allocated  
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
  
##  <a name="deallocated"></a> max_none::deallocated  
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
  
##  <a name="full"></a> max_none::full  
 Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion gibt immer `true` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf `true` zurückgibt, setzt `deallocate` den Speicherblock auf die Freiliste. Wenn FALSE zurückgegeben wird, ruft `deallocate` den Operator `delete` auf, um die Zuordnung für den Block aufzuheben.  
  
##  <a name="released"></a> max_none::released  
 Verringert die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void released();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wenn ein Speicherblock aus der Freiliste entfernt wird.  
  
##  <a name="saved"></a> max_none::saved  
 Erhöht die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Sie wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



