---
title: Makros (C/C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf97e61e68cd02891c738db5de8820924957fc56
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065472"
---
# <a name="macros-cc"></a>Makros (C/C++)
Vorverarbeitung erweitert Makros in allen Zeilen, die keine Präprozessordirektiven sind (Zeilen, die keine **#** als erstes Zeichen ohne Leerzeichen) und in Teilen einiger Direktiven, die nicht als Teil des übersprungen werden ein für die bedingte Kompilierung. "Direktiven für die bedingte Kompilierung" ermöglichen es Ihnen, die Kompilierung von Teilen einer Quelldatei zu unterdrücken, indem sie einen konstanten Ausdruck oder einen Bezeichner testen, um zu bestimmen, welche Textblöcke an den Compiler übergeben werden und welche Textblöcke während des Präprozessorlaufs aus der Quelldatei entfernt werden .

Die `#define`-Anweisung wird normalerweise verwendet, um aussagekräftige Bezeichner Konstanten, Schlüsselwörtern und häufig verwendeten Anweisungen oder Ausdrücken zuzuordnen. Bezeichner, die Konstanten darstellen, werden manchmal als "symbolische Konstanten "oder" Manifestkonstanten" bezeichnet. Bezeichner, die Anweisungen oder Ausdrücke darstellen, werden als "Makros" bezeichnet. In dieser Präprozessordokumentation wird nur der Begriff "Makro" verwendet.

Wenn der Name des Makros im Programmquelltext oder in den Argumenten von bestimmten anderen Präprozessorbefehlen erkannt wird, wird er als Aufruf dieses Makros behandelt. Der Makroname wird durch eine Kopie des Makrotexts ersetzt. Wenn das Makro Argumente akzeptiert, werden die tatsächlichen Argumente nach dem Makronamen durch formale Parameter im Makrotext ersetzt. Der Prozess des Ersetzens eines Makroaufrufs durch die verarbeitete Textkopie wird als "Erweiterung" des Makroaufrufs bezeichnet.

Praktisch gibt es zwei Arten von Makros. "Object-like"-Makros akzeptieren keine Argumente, während "function-like"-Makros definiert werden können, um Argumente zu akzeptieren, damit sie wie Funktionsaufrufe aussehen und wie solche reagieren. Da Makros keine tatsächlichen Funktionsaufrufe generieren, können Sie manchmal erreichen, dass Programme schneller ausgeführt werden, indem Sie Funktionsaufrufe durch Makros ersetzen. (In C++ sind Inlinefunktionen häufig eine bevorzugte Methode.) Makros können jedoch Probleme verursachen, wenn Sie sie nicht sorgfältig definieren und verwenden. Möglicherweise müssen Sie Klammern bei Makrodefinitionen mit Argumenten verwenden, um die gewünschte Rangfolge in einem Ausdruck zu erhalten. Makros behandeln außerdem Ausdrücke mit Nebeneffekte möglicherweise nicht ordnungsgemäß. Finden Sie unter den `getrandom` Beispiel [der #define-Anweisung](../preprocessor/hash-define-directive-c-cpp.md) für Weitere Informationen.

Sobald Sie ein Makro definiert haben, können Sie es nicht mit einem anderen Wert neu definieren, ohne zuerst die ursprüngliche Definition zu entfernen. Sie können jedoch das Makro mit genau derselben Definition neu definieren. Daher kann dieselbe Definition in einem Programm mehrmals vorkommen.

Die `#undef` -Anweisung entfernt die Definition eines Makros. Sobald Sie die Definition entfernt haben, können Sie das Makro mit einem anderen Wert neu definieren. [Die #define-Anweisung](../preprocessor/hash-define-directive-c-cpp.md) und [#undef-Direktive](../preprocessor/hash-undef-directive-c-cpp.md) erläutern die `#define` und `#undef` Anweisungen bzw.

Weitere Informationen finden Sie unter

- [Makros und C++](../preprocessor/macros-and-cpp.md)

- [Variadic-Makros](../preprocessor/variadic-macros.md)

- [Vordefinierte Makros](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>Siehe auch

[C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)