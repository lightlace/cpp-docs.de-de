---
title: max_fixed_size-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a853e417ad79ed27f7579ce50186974abfe21c3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="maxfixedsize-class"></a>max_fixed_size-Klasse
Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt auf eine maximale Länge begrenzt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Max>  
class max_fixed_size
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Max`|Die max-Klasse, die die maximale Anzahl von Elementen zum Speichern in der `freelist` bestimmt.|  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[max_fixed_size](#max_fixed_size)|Konstruiert ein Objekt vom Typ `max_fixed_size`.|  
  
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
  
##  <a name="allocated"></a> max_fixed_size::allocated  
 Erhöht die Anzahl der zugeordneten Speicherblöcke.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Nx`|Der Inkrementwert|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion bleibt untätig. Diese Memberfunktion wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` auf Operator `new` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `new` zugeordnet wurde.  
  
##  <a name="deallocated"></a> max_fixed_size::deallocated  
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
  
##  <a name="full"></a> max_fixed_size::full  
 Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn `Max <= _Nblocks`; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf `true` zurückgibt, setzt `deallocate` den Speicherblock auf die Freiliste. Wenn FALSE zurückgegeben wird, ruft `deallocate` den Operator `delete` auf, um die Zuordnung für den Block aufzuheben.  
  
##  <a name="max_fixed_size"></a> max_fixed_size::max_fixed_size  
 Konstruiert ein Objekt vom Typ `max_fixed_size`.  
  
```
max_fixed_size();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Konstruktor initialisiert den gespeicherten Wert `_Nblocks` auf null.  
  
##  <a name="released"></a> max_fixed_size::released  
 Verringert die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void released();
```  
  
### <a name="remarks"></a>Hinweise  
 Verringert den gespeicherten Wert `_Nblocks`. Die `released`-Memberfunktion der aktuellen [max-Klasse](../standard-library/allocators-header.md) wird von `cache_freelist::allocate` aufgerufen, wenn ein Speicherblock aus der Freiliste entfernt wird.  
  
##  <a name="saved"></a> max_fixed_size::saved  
 Erhöht die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion inkrementiert den gespeicherten `_Nblocks`-Wert. Diese Memberfunktion wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



