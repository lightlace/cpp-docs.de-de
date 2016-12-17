---
title: "Compilerfehler C3350"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3350"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3350"
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3350
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Delegat": Ein Delegatkonstruktor erwartet "Zahl" Argument\(e\).  
  
 Wenn Sie eine Instanz eines Delegaten erstellen, müssen Sie an eine Instanz des Typs mit der Delegatfunktion und an die Funktion zwei Argumente übergeben.  
  
 Im folgenden Beispiel wird C3350 generiert:  
  
```  
// C3350.cpp // compile with: /clr delegate void SumDelegate(); public ref class X { public: void F() {} static void F2() {} }; int main() { X ^ MyX = gcnew X(); SumDelegate ^ pSD = gcnew SumDelegate();   // C3350 SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F); SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2); }  
```  
  
 **Verwaltete Erweiterungen für C\+\+**  
  
 Im folgenden Beispiel wird C3350 generiert:  
  
```  
// C3350b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __delegate void SumDelegate(); public __gc class X { public: void F() {} static void F2() {} }; int main() { X * MyX = new X(); SumDelegate *pSD = new SumDelegate();   // C3350 SumDelegate *pSD1 = new SumDelegate(MyX, &X::F); SumDelegate *pSD2 = new SumDelegate(&X::F2); }  
```