---
title: "Compilerfehler C2085"
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
  - "C2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2085"
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Nicht in der formalen Parameterliste enthalten  
  
 Der Bezeichner wurde zwar in einer Funktionsdefinition deklariert, jedoch nicht in der Liste der formalen Parameter. \(Nur ANSI C\)  
  
 Im folgenden Beispiel wird C2085 generiert:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Mögliche Lösung:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Wenn das Semikolon fehlt, hat `func1()` die Form einer Funktionsdefinition und nicht die eines Prototyps. Daher wird `main` innerhalb von `func1()` definiert, was die Ausgabe des Fehlers C2085 für den `main`\-Bezeichner zur Folge hat.