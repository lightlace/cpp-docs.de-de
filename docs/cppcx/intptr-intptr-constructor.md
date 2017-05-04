---
title: "IntPtr::IntPtr-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::IntPtr-Konstruktor"
ms.assetid: 828b4c18-790d-4fb4-90fe-47769ff381c0
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::IntPtr-Konstruktor
Initialisiert eine neue Instanz von IntPtr mit dem angegebenen Wert.  
  
## Syntax  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
#### Parameter  
 Wert  
 Ein 64\-Bit\-Handle oder \-Zeiger oder ein Zeiger auf einen 64\-Bit\-Wert oder einen 32\-Bit\-Wert, der in einen 64\-Bit\-Wert konvertiert werden kann.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::IntPtr\-Wertklasse](../cppcx/platform-intptr-value-class.md)