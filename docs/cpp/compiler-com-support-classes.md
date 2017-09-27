---
title: "Compilerunterstützung für COM-Klassen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 48540910db97e7662eeaa7e8a7febf7e44df653b
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
