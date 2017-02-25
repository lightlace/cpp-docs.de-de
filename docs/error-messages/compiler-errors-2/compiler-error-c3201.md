---
title: "Compilerfehler C3201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3201"
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenparameterliste für die Klassenvorlage "template" stimmt nicht mit der Vorlagenparameterliste für den Vorlagenparameter "template" überein.  
  
 Sie haben eine Klassenvorlage im Argument an eine Klassenvorlage übergeben, die keinen Vorlagenparameter verwendet, oder Sie haben eine nicht übereinstimmende Anzahl Vorlagenargumente für das Standardvorlagenargument übergeben.  
  
```  
// C3201.cpp  
template<typename T1, typename T2>  
class X1  
{  
};  
  
template<template<typename T> class U = X1>   // C3201  
class X2  
{  
};  
  
template<template<typename T, typename V> class U = X1>   // OK  
class X3  
{  
};  
```