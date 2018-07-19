---
title: Compilerwarnung (Stufe 1) C4383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b78209cf4e3e320cca8b161a4e6c99eaca6d771c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286083"
---
# <a name="compiler-warning-level-1-c4383"></a>Compilerwarnung (Stufe 1) C4383
'Instanzendereferenzierungsoperator': die Bedeutung der Dereferenzieren eines Handles kann sich ändern, wenn ein benutzerdefinierte "Operator" Operator vorhanden ist. Schreiben Sie den Operator als eine statische Funktion der Operand explizit sein.  
  
 Wenn Sie eine benutzerdefinierte Instanz zum Überschreiben der Dereferenzierungsoperator in einem verwalteten Typ hinzufügen, überschreiben Sie potenziell die Fähigkeit der Dereferenzierungsoperator des Typs, das Handle des Objekts zurückzugeben. Berücksichtigen Sie beim Schreiben einer Static "," benutzerdefinierte Dereferenzierungsoperator.  
  
 Weitere Informationen finden Sie unter [Handle für Objekt (^)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) und [Verweisoperator nachverfolgen](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Außerdem ist ein Instanzenoperator nicht zur Verfügung, um andere Sprachcompiler über Metadaten verwiesen wird. Weitere Informationen finden Sie unter [benutzerdefinierte Operatoren (C + c++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4383 generiert.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```