---
title: "Compilerwarnung (Stufe 4) C4714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4714"
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion', als \_\_forceinline markiert, ist keine Inline\-Funktion  
  
 Die festgelegte Funktion wurde als Inlinefunktion angegeben, aber nicht entsprechend erweitert.  
  
 Obwohl der Compiler durch `__forceinline` stärker gebunden wird als durch `__inline`, entscheidet auch hier der Compiler darüber, ob eine Funktion "inline" erweitert wird oder nicht. Jedoch wird nicht heuristisch ermittelt, welche Vorteile die Inline\-Erweiterung dieser Funktion bietet.  
  
 In einigen Situationen erweitert der Compiler eine bestimmte Funktion aus technischen Gründen nicht "inline".  Beispielsweise erweitert der Compiler die folgenden Funktionen nicht "inline":  
  
-   Funktionen, bei denen strukturierte Ausnahmebehandlung und C\+\+\- Ausnahmebehandlung gemischt würden.  
  
-   Einige Funktionen, deren Objekte durch Kopieren erstellt und mit Wert übergeben werden, wenn \-GX\/EHs\/EHa aktiviert ist.  
  
-   Funktionen, die ein nicht entladbares Objekt anhand des Werts zurückgeben, wenn \-GX\/EHs\/Eha aktiviert ist.  
  
-   Funktionen mit Inlineassembly, wenn ohne \-Og\/Ox\/O1\/O2 kompiliert wird.  
  
-   Funktionen mit variabler Argumentliste.  
  
-   Funktionen mit einer **try**\-Anweisung \(C\+\+\-Ausnahmebehandlung\).  
  
 Im folgenden Beispiel wird C4714 generiert:  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```