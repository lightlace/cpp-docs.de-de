---
title: Analysieren von C++-Befehlszeilenargumenten
ms.date: 11/04/2016
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
ms.openlocfilehash: 53873fa9340253ab5e8459eb442385641246f930
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396118"
---
# <a name="parsing-c-command-line-arguments"></a>Analysieren von C++-Befehlszeilenargumenten

**Microsoft-spezifisch**

Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der Microsoft C/C++-Startcode die folgenden Regeln:

- Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.

- Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem vollständig verarbeitet, bevor es an das `argv`-Array im Programm übergeben wird.

- Eine Zeichenfolge, umgeben von doppelten Anführungszeichen ("*Zeichenfolge*") wird als ein einzelnes Argument, enthaltenen Leerräume interpretiert. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.

- Wenn dem Anführungszeichen ein umgekehrter Schrägstrich (\\") vorangestellt wird, wird diese Zeichenfolge als literales Anführungszeichen (") interpretiert.

- Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.

- Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das doppelte Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.

- Wenn auf eine ungerade Anzahl umgekehrter Schrägstriche ein doppeltes Anführungszeichen folgt, wird für jedes Paar von umgekehrten Schrägstrichen ein umgekehrter Schrägstrich in das `argv`-Array eingefügt, und das doppelte Anführungszeichen wird vom verbleibenden umgekehrten Schrägstrich mit einem Escapezeichen versehen, sodass ein echtes doppeltes Anführungszeichen (") in `argv` eingefügt wird.

## <a name="example"></a>Beispiel

Das folgende Programm zeigt, wie Befehlszeilenargumente übergeben werden:

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

Die folgende Tabelle zeigt beispielhafte Eingaben und zu erwartende Ausgaben, wobei die Regeln in der vorangehenden Liste aufgezeigt werden.

### <a name="results-of-parsing-command-lines"></a>Ergebnisse der Analyse von Befehlszeilen

|Befehlszeileneingabe|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)