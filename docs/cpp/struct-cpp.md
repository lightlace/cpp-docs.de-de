---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: e9ffd30dd0017e912fd7c196e2d3f0e987fb0810
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780859"
---
# <a name="struct-c"></a>struct (C++)

Die **Struktur** -Schlüsselwort definiert einen Strukturtyp und/oder eine Variable eines Strukturtyps.

## <a name="syntax"></a>Syntax

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>Parameter

*template-spec*<br/>
Optionale Vorlagenspezifikationen. Weitere Informationen finden Sie unter [Vorlagenspezifikationen](templates-cpp.md).

*struct*<br/>
Die **Struktur** Schlüsselwort.

*ms-decl-spec*<br/>
Optionale Speicherklassenspezifikation. Weitere Informationen finden Sie in der [__declspec](../cpp/declspec.md) Schlüsselwort.

*tag*<br/>
Der Typname, der für die Struktur angegeben wurde. Das Tag wird ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Struktur. Das Tag ist optional. Wenn es nicht angegeben wird, wird eine anonyme Struktur definiert. Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).

*base-list*<br/>
Optionale Liste von Klassen oder Strukturen, von denen diese Struktur ihre Member ableitet. Finden Sie unter [Basisklassen](../cpp/base-classes.md) für Weitere Informationen. Jede Klasse oder Struktur Basisnamen kann einen Zugriffsspezifizierer vorangestellt werden ([öffentliche](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md)) und die [virtuellen](../cpp/virtual-cpp.md) Schlüsselwort. Finden Sie in der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) für Weitere Informationen.

*member-list*<br/>
Liste der Strukturmember. Finden Sie unter [Member-Klassenübersicht](../cpp/class-member-overview.md) für Weitere Informationen. Der einzige Unterschied besteht darin, die **Struktur** dient anstelle von **Klasse**.

*Deklaratoren*<br/>
Deklaratorliste, die die Namen der Struktur angibt. Deklaratorlisten deklarieren eine oder mehrere Instanzen des Strukturtyps. Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Struktur sind **öffentliche**. Initialisierungslisten werden häufig in Strukturen, da der Datenmember sind **öffentliche** standardmäßig.  Finden Sie unter [Übersicht von Deklaratoren](../cpp/overview-of-declarators.md) für Weitere Informationen.

## <a name="remarks"></a>Hinweise

Ein Strukturtyp ist ein benutzerdefinierter zusammengesetzter Typ. Er setzt sich aus Feldern oder Membern zusammen, die unterschiedliche Typen aufweisen können.

In C++ ist eine Struktur ist identisch mit einer Klasse mit dem Unterschied, dass die Member werden **öffentliche** standardmäßig.

Informationen über verwaltete Klassen und strukte in C++ / CLI finden Sie unter [Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="using-a-structure"></a>Verwenden einer Struktur

In C müssen Sie explizit verwenden die **Struktur** Schlüsselwort, um eine Struktur zu deklarieren. In C++, Sie ist nicht erforderlich, verwenden die **Struktur** Schlüsselwort, nachdem der Typ definiert wurde.

Sie können Variablen deklarieren, wenn der Strukturtyp so definiert wurde, dass mindestens ein durch Trennzeichen getrennter Variablenname zwischen schließender Klammer und Semikolon steht.

Strukturvariablen können initialisiert werden. Die Initialisierung für jede Variable muss in Klammern eingeschlossen sein.

Weitere Informationen finden Sie unter [Klasse](../cpp/class-cpp.md), [Union](../cpp/unions.md), und [Enum](../cpp/enumerations-cpp.md).

## <a name="example"></a>Beispiel

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
