---
title: Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f2ebf51f28912c3cb798acc1ff4aa377c1bebb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++)
> [!NOTE]
>  Ab C ++ 11 werden zwei Arten von Aufgaben in der Sprache unterstützt: *kopieren Zuweisung* und *verschiebezuweisung*. In diesem Artikel bedeutet "Zuweisung" immer "Kopierzuweisung", sofern nicht explizit anders angegeben. Informationen zu bewegungszuweisungen finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](http://msdn.microsoft.com/en-us/1442de5f-37a5-42a1-83a6-ec9cfe0414db).  
>   
>  Objekte können sowohl mit dem Zuordnungsvorgang als auch dem Initialisierungsvorgang kopiert werden.  
  
-   **Zuweisung**: Wenn der Wert eines Objekts in ein anderes Objekt zugewiesen wird, wird das erste Objekt dem zweiten Objekt kopiert. Daher eignet sich  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     dazu, den Wert von `b` nach `a` zu kopieren.  
  
-   **Initialisierung**: Initialisierung erfolgt, wenn ein neues Objekt deklariert wird, wenn Argumente an Funktionen nach Wert übergeben werden, oder wenn Werte von Funktionen nach Wert zurückgegeben werden.  
  
 Sie können die Semantik von "kopieren" für Objekte des Klassentyps definieren. Betrachten Sie beispielsweise folgenden Code:  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 Der vorhergehende Code kann "Den Inhalt von FILE1.DAT auf FILE2.DAT kopieren" oder "FILE2.DAT ignorieren und `b` als zweiten Ziehpunkt für FILE1.DAT erstellen" bedeuten. Jeder Klasse muss wie folgt eine entsprechende Kopiersemantik beigefügt werden.  
  
-   Durch Verwendung des Zuweisungsoperators `operator=` mit einem Verweis auf den Klassentyp als Rückgabetyp und den Parameter, der vom `const`-Verweis übergeben wird, beispielsweise `ClassName& operator=(const ClassName& x);`.  
  
-   Durch Verwendung des Kopierkonstruktors.   
  
 Wenn Sie keinen Kopierkonstruktor deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktor für Sie.  Wenn Sie keinen Kopierkonstruktoroperator deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktoroperator für Sie. Das Deklarieren eines Kopierkonstruktors unterdrückt nicht den vom Compiler generierten Kopierzuweisungsoperator (und umgekehrt). Wenn Sie einen implementieren, sollten Sie auch den anderen implementieren, damit die Codebedeutung eindeutig ist.  
   
 Der Kopierkonstruktor nutzt ein Argument des Typs *Klassenname***&**, wobei *Klassenname* ist der Name der Klasse für die der Konstruktor definiert ist. Zum Beispiel:  
  
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
>  Stellen Sie den Kopierkonstruktor den Argumenttyp *const Klassenname*  **&**  wann immer möglich. Dadurch wird verhindert, dass der Kopierkonstruktor fälschlicherweise das Objekt ändert, aus dem er kopiert. Ermöglicht auch über Kopiervorgang **const** Objekte.  
  
## <a name="compiler-generated-copy-constructors"></a>Vom Compiler generierte Kopierkonstruktoren  
 Vom Compiler generierte Kopierkonstruktoren, wie benutzerdefinierte Kopierkonstruktoren, verfügen über ein einzelnes Argument vom Typ "Verweis auf *Klassenname*." Eine Ausnahme ist, wenn alle Basisklassen und Memberklassen Kopierkonstruktoren so deklariert, dass Sie ein einzelnes Argument vom Typ erwartet haben **const** *Klassenname***&**. In einem solchen Fall ist die vom Compiler generierte Argument eines Kopierkonstruktors auch **const**.  
  
 Wenn der Argumenttyp für den Kopierkonstruktor ist nicht **const**, Initialisierung durch Kopieren einer **const** Objekt wird ein Fehler generiert. Das Gegenteil trifft nicht: Wenn das Argument ist **const**, können Sie ein Objekt kopieren, nicht initialisieren **const**.  
  
 Vom Compiler generierte Zuweisungsoperatoren folgen dem gleichen Muster bezüglich **const.** Nehmen sie ein einzelnes Argument vom Typ *Klassenname*  **&**  es sei denn, die Zuweisungsoperatoren in allen Basis- und Memberklassen Argumente vom Typ akzeptieren **const** *Klassenname &.* In diesem Fall die Klasse des akzeptiert generierte Zuweisungsoperator ein **const** Argument.  
  
> [!NOTE]
>  Wenn virtuelle Basisklassen von Kopierkonstruktoren – vom Compiler generiert oder benutzerdefiniert – initialisiert werden, werden sie nur einmal initialisiert: bei der Erstellung.  
  
 Die Auswirkungen ähneln denen beim Kopierkonstruktor. Wenn der Argumenttyp ist nicht **const**, Zuweisung von einem **const** Objekt wird ein Fehler generiert. Das Gegenteil trifft nicht: Wenn ein **const** Wert zugewiesen wird, auf einen Wert, der nicht **const**, die Zuweisung erfolgreich.  
  
 Weitere Informationen zu überladenen Zuweisungsoperatoren finden Sie unter [Zuweisung](../cpp/assignment.md).  
  
