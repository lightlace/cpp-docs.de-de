---
title: _ITERATOR_DEBUG_LEVEL | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
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
ms.sourcegitcommit: 441f493d8ada3ef232f60d917dc3f95812ba9114
ms.openlocfilehash: d5f89f871f60827d894aa414e12b52f0c5f7ef38
ms.lasthandoff: 02/24/2017

---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL
Das `_ITERATOR_DEBUG_LEVEL`-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert sind. Dieses Makro hat Vorrang und kombiniert die Funktionalität der älteren `_SECURE_SCL`- und `_HAS_ITERATOR_DEBUGGING`-Makros.  
  
## <a name="macro-values"></a>Makrowerte  
In der folgenden Tabelle werden die möglichen Werte für das `_ITERATOR_DEBUG_LEVEL`-Makro angezeigt.  
  
|Kompilierungsmodus|Makrowert|Beschreibung|  
|----------------------|----------------|-----------------|  
|**Debuggen**|||  
||0|Deaktiviert überprüfte Iteratoren und das Iteratordebugging.|  
||1|Aktiviert überprüfte Iteratoren und deaktiviert das Iteratordebugging.|  
||2 (Standard)|Aktiviert das Iteratordebugging; überprüfte Iteratoren sind nicht relevant.|  
|**Version**|||  
||0 (Standard)|Deaktivierte überprüfte Iteratoren.|  
||1|Aktiviert überprüfte Iteratoren; das Iteratordebugging ist nicht relevant.|  
  
Im Releasemodus generiert der Compiler einen Fehler, wenn Sie `_ITERATOR_DEBUG_LEVEL` als 2 angeben.  
  
## <a name="remarks"></a>Hinweise  
Das `_ITERATOR_DEBUG_LEVEL`-Makro steuert, ob [überprüfte Iteratoren](../standard-library/checked-iterators.md) aktiviert ist, und im Debugmodus, ob die [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md) aktiviert ist. Wenn `_ITERATOR_DEBUG_LEVEL` als 1 oder 2 definiert ist, stellen aktivierte Iteratoren sicher, dass die Grenzen des Containers nicht überschrieben werden. Wenn `_ITERATOR_DEBUG_LEVEL` gleich 0 ist, werden Iteratoren nicht überprüft. Wenn `_ITERATOR_DEBUG_LEVEL` als 1 definiert ist, verursacht die unsichere Verwendung von Iteratoren einen Laufzeitfehler und das Programm wird beendet. Wenn `_ITERATOR_DEBUG_LEVEL` als 2 definiert ist, verursacht die unsichere Verwendung von Iteratoren eine Assert-Anweisung und ein Laufzeitfehler-Dialogfeld, dass Sie den Debugger unterbrechen lässt. 

Da das `_ITERATOR_DEBUG_LEVEL`-Makro ähnliche Funktionalitäten wie die `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING`-Makros unterstützt, sind Sie möglicherweise unsicher, welche Makros und Makrowerte Sie in einer bestimmten Situation verwenden sollten. Um Verwirrung zu vermeiden, wird empfohlen, nur das `_ITERATOR_DEBUG_LEVEL`-Makro zu verwenden. Diese Tabelle beschreibt den entsprechenden `_ITERATOR_DEBUG_LEVEL`-Makrowert für die Verwendung verschiedener Werte von `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING` in vorhandenem Code.  
  
|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (Releasestandard)|0 (deaktiviert)|0 (deaktiviert)|
|1|1 (aktiviert)|0 (deaktiviert)|
|2 (Debug-Standard)|(nicht relevant)|1 (aktiviert im Debugmodus)|
  
Informationen über das Deaktivieren der Warnungen für überprüfte Iteratoren finden Sie unter [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
### <a name="example"></a>Beispiel  
  
Verwenden Sie für die Angabe eines Werts für das `_ITERATOR_DEBUG_LEVEL`-Makro eine [/D](../build/reference/d-preprocessor-definitions.md)-Compileroption, um es in der Befehlszeile zu definieren, oder verwenden Sie `#define`, bevor die Kopfzeilen der C++-Standardbibliothek in Ihren Quelldateien enthalten sind. Um beispielsweise in der Befehlszeile *sample.cpp* im Debugmodus zu kompilieren und die Unterstützung für Iteratordebugging zu verwenden, können Sie die `_ITERATOR_DEBUG_LEVEL`-Makrodefinition angeben:  
  
`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`  
  
Geben Sie das Makro in einer Quelldatei ein, bevor die Kopfzeilen der Standardbibliothek Iteratoren definieren.  
  
```cpp  
// sample.cpp  
  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <vector>  
  
// ...
```  
  
## <a name="see-also"></a>Siehe auch  
[Überprüfte Iteratoren](../standard-library/checked-iterators.md)   
[Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)   
[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)

