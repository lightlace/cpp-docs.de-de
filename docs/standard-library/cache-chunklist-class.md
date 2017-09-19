---
title: cache_chunklist-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- stdext::cache_chunklist
- cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- cache_chunklist class
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 283186349d84225fdf9d1d52ec04817a12f3d27f
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="cachechunklist-class"></a>cache_chunklist-Klasse
Definiert eine [Blockzuweisung](../standard-library/allocators-header.md), die Speicherblöcke einheitlicher Größe zuweist und freigibt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Sz`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Vorlagenklasse verwendet `operator new`, um Blöcke von unformatiertem Speicher zuzuordnen, indem sie eine Unterzuweisung von Blöcken durchführt, um bei Bedarf Speicher für einen Speicherblock zuzuordnen. Sie speichert freigegebene Speicherblöcke in einer separate Freiliste für jeden Block und verwendet `operator delete`, um einen Block freizugeben, wenn keiner seiner Speicherblöcke verwendet wird.  
  
 Jeder Speicherblock enthält `Sz` Bytes Speicherkapazität und einen Zeiger auf den Block, dem er angehört. Jeder Block enthält `Nelts` Speicherblöcke, drei Zeiger, eine ganze Zahl und die Daten, die `operator new` und `operator delete` benötigen.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist)|Konstruiert ein Objekt vom Typ `cache_chunklist`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocate](#allocate)|Belegt einen Speicherblock.|  
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a> cache_chunklist::allocate  
 Belegt einen Speicherblock.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`count`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das zugewiesene Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cache_chunklist"></a> cache_chunklist::cache_chunklist  
 Konstruiert ein Objekt vom Typ `cache_chunklist`.  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="deallocate"></a> cache_chunklist::deallocate  
 Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`ptr`|Ein Zeiger auf das erste Objekt, dessen Zuweisung zum Speicher aufgehoben werden soll.|  
|`count`|Die Anzahl von Objekten, deren Zuweisung zum Speicherplatz aufgehoben werden soll.|  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




