---
title: "Compilerfehler C3113"
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
  - "C3113"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3113"
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3113
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine 'Struktur' kann keine Vorlage\/generisch sein  
  
 Sie haben versucht, eine Klassenvorlage oder generische Klasse auf der Grundlage einer Schnittstelle oder einer Enumeration zu erstellen.  
  
 Im folgenden Beispiel wird C3113 generiert:  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```