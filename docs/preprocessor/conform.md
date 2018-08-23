---
title: entsprechen | Microsoft-Dokumentation
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
ms.openlocfilehash: 8c6204349731222df99683ddb20b2b2d827b3fcd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538443"
---
# <a name="conform"></a>conform
**C++-spezifisch**  
  
Gibt das Verhalten zur Laufzeit die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
### <a name="parameters"></a>Parameter  
*name*  
Gibt den Namen der zu ändernden Compileroption an. Der einzige gültige *Namen* ist `forScope`.  
  
*anzeigen* (optional)  
Bewirkt, dass die aktuelle Einstellung der *Namen* ("true" oder "false"), die während der Kompilierung mittels einer Warnmeldung angezeigt werden. Beispielsweise `#pragma conform(forScope, show)`.  
  
*On, off*(optional)  
Festlegen von *Namen* zu *auf* ermöglicht die [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption. Der Standardwert ist *aus*.  
  
*Push* (optional)  
Legt den aktuellen Wert der *Namen* auf dem internen compilerstapel ab. Bei Angabe von *Bezeichner*, können Sie angeben, die *auf* oder *aus* Wert für *Namen* auf den Stapel verschoben werden. Beispielsweise `#pragma conform(forScope, push, myname, on)`.  
  
*POP* (optional)  
Legt den Wert der *Namen* auf den Wert am Anfang der internen Compilerstapels fest und ruft dann den Stapel. Wenn Bezeichner angegeben wird *pop*, die Stapel zurück, bis er feststellt, dass den Datensatz mit *Bezeichner*, die ebenfalls entfernt wird; der aktuelle Wert für *Namen* in der nächste Datensatz im Stapel wird der neue Wert für *Namen*. Bei Angabe von Pop mit einer *Bezeichner* das ist nicht in einem Datensatz auf dem Stapel, der *pop* wird ignoriert.  
  
*Bezeichner*(optional)  
Können mit einbezogen werden eine *Push* oder *pop* Befehl. Wenn *Bezeichner* verwendet wird, wird eine *auf* oder *aus* Bezeichner kann auch verwendet werden.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
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