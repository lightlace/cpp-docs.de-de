---
title: "&lt; Thread &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<thread>"
dev_langs: 
  - "C++"
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# &lt; Thread &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schließen Sie den Standardheader \< Thread> So definieren Sie die Klasse `thread` und verschiedene unterstützende Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In Code, der kompiliert wurde **"/ CLR"** oder **/clr: pure**, dieser Header blockiert.  
  
 Die `__STDCPP_THREADS__` -Makro wird definiert als einen Wert ungleich NULL, um anzugeben, dass Threads von dieser Header unterstützt werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-classes"></a>Öffentliche Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Thread-Klasse](../standard-library/thread-class.md)|Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads in einer Anwendung verwendet wird.|  
  
### <a name="public-structures"></a>Öffentliche Strukturen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Hash-Struktur (STL)](../standard-library/hash-structure-stl.md)|Definiert eine Memberfunktion, die einen Wert zurückgibt, die durch nicht eindeutig bestimmt ist eine `thread::id`. Die Member-Funktion definiert einen [Hash](hash%20Class.md) Funktion für die Zuordnung von Werten des Typs `thread::id` auf eine Verteilung von Indexwerten.|  
  
### <a name="public-functions"></a>Öffentliche Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_id-Funktion](../Topic/%3Cthread%3E%20functions.md#get_id_function)|Identifiziert eindeutig den aktuellen Thread der Ausführung.|  
|[Sleep_for-Funktion](../Topic/%3Cthread%3E%20functions.md#sleep_for_function)|Blockiert den aufrufenden Thread.|  
|[Sleep_until-Funktion](../Topic/%3Cthread%3E%20functions.md#sleep_until_function)|Blockiert den aufrufenden Thread mindestens bis zum angegebenen Zeitpunkt.|  
|[Swap-Funktion](../Topic/%3Cthread%3E%20functions.md#swap_function)|Tauscht die Zustände von zwei `thread` Objekte.|  
|[Yield-Funktion](../Topic/%3Cthread%3E%20functions.md#yield_function)|Signalisiert das Betriebssystem an andere Threads ausgeführt werden, selbst wenn der aktuelle Thread in der Regel führen Sie weiterhin.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator > =-Operator](../Topic/%3Cthread%3E%20operators.md#operator_gt__eq)|Bestimmt, ob ein `thread::id` Objekt ist größer als oder gleich einem anderen.|  
|[Operator >-Operator](../Topic/%3Cthread%3E%20operators.md#operator_gt_)|Bestimmt, ob ein `thread::id` -Quellobjekt ist größer als ein anderes.|  
|[Operator < =-Operator](../Topic/%3Cthread%3E%20operators.md#operator_lt__eq)|Bestimmt, ob ein `thread::id` Objekt ist kleiner als oder gleich einem anderen.|  
|[Operator <-Operator](../Topic/%3Cthread%3E%20operators.md#operator_lt_)|Bestimmt, ob ein `thread::id` -Objekts kleiner als ein anderes ist.|  
|[Operator! =-Operator](../Topic/%3Cthread%3E%20operators.md#operator_neq)|Überprüft zwei `thread::id`-Objekte auf Ungleichheit.|  
|[Operator ==-Operator](../Topic/%3Cthread%3E%20operators.md#operator_eq_eq)|Überprüft zwei `thread::id`-Objekte auf Gleichheit.|  
|[Operator << Operator](../Topic/%3Cthread%3E%20operators.md#operator_lt__lt_)|Fügt eine Textdarstellung einer `thread::id` Objekt in einen Stream.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

