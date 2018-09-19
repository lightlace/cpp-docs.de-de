---
title: C++-Programmiersprachenreferenz | Microsoft-Dokumentation
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- language reference
- C++, language reference
- language reference, Visual C++
- Visual C++, language reference
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 708db2b20cdbbe2e322075789f64433ff70612a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025515"
---
# <a name="c-language-reference"></a>C++-Programmiersprachenreferenz

In dieser Referenz wird die Implementierung der Programmiersprache C++ in Microsoft Visual C++ erläutert. Die Organisation basiert auf *The Annotated C++ Reference Manual* von Margaret Ellis und Bjarne Stroustrup sowie auf die ANSI/ISO C++ internationalen Standard (ISO/IEC FDIS 14882). Microsoft-spezifische Implementierungen von Funktionen der Programmiersprache C++- sind enthalten.

Eine Übersicht über moderne C++-Programmiertechniken, finden Sie unter [Willkommen zurück bei C++](welcome-back-to-cpp-modern-cpp.md).

Weitere Informationen dazu, wie Sie ein Schlüsselwort oder einen Operator schnell finden, erhalten Sie in den folgenden Tabellen:

- [C++-Schlüsselwörter](../cpp/keywords-cpp.md)

- [C++-Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

## <a name="in-this-section"></a>In diesem Abschnitt

[Lexikalische Konventionen](../cpp/lexical-conventions.md) grundlegende lexikalische Elemente eines C++-Programms: Token, Kommentare, Operatoren, Schlüsselwörter, Markierungszeichen, Literale. Außerdem werden Dateiübersetzung, Operatorrangfolge bzw. Assoziativität behandelt.

[Grundlegende Konzepte](../cpp/basic-concepts-cpp.md) Bereich, Bindung, Programmstart und Beendigung, Speicherklassen und Typen.

[Standardkonvertierungen](../cpp/standard-conversions.md) Typkonvertierungen zwischen den "grundlegenden", oder integrierten Typen. Außerdem arithmetische Konvertierungen und Konvertierungen mit Zeigern, Verweisen und pointer-to-member-Typen.

[Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md) die Operatoren in C++.

[Ausdrücke](../cpp/expressions-cpp.md) Typen von Ausdrücken, Semantik von Ausdrücken, Referenzthemen für Operatoren, Umwandlung und Umwandlungsoperatoren, Laufzeit Typinformationen.

[Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md) eine Programmiertechnik, die implizit definiert eine Funktion und ein Funktionsobjekt dieses Klassentyps erstellt.

[Anweisungen](../cpp/statements-cpp.md) Ausdruck, Null, zusammengesetzte, Auswahl, Iteration, Sprung und Deklaration-Anweisungen.

[Deklarationen und Definitionen](declarations-and-definitions-cpp.md) Speicherklassenspezifizierer, Funktionsdefinitionen, Initialisierungen, Enumerationen, **Klasse**, **Struktur**, und **Union** Deklarationen und **Typedef** Deklarationen. Darüber hinaus **Inline** Funktionen **const** -Schlüsselwort, Namespaces.

[Klassen, Strukturen und Unions](../cpp/classes-and-structs-cpp.md) Einführung in Klassen, Strukturen und Unions. Außerdem Memberfunktionen, spezielle Memberfunktionen, Datenmember, Bitfelder, **dies** Zeiger, geschachtelte Klassen.

[Abgeleitete Klassen](../cpp/inheritance-cpp.md) Einzel- und mehrfachvererbung, **virtuellen** Funktionen, die mehrere Basisklassen, **abstrakte** Klassen, Bereichsregeln. Darüber hinaus die **__super** und **__interface** Schlüsselwörter.

[Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) Steuern des Zugriffs auf Klassenmember: **öffentliche**, **private**, und **geschützt** Schlüsselwörter. Friend-Funktionen und -Klassen.

[Überladen von](operator-overloading.md) überladene Operatoren, Regeln für operatorüberladung.

[Behandlung von Ausnahmen](../cpp/exception-handling-in-visual-cpp.md) C++-Ausnahmebehandlung, strukturierte Ausnahmebehandlung (SEH), Schlüsselwörter, die Schreiben von fehlerbehandlungsanweisungen verwendet.

[Assertion und User-Supplied Meldungen](../cpp/assertion-and-user-supplied-messages-cpp.md) 
 `#error` Richtlinie, die **"static_assert"** -Schlüsselwort, das `assert` Makro.

[Vorlagen](../cpp/templates-cpp.md) vorlagenspezifikationen, Funktionsvorlagen, Klassenvorlagen, **Typename** -Schlüsselwort, Vorlagen im Vergleich zu Makros, Vorlagen und intelligente Zeiger.

[Behandlung von Ereignissen](../cpp/event-handling.md) Deklarieren von Ereignissen und Ereignishandlern.

[Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md) Microsoft C++-spezifische Modifizierer. Arbeitsspeicher adressieren, Aufrufkonventionen, **naked** Funktionen, erweiterte speicherklassenattribute (**__declspec**), **__w64**.

[Inlineassembler](../assembler/inline/inline-assembler.md) Verwenden von Assemblysprache und C++ im **__asm** Blöcke.

[COM-Unterstützung des Compilers](../cpp/compiler-com-support.md) einen Verweis auf die Microsoft-spezifische Klassen und globale Funktionen, die zur Unterstützung von COM-Typen verwendet.

[Microsoft Extensions](../cpp/microsoft-extensions.md) Microsoft-Erweiterungen für C++.

[Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md) Informationen über nicht dem Standard entsprechendes Verhalten von Visual C++-Compiler.

[Willkommen zurück bei C++](welcome-back-to-cpp-modern-cpp.md) ein Überblick über die moderne C++-Programmierung Methoden zum Schreiben von sicheren, korrekte und effiziente Programme.

## <a name="related-sections"></a>Verwandte Abschnitte

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md) Referenzmaterial zur Verwendung von Visual C++ die common Language Runtime als Ziel.

[Referenz zur C/C++-Erstellung](../build/reference/c-cpp-building-reference.md) Compiler-Optionen, Optionen des Linkers und anderen Buildtools.

[Referenz zur C/C++-Präprozessor](../preprocessor/c-cpp-preprocessor-reference.md) Referenzmaterial für Pragmas, präprozessoranweisungen, vordefinierte Makros und der Präprozessor.

[Visual C++-Bibliotheken](../standard-library/cpp-standard-library-reference.md) eine Liste mit Links zu den Startseiten für die verschiedenen Visual C++-Bibliotheken.

## <a name="see-also"></a>Siehe auch

[C-Sprachreferenz](../c-language/c-language-reference.md)