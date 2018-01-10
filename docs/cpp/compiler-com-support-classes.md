---
title: "Compilerunterstützung für COM-Klassen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9560b4b3a0623a0e712d5b54d2bbe5de7dbc17e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-com-support-classes"></a>Compilerklassen für COM-Unterstützung
**Microsoft-spezifisch**  
  
 Standardklassen werden verwendet, um einige der COM-Typen zu unterstützen. Die Klassen werden in "comdef.h" und den Headerdateien, die aus der Typbibliothek generiert werden, definiert.  
  
|Klasse|Zweck|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Umschließt den `BSTR`-Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
|[_com_error](../cpp/com-error-class.md)|Definiert das Fehlerobjekt ausgelöste [_com_raise_error](../cpp/com-raise-error.md) bei den meisten Fehlern.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Kapselt COM-Schnittstellenzeiger und automatisiert die erforderlichen Aufrufe von `AddRef`, **Release**, und `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Dient als Wrapper für die **VARIANT** Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-COM-Unterstützung](../cpp/compiler-com-support.md)   
 [Globale Compiler-COM-Funktionen](../cpp/compiler-com-global-functions.md)   
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)