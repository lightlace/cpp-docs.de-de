---
title: Präprozessordirektiven
ms.date: 06/28/2018
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 9481e977f2afb3de27a74278893a217fde48044b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179970"
---
# <a name="preprocessor-directives"></a>Präprozessordirektiven

Präprozessoranweisungen wie z. B. `#define` und `#ifdef`, werden in der Regel verwendet, einfach und leicht zu kompilieren in verschiedenen ausführungsumgebungen zu vereinfachen. Anweisungen in der Quelldatei weisen den Präprozessor an, bestimmte Aktionen auszuführen. Beispielsweise kann der Präprozessor Token im Text ersetzen, den Inhalt von anderen Dateien in die Quelldatei einfügen oder die Kompilierung eines Teils der Datei unterdrücken, indem er Textabschnitte entfernt. Präprozessorzeilen werden vor der Makroerweiterung erkannt und ausgeführt. Wenn also die Erweiterung eines Makros aussieht wie ein Präprozessorbefehl, wird dieser Befehl nicht vom Präprozessor erkannt.

Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden. Der Zeichensatz, der in Präprozessoranweisungen verwendet wird, ist mit dem Ausführungszeichensatz identisch. Der Präprozessor erkennt auch negative Zeichenwerte.

Der Präprozessor erkennt die folgenden Direktiven:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Das Nummernzeichen (**#**) müssen werden die ersten Leerstelle in der Zeile mit der Richtlinie; können Leerzeichen zwischen dem Nummernzeichen und dem ersten Buchstaben der Anweisung angezeigt werden. Manche Anweisungen enthalten Argumente oder Werte. Jeder Text, der eine Direktive (außer einem Argument oder Wert, der Teil der Direktive ist) folgt muss das einzeilige Kommentartrennzeichen vorangestellt werden (**//**) oder in Kommentartrennzeichen eingeschlossen ( __/ \*\*/__). Zeilen, die präprozessoranweisungen enthalten fortgesetzt werden können, indem unmittelbar vor der End-of-Line-Marker, mit einem umgekehrten Schrägstrich (**\\**).

Präprozessoranweisungen können an beliebiger Stelle in einer Quelldatei auftreten, aber sie gelten nur für den Rest der Quelldatei.

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)<br/>
[Vordefinierte Makros](../preprocessor/predefined-macros.md)<br/>
[C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)
