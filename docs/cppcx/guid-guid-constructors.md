---
title: "Guid::Guid-Konstruktoren | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Guid::Guid"
  - "Guid::Guid"
ms.assetid: dfa4dcad-1c3b-481f-9f60-05141b9788d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::Guid-Konstruktoren
Initialisiert eine neue Instanz einer GUID\-Struktur.  
  
## Syntax  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  
);  
  
    Guid(   
        GUID m  
);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n  
);  
```  
  
#### Parameter  
 `a`  
 Die ersten 4 Bytes der GUID.  
  
 `b`  
 Die nächsten 2 Bytes der GUID.  
  
 `c`  
 Die nächsten 2 Bytes der GUID.  
  
 `d`  
 Das nächste Byte der GUID.  
  
 `e`  
 Das nächste Byte der GUID.  
  
 `f`  
 Das nächste Byte der GUID.  
  
 `g`  
 Das nächste Byte der GUID.  
  
 `h`  
 Das nächste Byte der GUID.  
  
 `i`  
 Das nächste Byte der GUID.  
  
 `j`  
 Das nächste Byte der GUID.  
  
 `k`  
 Das nächste Byte der GUID.  
  
 `m`  
 Eine GUID wie in der Definition.  
  
 `n`  
 Die restlichen 8 Bytes der GUID.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::Guid\-Wertklasse](../cppcx/platform-guid-value-class.md)