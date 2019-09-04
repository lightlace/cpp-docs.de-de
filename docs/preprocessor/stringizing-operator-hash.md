---
title: Zeichenfolgenoperator (#)
ms.date: 08/29/2019
f1_keywords:
- '#'
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
ms.openlocfilehash: 5a1b43198e59bc1e69cdf1b56db56be75719fe46
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216549"
---
# <a name="stringizing-operator-"></a>Zeichenfolgenoperator (#)

Der Zahlen-und Zeichen folgen Operator ( **#** ) konvertiert Makro Parameter in Zeichenfolgenliterale, ohne die Parameterdefinition zu erweitern. Sie wird nur mit Makros verwendet, die Argumente annehmen. Wenn er einem formalen Parameter in der Makrodefinition voransteht, ist das tatsächliche Argument, das vom Makroaufruf übergeben wird, in Anführungszeichen eingeschlossen und wird als Zeichenfolgenliteral behandelt. Das Zeichenfolgenliteral ersetzt dann jedes Vorkommen einer Kombination des Zeichenfolgenoperators und des formalen Parameters innerhalb der Makrodefinition.

> [!NOTE]
> Die Erweiterung von Microsoft C (Version 6.0 und früher) für den ANSI C-Standard, die bisher formale Makroargumente in Zeichenfolgenliteralen und Zeichenkonstanten erweiterte, wird nicht mehr unterstützt. Code, der auf diese Erweiterung angewiesen war, sollte mit dem Zeichen folgen Operator **#** () neu geschrieben werden.

Leerraum, der dem ersten Token vorangestellt ist und dem letzten Token des tatsächlichen Arguments folgt, wird ignoriert. Jedes Leerzeichen zwischen den Token im tatsächlichen Argumente wird im resultierenden Zeichenfolgenliteral auf ein einzelnes Leerzeichen reduziert. Wenn also ein Kommentar zwischen zwei Token im eigentlichen Argument auftritt, wird er auf einen einzelnen Leerraum reduziert. Das resultierende Zeichenfolgenliteralzeichen wird automatisch mit allen angrenzenden Zeichenfolgenliteralen verkettet, die nur durch Leerraum getrennt sind.

Wenn ein im Argument enthaltenes Zeichen in der Regel eine Escapesequenz erfordert, wenn es in einem Zeichenfolgenliteralzeichen verwendet wird, z`\`. b. das Anführungszeichen (`"`) oder umgekehrter Schrägstrich (), wird automatisch der erforderliche Escapezeichen vor dem-Zeichen eingefügt.

Der Microsoft C++ -Zeichen folgen Operator verhält sich nicht korrekt, wenn er mit Zeichen folgen verwendet wird, die Escapesequenzen enthalten. In dieser Situation generiert der Compiler den [Compilerfehler C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt eine Makro Definition, die den Zeichen folgen Operator und eine Main-Funktion enthält, die das-Makro aufruft:

```cpp
// stringizer.cpp
#include <stdio.h>
#define stringer( x ) printf_s( #x "\n" )
int main() {
   stringer( In quotes in the printf function call );
   stringer( "In quotes when printed to the screen" );
   stringer( "This: \"  prints an escaped double quote" );
}
```

Die `stringer` Makros werden während der Vorverarbeitung erweitert und erzeugen den folgenden Code:

```cpp
int main() {
   printf_s( "In quotes in the printf function call" "\n" );
   printf_s( "\"In quotes when printed to the screen\"" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

```Output
In quotes in the printf function call
"In quotes when printed to the screen"
"This: \"  prints an escaped double quote"
```

Das folgende Beispiel zeigt, wie ein Makroparameter erweitert werden kann:

```cpp
// stringizer_2.cpp
// compile with: /E
#define F abc
#define B def
#define FB(arg) #arg
#define FB1(arg) FB(arg)
FB(F B)
FB1(F B)
```

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)
