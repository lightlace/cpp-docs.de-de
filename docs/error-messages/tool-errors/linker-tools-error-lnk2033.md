---
title: "Linkertoolfehler LNK2033"
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
  - "LNK2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2033"
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht aufgelöstes Typeref\-Token \(Token\) für 'Typ'  
  
 Für einen Typ ist in den MSIL\-Metadaten keine Definition vorhanden.  
  
 LNK2033 kann auftreten, wenn mit **\/clr:safe** kompiliert wird und nur eine Vorwärtsdeklaration für einen Typ in einem MSIL\-Modul vorhanden ist, in dem auf den Typ verwiesen wird.  
  
 Der Typ muss unter **\/clr:safe** definiert werden.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird LNK2033 generiert.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```