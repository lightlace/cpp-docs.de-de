---
title: freelist-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0e85e247346e71093df393a69b91b579236e2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="freelist-class"></a>freelist-Klasse
Verwaltet eine Liste von Speicherblöcken  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Sz`|Die Anzahl der zuzuweisenden Elemente im Array|  
|`Max`|Die max-Klasse, die die maximale Anzahl von Elementen darstellt, die in der freien Liste gespeichert werden. Die Klasse kann [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) oder [max_variable_size](../standard-library/max-variable-size-class.md) sein.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Vorlagenklasse verwaltet eine Liste von Speicherblöcken der Größe `Sz`, wobei die maximale, durch die max-Klasse festgelegte Länge der Liste an `Max` übergeben wird.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[freelist](#freelist)|Konstruiert ein Objekt vom Typ `freelist`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[pop](#pop)|Entfernt den ersten Speicherblock aus der freien Liste|  
|[push](#push)|Fügt der Liste einen Speicherblock hinzu|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="freelist"></a> freelist::freelist  
 Konstruiert ein Objekt vom Typ `freelist`.  
  
```
freelist();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="pop"></a> freelist::pop  
 Entfernt den ersten Speicherblock aus der freien Liste  
  
```
void *pop();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Speicherblock zurück, der aus der Liste entfernt wurde  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt `NULL` zurück, wenn die Liste leer ist. Andernfalls entfernt sie den ersten Speicherblock aus der Liste.  
  
##  <a name="push"></a> freelist::push  
 Fügt der Liste einen Speicherblock hinzu  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`ptr`|Ein Zeiger auf den Speicherblock, der der freien Liste hinzugefügt werden soll|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Funktion `full` der max-Klasse `false` zurückgibt. Andernfalls gibt die Funktion `push` `false` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Funktion `full` der max-Klasse `false` zurückgibt, fügt diese Memberfunktion den Speicherblock, auf den `ptr` zeigt, zu dem Anfang der Liste hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



