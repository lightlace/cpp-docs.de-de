---
title: "Compilerwarnung (Stufe 1) C4288 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4288"
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: 'var': Die Loop\-Steuerelementvariable, die in der for\-Schleife deklariert wurde, wird außerhalb des for\-Schleifenbereichs verwendet. Sie steht in Konflikt mit der Deklaration im äußeren Gültigkeitsbereich  
  
 Bei der Kompilierung mit [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) und **\/Zc:forscope\-** wurde eine in einer **for**\-Schleife deklarierte Variable außerhalb des Gültigkeitsbereichs der [for](../../cpp/for-statement-cpp.md)\-Schleife verwendet.  Durch eine Microsoft\-Erweiterung für die Sprache C\+\+ wird gewährleistet, dass sich diese Variable innerhalb des Gültigkeitsbereichs befindet. C4288 weist Sie darauf hin, dass die erste Deklaration der Variablen nicht verwendet wird.  
  
 Weitere Informationen dazu, wie Sie die Microsoft\-Erweiterung in **for**\-Schleifen mit \/Ze festlegen, finden Sie unter [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
 Im folgenden Beispiel wird C4288 generiert:  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```