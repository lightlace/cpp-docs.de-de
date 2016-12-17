---
title: "Compilerfehler C2951"
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
  - "C2951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2951"
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typdeklarationen sind nur im globalen, Namespace\- oder Klassengültigkeitsbereich zulässig  
  
 Sie können eine generische oder eine Vorlagenklasse nicht außerhalb des globalen oder des Namespace\-Gültigkeitsbereichs deklarieren.  Wenn Sie die generischen oder die Vorlagendeklarationen in einer Includedatei vornehmen, muss die Includedatei innerhalb des globalen Gültigkeitsbereichs verfügbar sein.  
  
 Im folgenden Beispiel wird C2951 generiert:  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```