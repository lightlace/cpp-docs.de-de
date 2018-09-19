---
title: Schleife | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs:
- C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4881dfdcb92e778501982482abc13cc91836b0
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42539790"
---
# <a name="loop"></a>Loop
Steuert, wie Schleifencode durch die automatische Parallelisierung berücksichtigt werden soll und/oder schließt eine Schleife von der Berücksichtigung durch die automatische Vektorisierung aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma loop( hint_parallel(n) )  
```  
  
```  
#pragma loop( no_vector )  
```  
  
```  
#pragma loop( ivdep )  
```  
  
### <a name="parameters"></a>Parameter  
*hint_parallel(n)*  
Weist den Compiler an, die über diese Schleife parallelisiert werden soll *n* Threads, in denen *n* ist ein positives Ganzzahlliteral oder 0 (null). Wenn *n* NULL ist, wird die maximale Anzahl von Threads zur Laufzeit verwendet. Dies ist ein Hinweis für den Compiler, kein Befehl, und es gibt keine Garantie dafür, dass die Schleife parallelisiert wird. Wenn die Schleife Datenabhängigkeiten oder strukturelle Probleme aufweist, z. B. in der Schleife in einen über den Schleifentext hinaus verwendeten Skalar gespeichert wird, dann wird die Schleife nicht parallelisiert.  
  
Der Compiler ignoriert diese Option aus, es sei denn, die [/Qpar](../build/reference/qpar-auto-parallelizer.md) -Compilerschalter wird angegeben.  
  
*no_vector*  
Standardmäßig ist die automatische Vektorisierung aktiviert und versucht, alle Schleifen zu vektorisieren, für die dies als nützlich bewertet wird. Geben Sie dieses Pragma an, um die automatische Vektorisierung für die darauf folgende Schleife zu deaktivieren.  
  
*ivdep*  
Weist den Compiler darauf hin, Vektorabhängigkeiten für diese Schleife zu ignorieren. Verwenden Sie diese in Verbindung mit *Hint_parallel*.  
  
## <a name="remarks"></a>Hinweise  
 
Verwenden der **Schleife** Pragma, platzieren Sie es direkt vor – nicht in – eine Schleifendefinition. Das Pragma gilt für den Gültigkeitsbereich der Schleife, die darauf folgt. Sie können mehrere Pragmas in beliebiger Reihenfolge auf eine Schleife anwenden, aber Sie müssen jedes in einer separaten Pragmaanweisung angeben.  
  
## <a name="see-also"></a>Siehe auch  
 
[Automatische Parallelisierung und automatische Vektorisierung](../parallel/auto-parallelization-and-auto-vectorization.md)   
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)