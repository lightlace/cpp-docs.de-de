---
title: Compilerfehler C3072 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3072
dev_langs:
- C++
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6287ba8e84df96adb0447728dbde8f2031c986cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252483"
---
# <a name="compiler-error-c3072"></a>Compilerfehler C3072
Operator "Operator" kann nicht mit einer Instanz einer Verweisklasse angewendet werden  
  
 Verwenden Sie die unären "`operator` " Operator, um eine Instanz einer Verweisklasse in einen Handletyp konvertieren  
  
 Ein CLR-Typ erfordert CLR-Operatoren, keine systemeigenen (oder Standard-)-Operatoren.  Weitere Informationen finden Sie unter [Verweisoperator nachverfolgen](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3072 generiert.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```