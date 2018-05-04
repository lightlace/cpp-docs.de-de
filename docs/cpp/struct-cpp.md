---
title: Struktur (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- struct_cpp
dev_langs:
- C++
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9ea6bea20ad1591db9b07507b4db959d10a318
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="struct-c"></a>struct (C++)
Das `struct`-Schlüsselwort definiert einen Strukturtyp und/oder eine Variable eines Strukturtyps.  
  
## <a name="syntax"></a>Syntax  
  
```  
[template-spec] struct[ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### <a name="parameters"></a>Parameter  
 `template-spec`  
 Optionale Vorlagenspezifikationen. Weitere Informationen finden Sie unter [Vorlagenspezifikationen](templates-cpp.md).  
  
 `struct`  
 Das `struct`-Schlüsselwort.  
  
 `ms-decl-spec`  
 Optionale Speicherklassenspezifikation. Weitere Informationen finden Sie unter der [__declspec](../cpp/declspec.md) Schlüsselwort.  
  
 `tag`  
 Der Typname, der für die Struktur angegeben wurde. Das Tag wird ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Struktur. Das Tag ist optional. Wenn es nicht angegeben wird, wird eine anonyme Struktur definiert. Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Optionale Liste von Klassen oder Strukturen, von denen diese Struktur ihre Member ableitet. Finden Sie unter [Basisklassen](../cpp/base-classes.md) für Weitere Informationen. Jede Klasse oder Struktur Basisnamen kann einen Zugriffsspezifizierer vorangestellt werden ([öffentlichen](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md)) und die [virtuellen](../cpp/virtual-cpp.md) Schlüsselwort. Finden Sie in der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) für Weitere Informationen.  
  
 `member-list`  
 Liste der Strukturmember. Verweisen auf [Member Klassenüberblick](../cpp/class-member-overview.md) für Weitere Informationen. Der einzige Unterschied besteht darin, dass `struct` anstelle von `class` verwendet wird.  
  
 `declarators`  
 Deklaratorliste, die die Namen der Klasse angibt. Deklaratorlisten deklarieren eine oder mehrere Instanzen des Strukturtyps. Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Klasse `public` sind. Initialisierungslisten werden häufig in Strukturen verwendet, da Datenmember standardmäßig `public` sind.  Finden Sie unter [Übersicht von Deklaratoren](../cpp/overview-of-declarators.md) für Weitere Informationen.  
  
## <a name="remarks"></a>Hinweise  
 Ein Strukturtyp ist ein benutzerdefinierter zusammengesetzter Typ. Er setzt sich aus Feldern oder Membern zusammen, die unterschiedliche Typen aufweisen können.  
  
 In C++ ist eine Struktur identisch mit einer Klasse, mit der Ausnahme, dass die Member standardmäßig `public` sind.  
  
 Informationen über verwaltete Klassen und Strukturen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="using-a-structure"></a>Verwenden einer Struktur  
 In C müssen Sie explizit das `struct`-Schlüsselwort verwenden, um eine Struktur zu deklarieren. In C++ müssen Sie das `struct`-Schlüsselwort nicht verwenden, nachdem der Typ definiert wurde.  
  
 Sie können Variablen deklarieren, wenn der Strukturtyp so definiert wurde, dass mindestens ein durch Trennzeichen getrennter Variablenname zwischen schließender Klammer und Semikolon steht.  
  
 Strukturvariablen können initialisiert werden. Die Initialisierung für jede Variable muss in Klammern eingeschlossen sein.  
  
 Weitere Informationen finden Sie unter [Klasse](../cpp/class-cpp.md), [Union](../cpp/unions.md), und [Enum](../cpp/enumerations-cpp.md).  
  
## <a name="example"></a>Beispiel  
  
```  
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
  
