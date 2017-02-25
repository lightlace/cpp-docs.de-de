---
title: "Compilerklassen f&#252;r COM-Unterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, COM-Unterstützung"
  - "COM, Compilerunterstützung"
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerklassen f&#252;r COM-Unterst&#252;tzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Standardklassen werden verwendet, um einige der COM\-Typen zu unterstützen.  Die Klassen werden in "comdef.h" und den Headerdateien, die aus der Typbibliothek generiert werden, definiert.  
  
|Klasse|Zweck|  
|------------|-----------|  
|[\_bstr\_t](../cpp/bstr-t-class.md)|Umschließt den `BSTR`\-Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
|[\_com\_error](../cpp/com-error-class.md)|Definiert das Fehlerobjekt, das von [\_com\_raise\_error](../cpp/com-raise-error.md) bei den meisten Fehlern ausgelöst wird.|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-class.md)|Kapselt COM\-Schnittstellenzeiger und automatisiert die erforderlichen Aufrufe von `AddRef`, **Release** und `QueryInterface`.|  
|[\_variant\_t](../cpp/variant-t-class.md)|Umschließt den **VARIANT**\-Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [COM\-Unterstützung des Compilers](../cpp/compiler-com-support.md)   
 [Globale Funktionen des Compiler\-COM](../cpp/compiler-com-global-functions.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)