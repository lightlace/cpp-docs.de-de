---
title: Compilerwarnung (Stufe 3) C4334 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7bb16ea38b2c2112c12c561398341a7d1adbfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044014"
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334
'Operator': Ergebnis der 32-Bit-Verschiebung wurde implizit zu 64 Bit konvertiert (war eine 64-Bit-Verschiebung vorgesehen?)  
  
 Das Ergebnis der 32-Bit-Verschiebung wurde implizit nach 64-Bit konvertiert, und der Compiler vermutet, dass eine 64-Bit-Verschiebung vorgesehen war. Zur Behebung des Problems verwenden Sie eine 64-Bit-Verschiebung, oder wandeln Sie das Ergebnis der Verschiebung explizit in 64-Bit um.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4334 generiert.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```
||||||| merged common ancestors
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334
'Operator': Ergebnis der 32-Bit-Verschiebung wurde implizit zu 64 Bit konvertiert (war eine 64-Bit-Verschiebung vorgesehen?)  
  
 Das Ergebnis der 32-Bit-Verschiebung wurde implizit nach 64-Bit konvertiert, und der Compiler vermutet, dass eine 64-Bit-Verschiebung vorgesehen war.  Zur Behebung des Problems verwenden Sie eine 64-Bit-Verschiebung, oder wandeln Sie das Ergebnis der Verschiebung explizit in 64-Bit um.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4334 generiert.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```
=======
---
# <a name="compiler-warning-level-3-c4334"></a>Compilerwarnung (Stufe 3) C4334

'Operator': Ergebnis der 32-Bit-Verschiebung wurde implizit zu 64 Bit konvertiert (war eine 64-Bit-Verschiebung vorgesehen?)

Das Ergebnis der 32-Bit-Verschiebung wurde implizit nach 64-Bit konvertiert, und der Compiler vermutet, dass eine 64-Bit-Verschiebung vorgesehen war.  Zur Behebung des Problems verwenden Sie eine 64-Bit-Verschiebung, oder wandeln Sie das Ergebnis der Verschiebung explizit in 64-Bit um.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4334 generiert.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```