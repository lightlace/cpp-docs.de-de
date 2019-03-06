---
title: /Zc (Übereinstimmung)
ms.date: 03/06/2018
f1_keywords:
- /zc
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 50f3e7a79b80514b6c28bd9aee86c720d6e20cf6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413913"
---
# <a name="zc-conformance"></a>/Zc (Übereinstimmung)

Sie können die **/Zc** Compileroptionen, standard oder Microsoft-spezifisches Compilerverhalten anzugeben.

## <a name="syntax"></a>Syntax

> **/Zc:**_option_{,_option_}

## <a name="remarks"></a>Hinweise

Wenn Visual Studio, eine Erweiterung von C- oder C++, die nicht mit dem Standard kompatibel ist implementiert hat, können Sie mithilfe einer `/Zc` Konformität-Option, um Standard-konformen oder Microsoft-spezifische Verhalten anzugeben. Für einige Optionen die Microsoft-spezifische Verhalten die Standardeinstellung ist, um umfangreiche Änderungen am vorhandenen Code zu verhindern. In anderen Fällen ist der Standardwert dem Standardverhalten von zunichte machen, in denen die Kosten für wichtige Änderungen Verbesserungen bei der Sicherheit, Kompatibilität oder Leistung. Die Standardeinstellung der einzelnen Optionen für die Übereinstimmung mit Standards möglicherweise in neueren Versionen von Visual Studio ändern. Weitere Informationen zu den einzelnen Optionen für die Übereinstimmung mit Standards finden Sie im Thema nach der entsprechenden Option. Die [/ PERMISSIVE--](permissive-standards-conformance.md) -Compileroption legt implizit die Konformität-Optionen, die nicht standardmäßig auf ihre konforme-Einstellung festgelegt werden.

Dies sind die `/Zc` Compileroptionen:

|Option|Verhalten|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C ++ 17 ausgerichtete dynamische speicherbelegung aktivieren (standardmäßig in C ++ 17).|
|[auto\[-\]](zc-auto-deduce-variable-type.md)|Erzwingen Sie die neue C++-standardbedeutung für `auto` (in der Standardeinstellung).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Aktivieren der **__cplusplus** Makro zum Melden des unterstützten Standards (standardmäßig deaktiviert).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Aktivieren Sie die externen Verknüpfung für `constexpr` Variablen (standardmäßig deaktiviert).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Erzwingen von Standard-c++ `for` Bereichsregeln (in der Standardeinstellung).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Aktivieren der impliziten `noexcept` für erforderliche Funktionen (für in der Standardeinstellung).|
|[inline\[-\]](zc-inline-remove-unreferenced-comdat.md)|Nicht referenzierte Funktion oder des entfernen, wenn er COMDAT oder verfügt über nur eine interne Verknüpfung (standardmäßig deaktiviert).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|Erzwingen von C ++ 17-Noexcept-Regeln (für standardmäßig in C ++ 17 oder höher).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Eine temporäre UDT wird nicht an einen nicht Konstanten Lvalue-Verweis gebunden (standardmäßig deaktiviert).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|C++-Standardbibliothek explizite typenkonvertierungsregeln erzwingen (standardmäßig deaktiviert).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C ++ 14-Größeninformationen für globale-Funktionen zu aktivieren (in der Standardeinstellung).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Deaktivieren von Zeichenfolgenliteral zu `char*` oder `wchar_t*` Konvertierung (standardmäßig deaktiviert).|
|[ternäre\[-\]](zc-ternary.md)|Bedingter Operator Regeln auf Operandentypen erzwingen (standardmäßig deaktiviert).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|Thread-sichere lokale statische Initialisierung aktivieren (in der Standardeinstellung).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Angenommen `operator new` löst bei einem Fehler (standardmäßig deaktiviert).|
|[trigraphs\[-\]](zc-trigraphs-trigraphs-substitution.md)|Trigraphen (veraltet, aus der Standardeinstellung) zu aktivieren.|
|[twoPhase-](zc-twophase.md)|Verwenden Sie nicht konforme Vorlage Analyseverhalten (in der Standardeinstellung entsprechen).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` ein systemeigener Typ., nicht Typedef (in der Standardeinstellung).|

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Siehe auch

[Compileroptionen](compiler-options.md)<br/>
[Festlegen von Compileroptionen](setting-compiler-options.md)
