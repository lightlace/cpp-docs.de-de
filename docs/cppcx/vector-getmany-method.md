---
title: "Vector::GetMany-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetMany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetMany-Methode"
ms.assetid: e2d5ccf4-101a-47e5-a0d8-56f65a7ff28d
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetMany-Methode
Ruft eine Sequenz von Elementen vom aktuellen Vektor ab, die am angegebenen Index beginnt, und kopiert sie in das vom Aufrufer reservierten Array.  
  
## Syntax  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
#### Parameter  
 `startIndex`  
 Der nullbasierte Index des Anfangs der Elemente, die abgerufen werden sollen.  
  
 `dest`  
 Ein vom Aufrufer reserviertes Array von Elementen, die bei dem Element beginnen, das durch `startIndex` angegeben ist, und beim letzten Element im Vektor enden.  
  
## Rückgabewert  
 Die Anzahl der abgerufenen Elemente.  
  
## Hinweise  
 Diese Funktion ist nicht für die direkte Verwendung durch Clientcode vorgesehen. Sie wird intern in der [to\_vector\-Funktion](../cppcx/to-vector-function.md) verwendet, um die effiziente Konvertierung von Platform::Vector\-Instanzen in std::vector\-Instanzen zu ermöglichen.  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [Platform::Collections::Vector\-Klasse](../cppcx/platform-collections-vector-class.md)