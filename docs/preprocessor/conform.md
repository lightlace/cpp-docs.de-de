---
title: entsprechen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b145225cfed3131b406d15827b589aed718d16bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843742"
---
# <a name="conform"></a>conform
**C++-spezifisch**  
  
 Gibt das Verhalten zur Laufzeit die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 Gibt den Namen der zu ändernden Compileroption an. Der einzige gültige *Namen* ist `forScope`.  
  
 **anzeigen** (optional)  
 Bewirkt, dass die aktuelle Einstellung der *Namen* ("true" oder "false"), die während der Kompilierung mittels einer Warnmeldung angezeigt werden. Beispielsweise `#pragma conform(forScope, show)`.  
  
 **On, off**(optional)  
 Festlegen von *Namen* auf **auf** ermöglicht die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) (Compileroption). Die Standardeinstellung ist **deaktiviert**.  
  
 **Push** (optional)  
 Legt den aktuellen Wert der *Namen* auf dem internen compilerstapel ab. Bei Angabe von *Bezeichner*, können Sie angeben, die **auf** oder **deaktiviert** Wert für *Namen* auf den Stapel verschoben werden. Beispielsweise `#pragma conform(forScope, push, myname, on)`.  
  
 **POP** (optional)  
 Legt den Wert des *Namen* auf den Wert am oberen Rand der internen compilerstapel ab und ruft den Stapel dann. Wenn Bezeichner angegeben wird **pop**, der Stapel reduziert, bis er den Datensatz mit findet *Bezeichner*, die ebenfalls entfernt wird; der aktuelle Wert für *Namen* in der nächste Datensatz auf dem Stapel wird der neue Wert für *Namen*. Bei Angabe von Pop mit einer *Bezeichner* , die sich nicht in einem Datensatz im Stapel befindet, die **pop** wird ignoriert.  
  
 *Bezeichner*(optional)  
 Kann enthalten eine **Push** oder **pop** Befehl. Wenn *Bezeichner* verwendet wird, wird eine **auf** oder **deaktiviert** Spezifizierer kann auch verwendet werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)