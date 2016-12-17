---
title: "Compilerwarnung (Stufe 4) C4289"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4289"
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: 'var': Die loop\-Steuerelementvariable, die in der for\-Schleife deklariert wurde, wird außerhalb des for\-Schleifenbereichs verwendet  
  
 Bei der Kompilierung mit [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) und **\/Zc:forScope\-** wurde eine in einer [for](../../cpp/for-statement-cpp.md)\-Schleife deklarierte Variable außerhalb des Gültigkeitsbereichs der **for**\-Schleife verwendet.  
  
 Weitere Informationen dazu, wie Sie das Standardverhalten in **for**\-Schleifen mit **\/Ze** festlegen, finden Sie unter [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Im folgenden Beispiel wird C4289 generiert:  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```