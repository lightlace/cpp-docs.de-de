---
title: No_registry | Microsoft Docs
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
ms.openlocfilehash: 416663592f4362c110637fb4d4b4b418d9776cde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849664"
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
 Wenn eine referenzierte Typbibliothek nicht in den Verzeichnissen Include gefunden wird, schlägt die Kompilierung fehl, selbst wenn in der Registrierung die Typbibliothek ist.  `no_registry` wird an anderen Typbibliotheken implizit mit importiert übertragen `auto_search`.  
  
 Der Compiler durchsucht niemals die Registrierung nach Typbibliotheken, die mit Dateinamen angegeben und direkt an `#import` übergeben werden.  
  
 Wenn `auto_search` angegeben wird, werden die zusätzlichen `#import`s mit der `no_registry`-Einstellung des ursprünglichen `#import` generiert (wenn die ursprüngliche `#import`-Direktive `no_registry` war, ist ein mit `auto_search` generiertes `#import` ebenfalls `no_registry`).  
  
 `no_registry` ist nützlich, wenn Sie Cross referenzierte Typbibliotheken ohne das Risiko, dass der Compiler eine ältere Version der Datei in der Registrierung suchen importieren möchten.  `no_registry` ist auch nützlich, wenn die Typbibliothek nicht registriert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)