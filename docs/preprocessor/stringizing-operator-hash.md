---
title: Zeichenfolgenoperator (#)
ms.date: 11/04/2016
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
ms.openlocfilehash: d90d07c8f3cce6c443be0eb994db494746c00fcc
ms.sourcegitcommit: 40ffe764244784c715b086c79626ac390b855d47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "68711142"
---
# <a name="stringizing-operator-"></a>Zeichenfolgenoperator (#)

Der Zahlen-und Zeichen folgen Operator ( **#** ) konvertiert Makro Parameter in Zeichenfolgenliterale, ohne die Parameterdefinition zu erweitern. Er wird nur mit Makros verwendet, die Argumente akzeptieren. Wenn er einem formalen Parameter in der Makrodefinition voransteht, ist das tatsächliche Argument, das vom Makroaufruf übergeben wird, in Anführungszeichen eingeschlossen und wird als Zeichenfolgenliteral behandelt. Das Zeichenfolgenliteral ersetzt dann jedes Vorkommen einer Kombination des Zeichenfolgenoperators und des formalen Parameters innerhalb der Makrodefinition.

> [!NOTE]
> Die Erweiterung von Microsoft C (Version 6.0 und früher) für den ANSI C-Standard, die bisher formale Makroargumente in Zeichenfolgenliteralen und Zeichenkonstanten erweiterte, wird nicht mehr unterstützt. Code, der auf diese Erweiterung angewiesen war, sollte mit dem Zeichen folgen Operator **#** () neu geschrieben werden.

Das Leerzeichen vor dem ersten Token des tatsächlichen Arguments und nach dem letzten Token des tatsächlichen Arguments wird ignoriert. Jedes Leerzeichen zwischen den Token im tatsächlichen Argumente wird im resultierenden Zeichenfolgenliteral auf ein einzelnes Leerzeichen reduziert. Wenn also ein Kommentar zwischen zwei Token im tatsächlichen Argument auftritt, wird das Leerzeichen auf einen einzelnes Leerzeichen reduziert. Das sich ergebende Zeichenfolgenliteral wird automatisch mit allen angrenzenden Zeichenfolgenliteralen verkettet, von denen es nur durch ein Leerzeichen getrennt ist.

Wenn ein im-Argument enthaltenes Zeichen in der Regel eine Escapesequenz erfordert, wenn es in einem Zeichenfolgenliteralzeichen (z. b **\\** . das Anführungszeichen ( **"** ) oder umgekehrter Schrägstrich ()) verwendet wird, wird automatisch der erforderliche Escapezeichen vor dem Zeichen.

Der visuelle C++ Zeichen folgen Operator verhält sich nicht ordnungsgemäß, wenn er mit Zeichen folgen verwendet wird, die Escapesequenzen einschließen. In dieser Situation generiert der Compiler den [Compilerfehler C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md).

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt eine Makrodefinition, welche den Zeichenfolgenoperator und eine Hauptfunktion umfasst, die das Makro aufruft:

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
