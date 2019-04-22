---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: c4ef9690a41737147354ee0976f6912c4711ff67
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774814"
---
# <a name="class-c"></a>class (C++)

Die **Klasse** -Schlüsselwort deklariert einen Klassentyp oder definiert ein Objekt eines Klassentyps.

## <a name="syntax"></a>Syntax

```
[template-spec]
class [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[ class ] tag declarators;
```

#### <a name="parameters"></a>Parameter

*template-spec*<br/>
Optionale Vorlagenspezifikationen. Weitere Informationen finden Sie unter [Vorlagen](templates-cpp.md).

*class*<br/>
Die **Klasse** Schlüsselwort.

*ms-decl-spec*<br/>
Optionale Speicherklassenspezifikation. Weitere Informationen finden Sie in der [__declspec](../cpp/declspec.md) Schlüsselwort.

*tag*<br/>
Der Typname, der für die Klasse angegeben wurde. Das Tag ist ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Klasse. Das Tag ist optional. Wenn es nicht angegeben wird, wird eine anonyme Klasse definiert. Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).

*base-list*<br/>
Optionale Liste von Klassen oder Strukturen, von denen diese Klasse ihre Member ableitet. Finden Sie unter [Basisklassen](../cpp/base-classes.md) für Weitere Informationen. Jede Klasse oder Struktur Basisnamen kann einen Zugriffsspezifizierer vorangestellt werden ([öffentliche](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md)) und die [virtuellen](../cpp/virtual-cpp.md) Schlüsselwort. Finden Sie in der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) für Weitere Informationen.

*member-list*<br/>
Liste von Klassenmembern. Finden Sie unter [Member-Klassenübersicht](../cpp/class-member-overview.md) für Weitere Informationen.

*Deklaratoren*<br/>
Deklaratorliste, die die Namen von mindestens einer Instanz eines Klassentyps festlegt. Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Klasse sind **öffentliche**. Dies ist häufiger in Strukturen, deren Datenmember sind **öffentliche** standardmäßig als in Klassen. Finden Sie unter [Übersicht von Deklaratoren](../cpp/overview-of-declarators.md) für Weitere Informationen.

## <a name="remarks"></a>Hinweise

Weitere Informationen zu Klassen im Allgemeinen finden Sie in einem der folgenden Themen:

- [struct](../cpp/struct-cpp.md)

- [union](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

Informationen über verwaltete Klassen und strukte in C++ / CLI und C++ / CX, finden Sie unter [Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md)

## <a name="example"></a>Beispiel

```cpp
// class.cpp
// compile with: /EHsc
// Example of the class keyword
// Exhibits polymorphism/virtual functions.

#include <iostream>
#include <string>
#define TRUE = 1
using namespace std;

class dog
{
public:
   dog()
   {
      _legs = 4;
      _bark = true;
   }

   void setDogSize(string dogSize)
   {
      _dogSize = dogSize;
   }
   virtual void setEars(string type)      // virtual function
   {
      _earType = type;
   }

private:
   string _dogSize, _earType;
   int _legs;
   bool _bark;

};

class breed : public dog
{
public:
   breed( string color, string size)
   {
      _color = color;
      setDogSize(size);
   }

   string getColor()
   {
      return _color;
   }

   // virtual function redefined
   void setEars(string length, string type)
   {
      _earLength = length;
      _earType = type;
   }

protected:
   string _color, _earLength, _earType;
};

int main()
{
   dog mongrel;
   breed labrador("yellow", "large");
   mongrel.setEars("pointy");
   labrador.setEars("long", "floppy");
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;
}
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)