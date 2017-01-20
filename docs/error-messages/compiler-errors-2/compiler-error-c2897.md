---
title: "Compilerfehler C2897"
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
  - "C2897"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2897"
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2897
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Destruktor\/Finalizer kann keine Funktionsvorlage sein  
  
 Da Destruktoren oder Finalizer nicht überladen werden können, ist die Deklaration eines Destruktors als Vorlage \(wodurch eine Gruppe von Destruktoren definiert würde\) nicht zulässig.  
  
 Im folgenden Beispiel wird C2897 generiert:  
  
## Beispiel  
 Im folgenden Beispiel wird C2897 generiert.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2897 generiert.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```