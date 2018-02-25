---
title: Schleife | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs:
- C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3e076c48b512c6059a2f574a07f6e77acfaca22
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
  
#### <a name="parameters"></a>Parameter  
 `hint_parallel(` `n` `)`  
 Weist den Compiler darauf hin, dass diese Schleife über `n` Threads parallelisiert werden soll, wobei `n` ein positives Ganzzahlliteral oder null ist. Wenn `n` null ist, wird die maximale Anzahl von Threads zur Laufzeit verwendet. Dies ist ein Hinweis für den Compiler, kein Befehl, und es gibt keine Garantie dafür, dass die Schleife parallelisiert wird. Wenn die Schleife Datenabhängigkeiten oder strukturelle Probleme aufweist, z. B. in der Schleife in einen über den Schleifentext hinaus verwendeten Skalar gespeichert wird, dann wird die Schleife nicht parallelisiert.  
  
 Der Compiler ignoriert diese Option aus, es sei denn, die [/Qpar](../build/reference/qpar-auto-parallelizer.md) -Compilerschalter wird angegeben.  
  
 `no_vector`  
 Standardmäßig ist die automatische Vektorisierung aktiviert und versucht, alle Schleifen zu vektorisieren, für die dies als nützlich bewertet wird. Geben Sie dieses Pragma an, um die automatische Vektorisierung für die darauf folgende Schleife zu deaktivieren.  
  
 `ivdep`  
 Weist den Compiler darauf hin, Vektorabhängigkeiten für diese Schleife zu ignorieren. Verwenden Sie diesen Parameter in Verbindung mit `hint_parallel`.  
  
## <a name="remarks"></a>Hinweise  
 Um das `loop`-Pragma zu verwenden, platzieren Sie es direkt vor eine Schleifendefinition, nicht in dieser. Das Pragma gilt für den Gültigkeitsbereich der Schleife, die darauf folgt. Sie können mehrere Pragmas in beliebiger Reihenfolge auf eine Schleife anwenden, aber Sie müssen jedes in einer separaten Pragmaanweisung angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Automatische Parallelisierung und automatische Vektorisierung](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)