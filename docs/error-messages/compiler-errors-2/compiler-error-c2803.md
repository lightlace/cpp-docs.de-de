---
title: "Compilerfehler C2803"
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
  - "C2803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2803"
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operator 'Operator' muss mindestens einen formalen Parameter vom Typ Klasse haben  
  
 Der überladene Operator hat keinen Parameter vom Typ "Klasse".  
  
 Sie müssen einen Parameter pro Verweis \(nicht bei Verwendung von Zeigern, sondern von Verweisen\) oder pro Wert mindestens übergeben, die in der Lage zu sein, ein \< "b" geschrieben \(a und b, die von Typklasse A sind\).  
  
 Wenn beide Parameter Zeiger sind, findet ein reiner Vergleich der Zeigeradressen statt. Die benutzerdefinierte Konvertierung wird nicht verwendet.  
  
 Im folgenden Beispiel wird C2803 generiert:  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```