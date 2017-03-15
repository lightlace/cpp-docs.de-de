---
title: "Compilerfehler C2970 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2970"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2970"
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2970
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse' : Vorlagenparameter 'param' : 'arg' : Ein Ausdruck, der Objekte mit interner Verknüpfung enthält, kann nicht als Nichttyp\-Argument verwendet werden  
  
 Name oder Adresse einer statischen Variablen können nicht als Vorlagenargument verwendet werden.  Die Vorlagenklasse erwartet einen konstanten Wert, der während der Kompilierung ausgewertet werden kann.  
  
 Im folgenden Beispiel wird C2970 generiert:  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```