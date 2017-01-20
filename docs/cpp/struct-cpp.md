---
title: "struct (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "struct"
  - "struct_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Strukturkonstruktoren"
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# struct (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `struct`\-Schlüsselwort definiert einen Strukturtyp und\/oder eine Variable eines Strukturtyps.  
  
## Syntax  
  
```  
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### Parameter  
 `template-spec`  
 Optionale Vorlagenspezifikationen.  Weitere Informationen finden Sie unter [Vorlagenspezifikationen](../Topic/Template%20Specifications.md).  
  
 `struct`  
 Das `struct`\-Schlüsselwort.  
  
 `ms-decl-spec`  
 Optionale Speicherklassenspezifikation.  Weitere Informationen finden Sie im Zusammenhang mit dem [\_\_declspec](../cpp/declspec.md)\-Schlüsselwort.  
  
 `tag`  
 Der Typname, der für die Struktur angegeben wurde.  Das Tag wird ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Struktur.  Das Tag ist optional.  Wenn es nicht angegeben wird, wird eine anonyme Struktur definiert.  Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Optionale Liste von Klassen oder Strukturen, von denen diese Struktur ihre Member ableitet.  Weitere Informationen finden Sie unter [Basisklassen](../cpp/base-classes.md).  Jedem Basisklassen\- oder Strukturnamen kann ein Zugriffsspezifizierer \([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md)\) und das [virtual](../cpp/virtual-cpp.md)\-Schlüsselwort vorangestellt werden.  Weitere Informationen finden Sie in der Memberzugriffstabelle unter [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md).  
  
 `member-list`  
 Liste der Strukturmember.  Weitere Informationen finden Sie unter [Übersicht über Klassenmember](../cpp/class-member-overview.md).  Der einzige Unterschied besteht darin, dass `struct` anstelle von `class` verwendet wird.  
  
 `declarators`  
 Deklaratorliste, die die Namen der Klasse angibt.  Deklaratorlisten deklarieren eine oder mehrere Instanzen des Strukturtyps.  Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Klasse `public` sind.  Initialisierungslisten werden häufig in Strukturen verwendet, da Datenmember standardmäßig `public` sind.  Weitere Informationen finden Sie unter [Übersicht über Deklaratoren](../cpp/overview-of-declarators.md).  
  
## Hinweise  
 Ein Strukturtyp ist ein benutzerdefinierter zusammengesetzter Typ.  Er setzt sich aus Feldern oder Membern zusammen, die unterschiedliche Typen aufweisen können.  
  
 In C\+\+ ist eine Struktur identisch mit einer Klasse, mit der Ausnahme, dass die Member standardmäßig `public` sind.  
  
 Weitere Informationen über verwaltete Klassen und Strukturen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Verwenden einer Struktur  
 In C müssen Sie explizit das `struct`\-Schlüsselwort verwenden, um eine Struktur zu deklarieren.  In C\+\+ müssen Sie das `struct`\-Schlüsselwort nicht verwenden, nachdem der Typ definiert wurde.  
  
 Sie können Variablen deklarieren, wenn der Strukturtyp so definiert wurde, dass mindestens ein durch Trennzeichen getrennter Variablenname zwischen schließender Klammer und Semikolon steht.  
  
 Strukturvariablen können initialisiert werden.  Die Initialisierung für jede Variable muss in Klammern eingeschlossen sein.  
  
 Weitere Informationen finden Sie unter [Klasse](../cpp/class-cpp.md), [Union](../cpp/unions.md) und [Enumeration](../cpp/enumerations-cpp.md).  
  
## Beispiel  
  
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
  
## Siehe auch  
 [\(NOTINBUILD\) Defining Class Types](assetId:///e8c65425-0f3a-4dca-afc2-418c3b1e57da)