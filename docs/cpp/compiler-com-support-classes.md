---
title: Compilerklassen für COM-Unterstützung
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: 066fe797bc500625e96e027777a70f278b88cddb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479663"
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

[COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)<br/>
[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)