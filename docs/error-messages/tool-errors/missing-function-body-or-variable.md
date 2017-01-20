---
title: "Fehlender Funktionsrumpf oder fehlende Variable"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsrumpf"
  - "Variablen, Fehlen"
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Fehlender Funktionsrumpf oder fehlende Variable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn einfach nur ein Funktionsprototyp vorhanden ist, setzt der Compiler die Verarbeitung zwar ohne Fehler fort, der Linker ist jedoch nicht in der Lage, einen Aufruf einer Adresse aufzulösen, da kein Platz für den Funktionscode oder Variablen reserviert ist.  Der Fehler tritt erst auf, wenn Sie einen Aufruf für eine Funktion erstellen, den der Linker auflösen muss.  
  
## Beispiel  
 Der Funktionsaufruf in main verursacht LNK2019, da der Prototyp es zulässt, dass der Compiler die Funktion als vorhanden betrachtet.  Der Linker stellt dann fest, dass dies nicht der Fall ist.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## Beispiel  
 Stellen Sie unter C\+\+ sicher, dass die Implementierung einer spezifischen Funktion für eine Klasse und nicht nur ein Prototyp in der Klassendefinition enthalten ist.  Wenn Sie die Klasse außerhalb der Headerdatei definieren, sollten Sie außerdem darauf achten, dass der Klassenname vor der Funktion \(`Classname``::``memberfunction`\) aufgeführt ist.  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)