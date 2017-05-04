---
title: "IntPtr::op_explicit-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::op_explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::op_explicit-Methode"
ms.assetid: cc52e9d5-fe73-471b-8cff-d9f684ba6e20
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::op_explicit-Operator
Konvertiert den angegebenen Parameter in einen IntPtr oder einen Zeiger auf einen IntPtr\-Wert.  
  
## Syntax  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
#### Parameter  
 value1  
 Ein Zeiger auf ein Handle oder einem IntPtr.  
  
 value2  
 Eine 32\-Bit\-Ganzzahl, die in einen IntPtr konvertiert werden kann.  
  
 value3  
 Ein IntPtr.  
  
## Rückgabewert  
 Der erste und zweite Operator gibt ein IntPtr zurück. Der dritte Operator gibt einen Zeiger auf den Wert zurück, der durch das aktuelle IntPtr dargestellt wird.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::IntPtr\-Wertklasse](../cppcx/platform-intptr-value-class.md)