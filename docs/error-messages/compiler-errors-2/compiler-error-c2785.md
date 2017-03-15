---
title: "Compilerfehler C2785 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2785"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2785"
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2785
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Deklaration1' und 'Deklaration2' haben verschiedene Rückgabetypen  
  
 Der Rückgabetyp einer Funktionsvorlagenspezialisierung unterscheidet sich vom Rückgabetyp der primären Funktionsvorlage.  
  
### So beheben Sie diesen Fehler  
  
1.  Prüfen Sie alle Spezialisierungen der Funktionsvorlage auf Konsistenz.  
  
## Beispiel  
 Im folgenden Beispiel wird C2785 generiert:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```