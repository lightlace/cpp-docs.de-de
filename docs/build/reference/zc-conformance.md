---
title: "-Zc (Übereinstimmung) | Microsoft Docs"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /zc
dev_langs: C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86b12604a5348c3a1aabb33c7e13a4e7a3c57932
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zc-conformance"></a>/Zc (Übereinstimmung)

Sie können die **/Zc** Compileroptionen in standard oder Microsoft-spezifisches Compilerverhalten anzugeben.

## <a name="syntax"></a>Syntax

> / Zc:_Option_{,_Option_}

## <a name="remarks"></a>Hinweise

Wenn Visual Studio eine Erweiterung für C- oder C++, die nicht mit dem Standard kompatibel ist implementiert, können Sie eine `/Zc` Konformität-Option, um Standard-konformen oder Microsoft-spezifische Verhalten anzugeben. Für einige Optionen ist die Microsoft-spezifische Verhalten Standard, um umfangreiche Änderungen am vorhandenen Code zu verhindern. In anderen Fällen ist die Standardeinstellung das Standardverhalten, wo Verbesserungen bei der Sicherheit, Leistung und Kompatibilität Kosten, die sich aktuelle Änderungen überwiegen. Die Standardeinstellung der einzelnen Optionen für die Übereinstimmung kann in neueren Versionen von Visual Studio ändern. Weitere Informationen zu den einzelnen Optionen für die Übereinstimmung finden Sie unter dem Thema nach der entsprechenden Option.

Dies sind die `/Zc` Compileroptionen:

|Option|Verhalten|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C ++ 17 ausgerichtetes dynamische Zuordnung aktivieren (standardmäßig in C ++ 17).|
|[Auto\[-\]](zc-auto-deduce-variable-type.md)|Erzwingen Sie die neue C++-Standardbibliothek Bedeutung für `auto` (in der Standardeinstellung).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Aktivieren Sie die externen Verknüpfung für `constexpr` Variablen (standardmäßig deaktiviert).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Erzwingen der C++-Standardbibliothek `for` Bereichsregeln (auf der Standardeinstellung).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Aktivieren der implizite `noexcept` auf erforderliche Funktionen (auf standardmäßig).|
|[Inline\[-\]](zc-inline-remove-unreferenced-comdat.md)|Entfernt Unreferenzierte Funktionen oder bei COMDAT ist oder nur eine internen Bindung (standardmäßig deaktiviert).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C ++ 17-Noexcept-Regeln erzwingen (in der Standardeinstellung in C ++ 17 oder höher).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Eine temporäre UDT nicht eine Bindung an ein nicht konstantes Lvalue-Verweis (standardmäßig deaktiviert).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|C++-Standardbibliothek explizite typkonvertierungsregeln erzwingen (standardmäßig deaktiviert).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C ++ 14-Größeninformationen globale-Funktionen zu aktivieren (in der Standardeinstellung).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Disable Zeichenfolgenliteral zu `char*` oder `wchar_t*` Konvertierung (standardmäßig deaktiviert).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|Aktivieren von lokalen statischen Initialisierung threadsichere (auf der Standardeinstellung).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Angenommen `operator new` löst bei einem Fehler (standardmäßig deaktiviert).|
|[Trigraphen\[-\]](zc-trigraphs-trigraphs-substitution.md)|Trigraphen (veraltet, deaktiviert standardmäßig) zu aktivieren.|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t`ein systemeigener Typ., nicht auf eine Typdefinition (auf der Standardeinstellung).|

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Siehe auch

[Compileroptionen](compiler-options.md)  
[Festlegen von Compileroptionen](setting-compiler-options.md)
