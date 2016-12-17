---
title: "Compilerfehler C2500"
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
  - "C2500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2500"
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2500
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner1': 'Bezeichner2' ist bereits eine direkte Basisklasse  
  
 Eine Klasse oder Struktur ist mehr als einmal in einer Liste von Basisklassen enthalten.  
  
 Eine direkte Basisklasse ist eine Klasse, die in der Basisliste aufgeführt ist.  Eine indirekte Basisklasse ist eine Basisklasse einer der Klassen, die in der Basisliste enthalten sind.  
  
 Es ist nicht zulässig, eine Klasse mehrfach als direkte Basisklasse anzugeben.  Eine Klasse kann jedoch mehrfach als indirekte Basisklasse verwendet werden.  
  
 Im folgenden Beispiel wird C2500 generiert:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```