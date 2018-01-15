---
title: No_registry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_registry
dev_langs: C++
helpviewer_keywords: no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d2b4b34a4ebf266f4ae8062bb2fff0f80060a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="noregistry"></a>no_registry
`no_registry` weist den Compiler an, nicht die Registrierung für Typbibliotheken zu suchen, die mit `#import` importiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>Parameter  
 *filename*  
 Eine Typbibliothek.  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine referenzierte Typbibliothek nicht in den Verzeichnissen Include gefunden wird, schlägt die Kompilierung fehl, selbst wenn in der Registrierung die Typbibliothek ist.  `no_registry`wird an anderen Typbibliotheken implizit mit importiert übertragen `auto_search`.  
  
 Der Compiler durchsucht niemals die Registrierung nach Typbibliotheken, die mit Dateinamen angegeben und direkt an `#import` übergeben werden.  
  
 Wenn `auto_search` angegeben wird, werden die zusätzlichen `#import`s mit der `no_registry`-Einstellung des ursprünglichen `#import` generiert (wenn die ursprüngliche `#import`-Direktive `no_registry` war, ist ein mit `auto_search` generiertes `#import` ebenfalls `no_registry`).  
  
 `no_registry`ist nützlich, wenn Sie Cross referenzierte Typbibliotheken ohne das Risiko, dass der Compiler eine ältere Version der Datei in der Registrierung suchen importieren möchten.  `no_registry`ist auch nützlich, wenn die Typbibliothek nicht registriert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)