---
title: Makros (C/C++)
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
ms.openlocfilehash: ba2c0f012974a528876219d00c61c0f31a6cd820
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218862"
---
# <a name="macros-cc"></a>Makros (C/C++)

Der Präprozessor erweitert Makros in allen Zeilen mit Ausnahme von *Präprozessordirektiven*, **#** Zeilen, die als erstes nicht-Leerzeichen enthalten. Es erweitert Makros in Teilen einiger Direktiven, die nicht im Rahmen einer bedingten Kompilierung übersprungen werden. *Bedingte Kompilierungs Direktiven* ermöglichen es Ihnen, die Kompilierung von Teilen einer Quelldatei zu unterdrücken. Sie testen einen konstanten Ausdruck oder Bezeichner, um zu bestimmen, welche Textblöcke an den Compiler übergeben werden sollen und welche aus der Quelldatei bei der Vorverarbeitung entfernt werden sollen.

Die `#define`-Direktive wird normalerweise verwendet, um aussagekräftige Bezeichner Konstanten, Schlüsselwörtern und häufig verwendeten Anweisungen oder Ausdrücken zuzuordnen. Bezeichner, die Konstanten darstellen, werden mitunter als *symbolische Konstanten* oder *Manifest-Konstanten*bezeichnet. Bezeichner, die-Anweisungen oder-Ausdrücke darstellen, werden als *Makros*bezeichnet. In dieser Präprozessordokumentation wird nur der Begriff "Makro" verwendet.

Wenn der Name eines Makros im Programm Quelltext oder in den Argumenten bestimmter anderer Präprozessorbefehle erkannt wird, wird er als ein Aufrufvorgang dieses Makros behandelt. Der Makroname wird durch eine Kopie des Makrotexts ersetzt. Wenn das Makro Argumente akzeptiert, werden die tatsächlichen Argumente nach dem Makronamen durch formale Parameter im Makrotext ersetzt. Der Prozess des Ersetzens eines Makro Aufrufs mit der verarbeiteten Kopie des Texts wird als *Erweiterung* des Makro Aufrufs bezeichnet.

Praktisch gibt es zwei Arten von Makros. *Objektähnliche* Makros akzeptieren keine Argumente. *Funktions ähnliche* Makros können so definiert werden, dass Sie Argumente akzeptieren, damit Sie wie Funktionsaufrufe Aussehen und agieren. Da Makros keine tatsächlichen Funktionsaufrufe generieren, können Sie die Programme manchmal schneller ausführen, indem Sie Funktionsaufrufe durch Makros ersetzen. (In C++ sind Inlinefunktionen häufig eine bevorzugte Methode.) Makros können jedoch Probleme verursachen, wenn Sie Sie nicht mit Bedacht definieren und verwenden. Möglicherweise müssen Sie Klammern bei Makrodefinitionen mit Argumenten verwenden, um die gewünschte Rangfolge in einem Ausdruck zu erhalten. Makros behandeln außerdem Ausdrücke mit Nebeneffekte möglicherweise nicht ordnungsgemäß. Weitere Informationen finden `getrandom` Sie im Beispiel in [der #define-Direktive](../preprocessor/hash-define-directive-c-cpp.md).

Nachdem Sie ein Makro definiert haben, können Sie es nicht mehr mit einem anderen Wert neu definieren, ohne zuerst die ursprüngliche Definition zu entfernen. Sie können jedoch das Makro mit genau derselben Definition neu definieren. Daher kann die gleiche Definition mehrmals in einem Programm vorkommen.

Die `#undef` -Direktive entfernt die Definition eines Makros. Nachdem Sie die Definition entfernt haben, können Sie das Makro mit einem anderen Wert neu definieren. [Die #define-Direktive](../preprocessor/hash-define-directive-c-cpp.md) und [die #undef](../preprocessor/hash-undef-directive-c-cpp.md) - `#define` Direktive erörtern die-und- `#undef` Direktiven.

Weitere Informationen finden Sie unter

- [Makros und C++](../preprocessor/macros-and-cpp.md)

- [Variadic-Makros](../preprocessor/variadic-macros.md)

- [Vordefinierte Makros](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>Siehe auch

[C/C++ präprozessorverweis](../preprocessor/c-cpp-preprocessor-reference.md)
