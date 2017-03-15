---
title: "__RTDynamicCast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__RTDynamicCast"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__RTDynamicCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__RTDynamicCast"
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __RTDynamicCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Laufzeitimplementierung des Operators [Der Operator dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
## Syntax  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### Parameter  
 `inptr`  
 Zeiger zu einem polymorphen Objekt.  
  
 `VfDelta`  
 Offset des virtuellen Funktionszeigers im Objekt.  
  
 `SrcType`  
 Statischer Typ des Objekts dargestellt auf `inptr` durch den Parameter.  
  
 `TargetType`  
 Beabsichtigtes Ergebnis der Umwandlung.  
  
 `isReference`  
 `true`, wenn die Eingabe ein Verweis ist; `false`, wenn die Eingabe ein Zeiger ist.  
  
## Rückgabewert  
 Zeiger zum entsprechenden Unterobjekt, wenn erfolgreich; andernfalls NULL.  
  
## Ausnahmen  
 `bad_cast()`, wenn die Eingabe in `dynamic_cast<>` einen Verweis und die Umwandlung ist, schlägt fehl.  
  
## Hinweise  
 Konvertiert `inptr` in ein Objekt des Typs `TargetType`.  Der `inptr`\-Typ muss ein Zeiger sein, wenn `TargetType` ein Zeiger ist, oder ein lvalue, wenn `TargetType` ein Verweis ist.  `TargetType` muss ein Zeiger oder Verweis auf einem vorher definierten Klassentyps einzubinden oder ein Zeiger sein.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_RTDynamicCast|rtti.h|