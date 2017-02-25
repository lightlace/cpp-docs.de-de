---
title: "Compilerwarnung (Stufe 1) C4742 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4742"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4742"
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4742
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' hat eine unterschiedliche Ausrichtung in 'Datei1' und 'Datei2': Zahl und Zahl  
  
 Eine externe Variable, die in zwei Dateien referenziert oder definiert wurde, verfügt über verschiedene Ausrichtungen in diesen Dateien.  Diese Warnung wird ausgegeben, wenn der Compiler erkennt dass `__alignof` für die Variable in *file1* von `__alignof` für die Variable in *file2* unterscheidet.  Ursache dafür kann die Verwendung nicht kompatibler Typen beim Deklarieren von Variablen in verschiedenen Dateien oder die Verwendung des nicht übereinstimmenden `#pragma pack` in verschiedenen Dateien sein.  
  
 Zur Behebung des Problems verwenden Sie entweder die gleiche Typdefinition oder unterschiedliche Namen für die Variablen.  
  
 Weitere Informationen finden Sie unter [pack](../../preprocessor/pack.md) und [\_\_alignof\-Operator](../../cpp/alignof-operator.md).  
  
## Beispiel  
 Dies ist die erste Datei, die den Typ definiert.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## Beispiel  
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