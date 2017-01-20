---
title: "Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "=-Operator, Kopieren von Objekten"
  - "Zuweisen von Werten zum Kopieren von Objekten"
  - "Zuweisungsoperatoren, Zum Kopieren von Objekten"
  - "Zuweisungsanweisungen, Kopieren von Objekten"
  - "Kopieren von Objekten"
  - "Initialisieren von Objekten, Durch Kopieren von Objekten"
  - "Objekte [C++], Kopieren"
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Kopierkonstruktoren und Kopierzuweisungsoperatoren (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ab C \+\+ 11 werden zwei Arten von Aufgaben unterstützt: *Kopierzuweisung* und *Bewegungszuweisung*.  In diesem Artikel bedeutet "Zuweisung" immer "Kopierzuweisung", sofern nicht explizit anders angegeben.  Informationen zu Bewegungszuweisungen finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren \(C\+\+\)](assetId:///1442de5f-37a5-42a1-83a6-ec9cfe0414db).  
>   
>  Objekte können sowohl mit dem Zuordnungsvorgang als auch dem Initialisierungsvorgang kopiert werden.  
  
-   **Zuordnung**: Wenn der Wert eines Objekts einem anderen Objekt zugewiesen wird, wird das erste Objekt in das zweite Objekt kopiert.  Daher eignet sich  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     dazu, den Wert von `b` nach `a` zu kopieren.  
  
-   **Initialisierung**: Die Initialisierung erfolgt zum Zeitpunkt der Deklaration eines neuen Objekts, wenn Argumente an Funktionen nach Wert übergeben werden und wenn Werte von Funktionen nach Wert zurückgegeben werden.  
  
 Sie können die Semantik von "kopieren" für Objekte des Klassentyps definieren.  Betrachten Sie beispielsweise folgenden Code:  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 Der vorhergehende Code kann "Den Inhalt von FILE1.DAT auf FILE2.DAT kopieren" oder "FILE2.DAT ignorieren und `b` als zweiten Ziehpunkt für FILE1.DAT erstellen" bedeuten. Jeder Klasse muss wie folgt eine entsprechende Kopiersemantik beigefügt werden.  
  
-   Durch Verwendung des Zuweisungsoperators `operator=` mit einem Verweis auf den Klassentyp als Rückgabetyp und den Parameter, der vom `const`\-Verweis übergeben wird, beispielsweise `ClassName& operator=(const ClassName& x);`.  
  
-   Durch Verwendung des Kopierkonstruktors.  Weitere Informationen über den Kopierkonstruktor finden Sie unter [Regeln zum Deklarieren von Konstruktoren](../misc/rules-for-declaring-constructors.md).  
  
 Wenn Sie keinen Kopierkonstruktor deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktor für Sie.  Wenn Sie keinen Kopierkonstruktoroperator deklarieren, generiert der Compiler einen memberweisen Kopierkonstruktoroperator für Sie. Das Deklarieren eines Kopierkonstruktors unterdrückt nicht den vom Compiler generierten Kopierzuweisungsoperator \(und umgekehrt\).  Wenn Sie einen implementieren, sollten Sie auch den anderen implementieren, damit die Codebedeutung eindeutig ist.  
  
 Die memberweise Zuweisung wird ausführlich in [\(NOTINBUILD\) Memberwise Assignment and Initialization](assetId:///94048213-8b49-4416-8069-b1b7a6f271f9) besprochen.  
  
 Der Kopierkonstruktor nutzt ein Argument des Typs *class\-name***&**, wobei *class\-name* für den Namen der Klasse steht, für die der Konstruktor definiert ist.  Zum Beispiel:  
  
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
>  Nutzen Sie soweit möglich für den Kopierkonstruktor den Argumenttyp *const class\-name***&**.  Dadurch wird verhindert, dass der Kopierkonstruktor fälschlicherweise das Objekt ändert, aus dem er kopiert.  Zudem wird auch das Kopieren von **const**\-Objekten ermöglicht.  
  
## Vom Compiler generierte Kopierkonstruktoren  
 Vom Compiler generierte Kopierkonstruktoren, wie benutzerdefinierte Kopierkonstruktoren, verfügen über ein einzelnes Argument vom Typ "Verweis auf *class\-name*". Eine Ausnahme liegt vor, wenn alle Basisklassen und Memberklassen Kopierkonstruktoren so deklariert haben, dass sie ein einzelnes Argument vom Typ **const** *class\-name***&** akzeptieren.  In einem solchen Fall ist das vom Compiler generierte Argument eines Kopierkonstruktors auch **const**.  
  
 Wenn der Argumenttyp für den Kopierkonstruktor nicht **const** ist, erzeugt die Initialisierung durch Kopieren eines **const**\-Objekts einen Fehler.  Das Gegenteil trifft nicht zu: Wenn das Argument **const** ist, können Sie eine Initialisierung vornehmen, indem Sie ein Objekt kopieren, das nicht **const** ist.  
  
 Vom Compiler generierte Zuweisungsoperatoren folgen bezüglich **const** demselben Muster. Sie akzeptieren ein einzelnes Argument vom Typ *class\-name***&**, es sei denn, die Zuweisungsoperatoren in allen Basis\- und Memberklassen akzeptieren Argumente vom Typ **const** *class\-name&*. In diesem Fall akzeptiert der generierte Zuweisungsoperator der Klasse ein **const**\-Argument.  
  
> [!NOTE]
>  Wenn virtuelle Basisklassen von Kopierkonstruktoren – vom Compiler generiert oder benutzerdefiniert – initialisiert werden, werden sie nur einmal initialisiert: bei der Erstellung.  
  
 Die Auswirkungen ähneln denen beim Kopierkonstruktor.  Wenn der Argumenttyp nicht **const** ist, erzeugt die Zuweisung von einem **const**\-Objekt einen Fehler.  Das Gegenteil trifft nicht zu: Wenn ein **const**\-Wert einem Wert zugewiesen ist, der nicht **const** ist, ist die Zuweisung erfolgreich.  
  
 Weitere Informationen zu überladenen Zuweisungsoperatoren finden Sie unter [Zuweisung](../cpp/assignment.md).  
  
## Siehe auch  
 [Spezielle Memberfunktionen](../misc/special-member-functions-cpp.md)