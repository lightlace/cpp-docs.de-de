---
title: Präprozessordirektiven
ms.date: 08/29/2019
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 86432ebf210523dd958f3258075d9e9c6d3bb4e6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222280"
---
# <a name="preprocessor-directives"></a>Präprozessordirektiven

Präprozessordirektiven, `#define` wie `#ifdef`z. b. und, werden in der Regel verwendet, um das ändern und Kompilieren von Quell Programmen in verschiedenen Ausführungs Umgebungen zu vereinfachen. Anweisungen in der Quelldatei weisen den Präprozessor an, bestimmte Aktionen auszuführen. Beispielsweise kann der Präprozessor Token im Text ersetzen, den Inhalt von anderen Dateien in die Quelldatei einfügen oder die Kompilierung eines Teils der Datei unterdrücken, indem er Textabschnitte entfernt. Präprozessorzeilen werden vor der Makroerweiterung erkannt und ausgeführt. Wenn ein Makro in etwas, das wie ein Präprozessorbefehl aussieht, erweitert wird, wird es daher vom Präprozessor nicht erkannt.

Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldatei Anweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden. Der Zeichensatz, der in Präprozessoranweisungen verwendet wird, ist mit dem Ausführungszeichensatz identisch. Der Präprozessor erkennt auch negative Zeichenwerte.

Der Präprozessor erkennt die folgenden Direktiven:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Das Nummern Zeichen (`#`) muss das erste nicht-Leerzeichen in der Zeile sein, die die Direktive enthält. Leerzeichen können zwischen dem Nummern Zeichen und dem ersten Buchstaben der Direktive angezeigt werden. Manche Anweisungen enthalten Argumente oder Werte. Jedem Text, der auf eine Direktive folgt (außer einem Argument oder einem Wert, der Teil der Anweisung ist), muss das einzeilige Kommentar Trennzeichen`//`() vorangestellt oder in Kommentar Trennzeichen`/* */`() eingeschlossen werden. Zeilen, die Präprozessordirektiven enthalten, können fortgesetzt werden, indem der zeitzeiendemarker mit`\`einem umgekehrten Schrägstrich () unmittelbar vorangestellt wird.

Präprozessordirektiven können an beliebiger Stelle in einer Quelldatei vorkommen, Sie gelten jedoch nur für den Rest der Quelldatei, nachdem Sie angezeigt wurden.

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)\
[Vordefinierte Makros](../preprocessor/predefined-macros.md)\
[c/c++-präprozessorverweis](../preprocessor/c-cpp-preprocessor-reference.md)
