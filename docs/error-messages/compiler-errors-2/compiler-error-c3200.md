---
title: "Compilerfehler C3200"
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
  - "C3200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3200"
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Vorlage': Ungültiges Vorlagenargument für den Vorlagenparameter 'Parameter'; Klassenvorlage erwartet  
  
 An eine Klassenvorlage wurde ein ungültiges Argument übergeben.  Die Klassenvorlage erwartet eine Vorlage als Parameter.  Im folgenden Beispiel generiert der Aufruf von `Y<int, int> aY` den Fehler C3200.  Der erste Parameter muss eine Vorlage sein, z. B. `Y<X, int> aY`.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```