---
title: "__set_app_type"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__set_app_type"
  - "_set_app_type"
apilocation: 
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__set_app_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__set_app_type"
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# __set_app_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den aktuellen Anwendungstyp fest.  
  
## Syntax  
  
```cpp  
void __set_app_type (  
   int at  
   )  
```  
  
#### Parameter  
 `at`  
 Ein Wert, der Anwendungstyp angibt.  Mögliche Werte sind:  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|\_UNKNOWN\_APP|Unbekannter Anwendungstyp.|  
|\_CONSOLE\_APP|Konsolenanwendung \(Befehlszeile\).|  
|\_GUI\_APP|Anwendung GUI \(Windows\).|  
  
## Hinweise  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_set\_app\_type|internal.h|