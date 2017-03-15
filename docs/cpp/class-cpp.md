---
title: "class (C++)"
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
  - "class_cpp"
  - "class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class-Schlüsselwort [C++]"
  - "Klassentypen, class-Anweisungen"
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# class (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `class`\-Schlüsselwort deklariert einen Klassentyp oder definiert ein Objekt eines Klassentyps.  
  
## Syntax  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### Parameter  
 `template-spec`  
 Optionale Vorlagenspezifikationen.  Weitere Informationen finden Sie unter [Vorlagenspezifikationen](../Topic/Template%20Specifications.md).  
  
 `class`  
 Das `class`\-Schlüsselwort.  
  
 `ms-decl-spec`  
 Optionale Speicherklassenspezifikation.  Weitere Informationen finden Sie im Zusammenhang mit dem [\_\_declspec](../cpp/declspec.md)\-Schlüsselwort.  
  
 `tag`  
 Der Typname, der für die Klasse angegeben wurde.  Das Tag ist ein reserviertes Wort innerhalb des Gültigkeitsbereichs der Klasse.  Das Tag ist optional.  Wenn es nicht angegeben wird, wird eine anonyme Klasse definiert.  Weitere Informationen finden Sie unter [Anonyme Klassentypen](../cpp/anonymous-class-types.md).  
  
 `base-list`  
 Optionale Liste von Klassen oder Strukturen, von denen diese Klasse ihre Member ableitet.  Weitere Informationen finden Sie unter [Basisklassen](../cpp/base-classes.md).  Jedem Basisklassen\- oder Strukturnamen kann ein Zugriffsspezifizierer \([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md)\) und das [virtual](../cpp/virtual-cpp.md)\-Schlüsselwort vorangestellt werden.  Weitere Informationen finden Sie in der Memberzugriffstabelle unter [Steuern des Zugriffs auf Klassenmember](../misc/controlling-access-to-class-members.md).  
  
 `member-list`  
 Liste von Klassenmembern.  Weitere Informationen finden Sie unter [Übersicht über Klassenmember](../cpp/class-member-overview.md).  
  
 `declarators`  
 Deklaratorliste, die die Namen von mindestens einer Instanz eines Klassentyps festlegt.  Deklaratoren können Initialisierungslisten enthalten, wenn alle Datenmember der Klasse `public` sind.  Dies tritt in Strukturen, deren Datenmember standardmäßig `public` sind, häufiger auf als in Klassen.  Weitere Informationen finden Sie unter [Übersicht über Deklaratoren](../cpp/overview-of-declarators.md).  
  
## Hinweise  
 Weitere Informationen zu Klassen im Allgemeinen finden Sie in einem der folgenden Themen:  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [\_\_multiple\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_single\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_virtual\_inheritance](../cpp/inheritance-keywords.md)  
  
 Informationen über verwaltete Klassen und Strukturen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Beispiel  
  
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
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)