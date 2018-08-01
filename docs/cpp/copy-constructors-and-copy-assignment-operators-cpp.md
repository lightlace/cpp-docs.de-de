---
title: Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- = operator [C++], copying objects
- assignment statements [C++], copying objects
- assignment operators [C++], for copying objects
- objects [C++], copying
- initializing objects, by copying objects
- copying objects
- assigning values to copy objects
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24f9e4e5b3d157f23c18d46f2857b29e6960e82e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405755"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++)
> [!NOTE]
>  Ab C ++ 11, werden zwei Arten von Aufgaben in der Sprache unterstützt: *kopieren Zuweisung* und *bewegungszuweisung*. In diesem Artikel bedeutet "Zuweisung" immer "Kopierzuweisung", sofern nicht explizit anders angegeben. Weitere Informationen zu bewegungszuweisungen finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](http://msdn.microsoft.com/1442de5f-37a5-42a1-83a6-ec9cfe0414db).  
>   
>  Objekte können sowohl mit dem Zuordnungsvorgang als auch dem Initialisierungsvorgang kopiert werden.  
  
-   **Zuweisung**: Wenn der Wert eines Objekts in ein anderes Objekt zugewiesen wird, wird das erste Objekt dem zweiten Objekt kopiert. Daher eignet sich  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     dazu, den Wert von `b` nach `a` zu kopieren.  
  
-   **Initialisierung**: Initialisierung tritt auf, wenn ein neues Objekt deklariert wird, wenn Argumente an Funktionen nach Wert übergeben werden, oder wenn die Werte von Funktionen nach Wert zurückgegeben werden.  
  
 Sie können die Semantik von "kopieren" für Objekte des Klassentyps definieren. Betrachten Sie beispielsweise folgenden Code:  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 Der vorhergehende Code kann "Den Inhalt von FILE1.DAT auf FILE2.DAT kopieren" oder "FILE2.DAT ignorieren und `b` als zweiten Ziehpunkt für FILE1.DAT erstellen" bedeuten. Jeder Klasse muss wie folgt eine entsprechende Kopiersemantik beigefügt werden.  
  
-   Durch die Verwendung des Zuweisungsoperators **Operator =** mit einem Verweis auf den Klassentyp als Rückgabetyp und den Parameter, der übergeben wird, indem **const** Verweis – z. B. `ClassName& operator=(const ClassName& x);`.  
  
-   Durch Verwendung des Kopierkonstruktors.   
  
 Wenn Sie keinen Kopierkonstruktor deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktor für Sie.  Wenn Sie keinen Kopierkonstruktoroperator deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktoroperator für Sie. Das Deklarieren eines Kopierkonstruktors unterdrückt nicht den vom Compiler generierten Kopierzuweisungsoperator (und umgekehrt). Wenn Sie einen implementieren, sollten Sie auch den anderen implementieren, damit die Codebedeutung eindeutig ist.  
   
 Der Kopierkonstruktor nutzt ein Argument vom Typ * Klasse-Name ***&**, wobei *Klassennamen* ist der Name der Klasse für die der Konstruktor definiert ist. Zum Beispiel:  
  
```cpp  
// spec1_copying_class_objects.cpp  
class Window  
{  
public:  
    Window( const Window& ); // Declare copy constructor.  
    // ...  
};  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  Stellen Sie den Kopierkonstruktor den Argumenttyp *const-Klasse-Namen *** &** nach Möglichkeit. Dadurch wird verhindert, dass der Kopierkonstruktor fälschlicherweise das Objekt ändert, aus dem er kopiert. Er ermöglicht auch die kopieren aus **const** Objekte.  
  
## <a name="compiler-generated-copy-constructors"></a>Vom Compiler generierte Kopierkonstruktoren  
 Vom Compiler generierte Kopierkonstruktoren, wie benutzerdefinierte Kopierkonstruktoren, haben Sie ein einzelnes Argument vom Typ "Verweis auf *Klassennamen*." Eine Ausnahme ist, wenn alle Basisklassen und Memberklassen Kopierkonstruktoren so deklariert, als ein einzelnes Argument des Typs haben **const** * Klasse-Name ***&**. In diesem Fall ist der vom Compiler generierte Kopierkonstruktor den Argumenttyp auch **const**.  
  
 Wenn der Argumenttyp für den Kopierkonstruktor nicht ist **const**, Initialisierung durch Kopieren einer **const** Objekt wird ein Fehler generiert. Das Gegenteil trifft nicht: Wenn das Argument ist **const**, können Sie ein Objekt, das nicht kopieren initialisieren **const**.  
  
 Vom Compiler generierte Zuweisungsoperatoren folgen demselben Muster in Bezug auf **const.** Sie akzeptieren ein einzelnes Argument vom Typ *Klasse-Namen *** &** es sei denn, die Zuweisungsoperatoren in allen Basis- und Memberklassen Argumente vom Typ akzeptieren **const** *Klassennamen &.* In diesem Fall die Klasse des akzeptiert generierte Zuweisungsoperator eine **const** Argument.  
  
> [!NOTE]
>  Wenn virtuelle Basisklassen von Kopierkonstruktoren – vom Compiler generiert oder benutzerdefiniert – initialisiert werden, werden sie nur einmal initialisiert: bei der Erstellung.  
  
 Die Auswirkungen ähneln denen beim Kopierkonstruktor. Wenn der Argumenttyp ist nicht **const**, Zuweisung von einem **const** Objekt wird ein Fehler generiert. Das Gegenteil trifft nicht: Wenn ein **const** Wert wird zugewiesen, auf einen Wert, der nicht **const**, die Zuordnung erfolgreich ist.  
  
 Weitere Informationen zu überladenen Zuweisungsoperatoren finden Sie unter [Zuweisung](../cpp/assignment.md).  