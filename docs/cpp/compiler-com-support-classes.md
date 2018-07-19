---
title: Compilerunterstützung für die COM-Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eba4ae92f9db67dfff58ec111b294b6cd26eff5a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939818"
---
# <a name="compiler-com-support-classes"></a>Compilerklassen für COM-Unterstützung
**Microsoft-spezifisch**  
  
 Standardklassen werden verwendet, um einige der COM-Typen zu unterstützen. Die Klassen definiert sind, im \<comdef.h > und den Headerdateien, die aus der Typbibliothek generiert.  
  
|Klasse|Zweck|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Umschließt den `BSTR`-Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
|[_com_error](../cpp/com-error-class.md)|Definiert das Fehlerobjekt, das ausgelöst wird, indem [_com_raise_error](../cpp/com-raise-error.md) bei den meisten Fehlern.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Kapselt COM-Schnittstellenzeiger und automatisiert die erforderlichen Aufrufe von `AddRef`, `Release`, und `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Umschließt den `VARIANT`-Typ, um hilfreiche Operatoren und Methoden bereitzustellen.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-COM-Unterstützung](../cpp/compiler-com-support.md)   
 [Globale Compiler-COM-Funktionen](../cpp/compiler-com-global-functions.md)   
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)