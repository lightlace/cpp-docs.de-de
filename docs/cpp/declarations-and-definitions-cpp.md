---
title: Deklarationen und Definitionen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdf87e9db7ecd419897615ab45cc967360b67fc2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462400"
---
# <a name="declarations-and-definitions-c"></a>Deklarationen und Definitionen (C++)
Deklarationen führen Namen in einem Programm, z. B. die Namen von Variablen, Namespaces, Funktionen und Klassen. Deklarationen geben außerdem die Typinformationen als auch andere Eigenschaften des Objekts an, das deklariert wird. Ein Name muss deklariert werden, bevor er verwendet werden kann. In C++ bestimmt der Punkt, an dem ein Name deklariert wird, ob er für den Compiler sichtbar ist. Sie können nicht auf eine Funktion oder Klasse, die zu einem späteren Zeitpunkt in der Kompilierungseinheit deklariert ist, verweisen; Sie können *Vorwärtsdeklarationen* , diese Einschränkung zu umgehen.  
  
 Definitionen angeben, welchen Code oder Daten auf den Namen beschreibt. Der Compiler benötigt die Definition, um Speicherplatz für das zu reservieren, was deklariert wird.  
  
## <a name="declarations"></a>Deklarationen  
 Eine Deklaration führt mindestens einen Namen in ein Programm ein. Deklarationen können in einem Programm mehrmals vorkommen. Daher können Klassen, Strukturen, Enumerationstypen und andere benutzerdefinierte Typen für die einzelnen Kompilierungseinheiten deklariert werden. Die Einschränkung für diese mehrfache Deklaration besteht darin, dass alle Deklarationen identisch sein müssen. Deklarationen dienen als auch Definitionen, außer wenn auf die Deklaration Folgendes zutrifft:  
  
1.  Sie ist ein Funktionsprototyp (eine Funktionsdeklaration ohne Funktionstext).  
  
2.  Enthält die **"extern"** Spezifizierer, aber keine Initialisierer (Objekte und Variablen) oder Funktionsrumpf (Funktionen). Dies gibt an, dass die Definition nicht notwendigerweise in der aktuellen Übersetzungseinheit ist, und weist dem Namen eine externe Bindung zu.  
  
3.  Sie ist von einem statischen Datenmember innerhalb einer Klassendeklaration.  
  
     Da statische Klassendatenmember diskrete Variablen sind, die für alle Objekte der Klasse freigegeben werden, müssen sie definiert werden und außerhalb der Klassendeklaration initialisiert werden. (Weitere Informationen über Klassen und Klassenmembern finden Sie unter [Klassen](../cpp/classes-and-structs-cpp.md).)  
  
4.  Sie ist eine Klassennamendeklaration ohne nachfolgende Definition, wie `class T;`.  
  
5.  Ist eine **Typedef** Anweisung.  
  
Beispiele für Deklarationen, die auch Definitionen sind:  
  
```cpp 
// Declare and define int variables i and j.  
int i;  
int j = 10;  
  
// Declare enumeration suits.  
enum suits { Spades = 1, Clubs, Hearts, Diamonds };  
  
// Declare class CheckBox.  
class CheckBox : public Control  
{  
public:  
            Boolean IsChecked();  
    virtual int     ChangeState() = 0;  
};  
```  
  
Beispiele für Deklarationen, die keine Definitionen sind:  
  
```cpp 
extern int i;  
char *strchr( const char *Str, const char Target );  
```  
  
 Es wird angenommen, dass ein Name unmittelbar nach seinem Deklarator, jedoch vor seinem (optionalen) Initialisierer deklariert wird. Weitere Informationen finden Sie unter [Zeitpunkt der Deklarationen](../cpp/point-of-declaration-in-cpp.md).  
  
 Deklarationen werden in einem *Bereich*. Der Bereich steuert die Sichtbarkeit des deklarierten Namens und die Dauer des definierten Objekts, falls vorhanden. Weitere Informationen darüber, wie Bereichsregeln mit Deklarationen interagieren, finden Sie unter [Bereich](../cpp/scope-visual-cpp.md).  
  
 Eine Objektdeklaration ist auch eine Definition, es sei denn, die **"extern"** Speicherklassenspezifizierer, die in beschriebenen [Speicherklassen](storage-classes-cpp.md). Eine Funktionsdeklaration ist auch eine Definition, es sei denn, sie ist ein Prototyp. Ein Prototyp ist ein Funktionsheader ohne einen definierenden Funktionsrumpf. Die Definition eines Objekts bewirkt die Speicherbelegung und die richtige Initialisierung des Objekts.  
  
## <a name="definitions"></a>Definitionen  
 Eine Definition ist eine eindeutige Spezifikation eines Objekts oder einer Variable, Funktion, Klasse oder eines Enumerators. Da Definitionen eindeutig sein müssen, kann ein Programm nur eine Definition für ein gegebenes Programmelement enthalten. Es kann eine n:1-Zuordnung zwischen Deklarationen und Definitionen vorgenommen werden. Es gibt zwei Fälle, in denen ein Programmelement deklariert werden und nicht definiert werden kann:  
  
1.  Eine Funktion wird deklariert, aber nie mit einem Funktionsaufruf oder einem Ausdruck, der die Adresse der Funktion akzeptiert, referenziert.  
  
2.  Eine Klasse wird nur auf eine Weise verwendet, die nicht erfordert, dass ihre Definition bekannt ist. Allerdings muss die Klasse deklariert werden. Das folgende Codebeispiel veranschaulicht einen solchen Fall:  
  
    ```cpp 
    // definitions.cpp  
    class WindowCounter;   // Forward declaration; no definition  
  
    class Window  
    {  
       // Definition of WindowCounter not required  
       static WindowCounter windowCounter;  
    };  
  
    int main()  
    {  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)   
 [Zeitpunkt der Deklarationen](../cpp/point-of-declaration-in-cpp.md)