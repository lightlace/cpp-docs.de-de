---
title: "Compilerfehler C2897 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2897"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2897"
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
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