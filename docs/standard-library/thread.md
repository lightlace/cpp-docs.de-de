---
title: '&lt;Thread&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 9b32de86d2ec84017157cccf1a05b9e9b6802e47
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt"></a>&lt;Thread&gt;
Schließen Sie den Standardheader \<Thread > zum Definieren der Klasse `thread` und verschiedene unterstützende Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In Code, der kompiliert wird **/CLR**, dieser Header blockiert.  
  
 Die `__STDCPP_THREADS__` -Makro wird definiert, wie ein Wert ungleich NULL, um anzugeben, dass Threads von dieser Header unterstützt werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[thread-Klasse](../standard-library/thread-class.md)|Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads in einer Anwendung verwendet wird.|  
  
### <a name="public-structures"></a>Öffentliche Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Hash-Struktur (C++-Standardbibliothek)](../standard-library/hash-structure-stl.md)|Definiert eine Memberfunktion, die einen Wert zurückgibt, die eindeutig durch bestimmt ist eine `thread::id`. Die Member-Funktion definiert eine [Hash](../standard-library/hash-class.md) Funktion für die Zuordnung von Werten des Typs `thread::id` einer Verteilung von Indexwerten.|  
  
### <a name="public-functions"></a>Öffentliche Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_id-Funktion](../standard-library/thread-functions.md#get_id_function)|Weist den aktuellen Ausführungsthread eindeutig aus.|  
|[Sleep_for-Funktion](../standard-library/thread-functions.md#sleep_for_function)|Blockiert den aufrufenden Thread.|  
|[Sleep_until-Funktion](../standard-library/thread-functions.md#sleep_until_function)|Blockiert den aufrufenden Thread mindestens bis zum angegebenen Zeitpunkt.|  
|[swap-Funktion](../standard-library/thread-functions.md#swap_function)|Tauscht die Zustände von zwei `thread` Objekte.|  
|[Yield-Funktion](../standard-library/thread-functions.md#yield_function)|Signalisiert dem Betriebssystem, andere Threads auszuführen, auch wenn der aktuelle Thread normalerweise weiterhin ausgeführt werden würde.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator > = (Operator)](../standard-library/thread-operators.md#operator_gt__eq)|Bestimmt, ob ein `thread::id`-Objekt größer als oder gleich einem anderen Objekt ist.|  
|[Operator > Operator](../standard-library/thread-operators.md#operator_gt_)|Bestimmt, ob ein `thread::id`-Objekt größer als ein anderes Objekt ist.|  
|[Operator<=></=>](../standard-library/thread-operators.md#operator_lt__eq)|Bestimmt, ob ein `thread::id`-Objekt kleiner als oder gleich einem anderen Objekt ist.|  
|[Operator<>](../standard-library/thread-operators.md#operator_lt_)|Bestimmt, ob ein `thread::id`-Objekt kleiner als ein anderes Objekt ist.|  
|[Operator! =-Operator](../standard-library/thread-operators.md#operator_neq)|Überprüft zwei `thread::id`-Objekte auf Ungleichheit.|  
|[Operator ==-Operator](../standard-library/thread-operators.md#operator_eq_eq)|Überprüft zwei `thread::id`-Objekte auf Gleichheit.|  
|[Operator<>](../standard-library/thread-operators.md#operator_lt__lt_)|Fügt eine Textdarstellung eines `thread::id`-Objekts in einen Stream ein.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)


