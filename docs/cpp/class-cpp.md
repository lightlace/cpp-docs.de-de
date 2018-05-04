---
title: Klasse (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- class_cpp
dev_langs:
- CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bffa79760e9c597c5a6d736104dc856fc1de16b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="class-c"></a>class (C++)
Das `class`-Schlüsselwort deklariert einen Klassentyp oder definiert ein Objekt eines Klassentyps.  
  
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
 `template-spec`  
 Optionale Vorlagenspezifikationen. Weitere Informationen finden Sie unter [Vorlagen](templates-cpp.md).  
  
 `class`  
 Das `class`-Schlüsselwort.  
  
 `ms-decl-spec`  
 Optionale Speicherklassenspezifikation. Weitere Informationen finden Sie unter der [__declspec](../cpp/declspec.md) Schlüsselwort.  
  
 `tag`  
 Der Typname, der für die Klasse angegeben wurde. Das Tag ist ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Klasse. Das Tag ist optional. Wenn es nicht angegeben wird, wird eine anonyme Klasse definiert. Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Optionale Liste von Klassen oder Strukturen, von denen diese Klasse ihre Member ableitet. Finden Sie unter [Basisklassen](../cpp/base-classes.md) für Weitere Informationen. Jede Klasse oder Struktur Basisnamen kann einen Zugriffsspezifizierer vorangestellt werden ([öffentlichen](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md)) und die [virtuellen](../cpp/virtual-cpp.md) Schlüsselwort. Finden Sie in der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) für Weitere Informationen.  
  
 `member-list`  
 Liste von Klassenmembern. Verweisen auf [Member Klassenüberblick](../cpp/class-member-overview.md) für Weitere Informationen.  
  
 `declarators`  
 Deklaratorliste, die die Namen von mindestens einer Instanz eines Klassentyps festlegt. Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Klasse `public` sind. Dies tritt in Strukturen, deren Datenmember standardmäßig `public` sind, häufiger auf als in Klassen. Finden Sie unter [Übersicht von Deklaratoren](../cpp/overview-of-declarators.md) für Weitere Informationen.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu Klassen im Allgemeinen finden Sie in einem der folgenden Themen:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 Informationen über verwaltete Klassen und Strukturen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>Beispiel  
  
```  
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
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)