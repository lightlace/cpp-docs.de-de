---
title: Präprozessoranweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3835d3c3d2900b97c16bc82963df2d08f35a879d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416291"
---
# <a name="preprocessor-directives"></a>Präprozessoranweisungen

Präprozessoranweisungen wie z. B. `#define` und `#ifdef`, werden in der Regel verwendet, einfach und leicht zu kompilieren in verschiedenen ausführungsumgebungen zu vereinfachen. Anweisungen in der Quelldatei weisen den Präprozessor an, bestimmte Aktionen auszuführen. Beispielsweise kann der Präprozessor Token im Text ersetzen, den Inhalt von anderen Dateien in die Quelldatei einfügen oder die Kompilierung eines Teils der Datei unterdrücken, indem er Textabschnitte entfernt. Präprozessorzeilen werden vor der Makroerweiterung erkannt und ausgeführt. Wenn also die Erweiterung eines Makros aussieht wie ein Präprozessorbefehl, wird dieser Befehl nicht vom Präprozessor erkannt.

Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden. Der Zeichensatz, der in Präprozessoranweisungen verwendet wird, ist mit dem Ausführungszeichensatz identisch. Der Präprozessor erkennt auch negative Zeichenwerte.

Der Präprozessor erkennt die folgenden Anweisungen:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Das Nummernzeichen (**#**) müssen werden die ersten Leerstelle in der Zeile mit der Richtlinie; können Leerzeichen zwischen dem Nummernzeichen und dem ersten Buchstaben der Anweisung angezeigt werden. Manche Direktiven enthalten Argumente oder Werte. Jeder Text, der eine Direktive (außer einem Argument oder Wert, der Teil der Direktive ist) folgt muss das einzeilige Kommentartrennzeichen vorangestellt werden (**//**) oder in Kommentartrennzeichen eingeschlossen ( __/ \*\*/__). Zeilen, die präprozessoranweisungen enthalten fortgesetzt werden können, indem unmittelbar vor der End-of-Line-Marker, mit einem umgekehrten Schrägstrich (**\\**).

Präprozessoranweisungen können an beliebiger Stelle in einer Quelldatei auftreten, aber sie gelten nur für den Rest der Quelldatei.

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)<br/>
[Vordefinierte Makros](../preprocessor/predefined-macros.md)<br/>
[C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)  
