---
title: No_registry | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105c2b0ee4d2648a1cc43d0baca9f30146184e78
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539040"
---
# <a name="noregistry"></a>no_registry
**No_registry** weist den Compiler nicht an die Registrierung nach Typbibliotheken, die mit importiert suchen `#import`.  
  
## <a name="syntax"></a>Syntax  
  
```  
#import filename no_registry  
```  
  
### <a name="parameters"></a>Parameter  
*filename*  
Eine Typbibliothek.  
  
## <a name="remarks"></a>Hinweise  
 
Wenn keine referenzierte Typbibliothek in der Include-Verzeichnissen nicht gefunden wird, wird die Kompilierung fehlschlagen, auch wenn die Typbibliothek in der Registrierung ist.  **No_registry** überträgt auf andere Typbibliotheken importiert implizit mit `auto_search`.  
  
Der Compiler durchsucht niemals die Registrierung nach Typbibliotheken, die mit Dateinamen angegeben und direkt an `#import` übergeben werden.  
  
Bei der `auto_search` angegeben wird, die zusätzliche `#import`mit s generiert werden die **No_registry** -Einstellung des ursprünglichen `#import` (wenn der ursprüngliche `#import` Richtlinie wurde **No_registry** , `auto_search`-generiert `#import` auch **No_registry**.)  
  
**No_registry** ist nützlich, wenn Sie plattformübergreifende Typbibliotheken ohne das Risiko des Compilers finden in der Registrierung eine ältere Version der Datei importieren möchten. **No_registry** ist auch nützlich, wenn die Typbibliothek nicht registriert ist.  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)