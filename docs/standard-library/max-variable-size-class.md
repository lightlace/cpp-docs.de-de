---
title: max_variable_size-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::max_variable_size
- allocators/stdext::max_variable_size
- max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- max_variable_size class
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: dbb2405313f9b58bc6c5634410a5c378e0f0abca
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="maxvariablesize-class"></a>max_variable_size-Klasse
Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das die maximale Länge eines [freelist](../standard-library/freelist-class.md)-Objekts auf eine maximale Länge einschränkt, die annähernd proportional zur Anzahl von zugewiesenen Speicherblöcken ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|Konstruiert ein Objekt vom Typ `max_variable_size`.|  
  
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
  
##  <a name="allocated"></a> max_variable_size::allocated  
 Erhöht die Anzahl der zugeordneten Speicherblöcke.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Nx`|Der Inkrementwert|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion fügt `_Nx` dem gespeicherten Wert `_Nallocs` hinzu. Diese Memberfunktion wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` auf Operator `new` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `new` zugeordnet wurde.  
  
##  <a name="deallocated"></a> max_variable_size::deallocated  
 Verringert die Anzahl der zugeordneten Speicherblöcke.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Nx`|Der Inkrementwert|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion entfernt `_Nx` vom gespeicherten Wert `_Nallocs`. Diese Memberfunktion wird nach jedem Aufruf von `cache_freelist::deallocate` auf Operator `delete` aufgerufen. Das Argument `_Nx` stellt die Anzahl der Speicherblöcke im Segment dar, die vom Operator `delete` verringert wurde.  
  
##  <a name="full"></a> max_variable_size::full  
 Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn `_Nallocs / 16 + 16 <= _Nblocks`  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf `true` zurückgibt, setzt `deallocate` den Speicherblock auf die Freiliste. Wenn FALSE zurückgegeben wird, ruft `deallocate` den Operator `delete` auf, um die Zuordnung für den Block aufzuheben.  
  
##  <a name="max_variable_size"></a> max_variable_size::max_variable_size  
 Konstruiert ein Objekt vom Typ `max_variable_size`.  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Konstruktor initialisiert die gespeicherten Werte `_Nblocks` und `_Nallocs` auf null.  
  
##  <a name="released"></a> max_variable_size::released  
 Verringert die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void released();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verringert den gespeicherten `_Nblocks`-Wert. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wann immer ein Speicherblock aus der Freiliste entfernt wird.  
  
##  <a name="saved"></a> max_variable_size::saved  
 Erhöht die Anzahl der Speicherblöcke auf der Freiliste.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion inkrementiert den gespeicherten `_Nblocks`-Wert. Diese Memberfunktion wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




