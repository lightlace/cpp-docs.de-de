---
title: Compilerfehler Warnung (Stufe 1) C4742 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4742
dev_langs:
- C++
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9c5c891699e89b177f9a3c070a95f496e2c77ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282079"
---
# <a name="compiler-warning-level-1-c4742"></a>Compilerwarnung (Stufe 1) C4742
"Var" verfügt über andere Ausrichtung in "Datei1" und "Datei2": Anzahl und  
  
 Eine externe Variable, die auf die verwiesen wird, oder in zwei Dateien definiert wurden aufweist andere Ausrichtung in diesen Dateien. Diese Warnung wird ausgegeben, wenn der Compiler feststellt, dass `__alignof` für die Variable im *"file1"* unterscheidet sich von `__alignof` für die Variable im *file2*. Dies kann verursacht werden, mithilfe von inkompatiblen Typen beim Deklarieren von Variablen in verschiedenen Dateien oder mithilfe von nicht übereinstimmenden `#pragma pack` in verschiedenen Dateien.  
  
 Um diese Warnung zu beheben, verwenden Sie die gleichen Typdefinition oder verwenden Sie unterschiedliche Namen für die Variablen.  
  
 Weitere Informationen finden Sie unter [Pack](../../preprocessor/pack.md) und [__alignof-Operator](../../cpp/alignof-operator.md).  
  
## <a name="example"></a>Beispiel  
 Dies ist die erste Datei, die den Typ definiert.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4742 generiert.  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```