---
title: Bezeichner (C++)
ms.date: 09/12/2018
helpviewer_keywords:
- decorated names
- decorated names, about decorated names
- identifiers, C++
- white space, in C++ identifiers
- identifiers [C++]
ms.assetid: 03a0dfb1-4530-4cdf-8295-5ea4dca4c1b8
ms.openlocfilehash: 6f87486d0bb2614a3b2542cf050172a47f152c4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184600"
---
# <a name="identifiers-c"></a>Bezeichner (C++)

Ein Bezeichner ist eine Folge von Zeichen zur Angabe folgender Elemente:

- Objekt- oder Variablenname

- Klassen-, Struktur- oder Unionsname

- Name des enumerierten Typs

- Member einer Klasse, Struktur, Union oder Enumeration

- Funktion oder Klassenmemberfunktion

- typedef-Name

- Bezeichnungsname

- Makroname

- Makroparameter

Die folgenden Zeichen sind als beliebiges Zeichen eines Bezeichners zulässig:

```
_ a b c d e f g h i j k l m
n o p q r s t u v w x y z
A B C D E F G H I J K L M
N O P Q R S T U V W X Y Z
```

Bestimmte Bereiche von universellen Zeichennamen sind ebenfalls in einem Bezeichner zulässig.  Ein universeller Zeichenname in einem Bezeichner darf weder ein Steuerzeichen noch ein Zeichen im grundlegenden Quellzeichensatz darstellen. Weitere Informationen finden Sie unter [Character Sets](../cpp/character-sets.md). Diese Unicode-Codepunkt-Zahlenbereiche sind als universelle Zeichennamen für ein beliebiges Zeichen in einem Bezeichner zulässig:

- 00A8, 00AA, 00AD, 00AF, 00B2-00B5, 00B7-00BA, 00BC-00BE, 00C0-00D6, 00D8-00F6, 00F8-00FF, 0100-02FF, 0370-167F, 1681-180D, 180F-1DBF, 1E00-1FFF, 200B-200D, 202A-202E, 203F-2040, 2054, 2060-206F, 2070-20CF, 2100-218F, 2460-24FF, 2776-2793, 2C00-2DFF, 2E80-2FFF, 3004-3007, 3021-302F, 3031-303F, 3040-D7FF, F900-FD3D, FD40-FDCF, FDF0-FE1F, FE30-FE44, FE47-FFFD, 10000-1FFFD, 20000-2FFFD, 30000-3FFFD, 40000-4FFFD, 50000-5FFFD, 60000-6FFFD, 70000-7FFFD, 80000-8FFFD, 90000-9FFFD, A0000-AFFFD, B0000-BFFFD, C0000-CFFFD, D0000-DFFFD, E0000-EFFFD

Die folgenden Zeichen können als beliebiges Zeichen in einem Bezeichner verwendet werden, außer als erstes Zeichen:

```
0 1 2 3 4 5 6 7 8 9
```

Diese Unicode-Codepunkt-Zahlenbereiche sind, mit Ausnahme des ersten, ebenfalls als universelle Zeichennamen für ein beliebiges Zeichen in einem Bezeichner zulässig:

- 0300-036F, 1DC0-1DFF, 20D0-20FF, FE20-FE2F

**Microsoft-spezifisch**

Nur die ersten 2048 Zeichen aus Microsoft C++-Bezeichnern sind signifikant. Namen für benutzerdefinierte Typen werden vom Compiler "ergänzt", damit die Typinformationen beibehalten werden. Der resultierende Name, einschließlich der Typinformationen, darf nicht länger als 2048 Zeichen sein. (Finden Sie unter [ergänzte Namen](../build/reference/decorated-names.md) für Weitere Informationen.) Folgende Faktoren können die Länge eines ergänzten Bezeichners beeinflussen:

- Gibt an, ob der Bezeichner ein Objekt eines benutzerdefinierten Typs angibt oder einen von einem benutzerdefinierten Typ abgeleiteten Typ.

- Gibt an, ob der Bezeichner eine Funktion angibt oder einen von einer Funktion abgeleiteten Typ.

- Die Anzahl von Argumenten für eine Funktion.

Das Dollarzeichen `$` ist ein gültiges Bezeichnerzeichen in Visual C++. In Visual C++ können Sie die tatsächlichen Zeichen, die durch die zulässigen Bereiche der universellen Zeichennamen dargestellt sind, in Bezeichnern verwenden. Damit Sie diese Zeichen verwenden können, müssen Sie die Datei speichern, indem Sie eine Dateicodierungs-Codepage verwenden, die die Zeichen enthält.  In diesem Beispiel wird gezeigt, wie Sie sowohl erweiterte Zeichen als auch universelle Zeichennamen austauschbar in Ihrem Code verwenden können.

```cpp
// extended_identifier.cpp
// In Visual Studio, use File, Advanced Save Options to set
// the file encoding to Unicode codepage 1200
struct テスト         // Japanese 'test'
{
    void トスト() {}  // Japanese 'toast'
};

int main() {
    テスト \u30D1\u30F3;  // Japanese パン 'bread' in UCN form
    パン.トスト();        // compiler recognizes UCN or literal form
}
```

Der Bereich der in einem Bezeichner zulässigen Zeichen ist weniger restriktiv, wenn C++ /CLI-Code kompiliert wird. Im Code mit/CLR kompiliert entsprechen [Standard ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

**Ende Microsoft-spezifisch**

Das erste Zeichen eines Bezeichners muss ein Buchstabe des Alphabets (Großbuchstabe oder Kleinbuchstabe) oder ein Unterstrich ( **_** ) sein. Da bei C++-Bezeichnern die Groß- und Kleinschreibung berücksichtigt wird, unterscheidet sich `fileName` von `FileName`.

Für Bezeichner muss eine andere Schreibweise gewählt werden als für Schlüsselwörter. Bezeichner, die Schlüsselwörter enthalten, sind gültig. Z. B. `Pint` ist ein gültiger Bezeichner, obwohl er enthält **Int**, dies ist ein Schlüsselwort.

Verwendung von zwei aufeinander folgenden unterstrichen ( **__** ) in einen Bezeichner oder eines einzelnen vorangestellten Unterstrichs, gefolgt von einem Großbuchstaben beginnen, ist für die reserviert C++ Implementierungen in allen Bereichen. Sie sollten es vermeiden, einen einzelnen vorangestellten Unterstrich gefolgt von einem Kleinbuchstaben für Dateibereiche zu verwenden, da Konflikte mit aktuellen oder zukünftigen reservierten Bezeichnern auftreten können.

## <a name="see-also"></a>Siehe auch

[Lexikalische Konventionen](../cpp/lexical-conventions.md)
