---
title: "Prim&#228;re Ausdr&#252;cke"
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
  - "Ausdrücke [C++], Literal"
  - "Ausdrücke [C++], Name"
  - "Ausdrücke [C++], Primär"
  - "Ausdrücke [C++], Qualifizierte Namen"
  - "Primäre Ausdrücke"
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Prim&#228;re Ausdr&#252;cke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Primäre Ausdrücke sind die Bausteine für komplexere Ausdrücke.  Es handelt sich um Literale, Namen und Namen, die vom Bereichsauflösungsoperator \(`::`\) qualifiziert werden.  Ein primärer Ausdruck kann jede der folgenden Formen haben:  
  
```  
  
        literal  
this  
:: name  
name   
( expression )  
```  
  
 Ein *Literal* ist ein konstanter primärer Ausdruck.  Sein Typ hängt von der Form seiner Spezifikation ab.  Alle Informationen über das Festlegen von Literalen finden Sie unter [Literals](../cpp/numeric-boolean-and-pointer-literals-cpp.md).  
  
 Das Schlüsselwort **this** ist ein Zeiger auf ein Klassenobjekt.  Es ist innerhalb von nicht statische Memberfunktionen verfügbar und zeigt auf die Instanz der Klasse, für die die Funktion aufgerufen wurde.  Das Schlüsselwort **this** kann nicht außerhalb des Texts der Klassenmemberfunktion verwendet werden.  
  
 Der Typ des **this**\-Zeigers ist `type` **\*const** \(wobei `type` der Klassenname ist\) innerhalb von Funktionen, die den **this**\-Zeiger nicht speziell ändern.  Das folgende Beispiel zeigt Memberfunktionsdeklarationen und die Typen von **this**:  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 Weitere Informationen über das Ändern des Typs des **this**\-Zeigers finden Sie unter [Type of this Pointer](../misc/type-of-this-pointer.md).  
  
 Der Bereichsauflösungsoperator \(`::`\) gefolgt von einem Namen stellt einen primären Ausdruck dar.  Solche Namen müssen Namen von globaler Reichweite sein, nicht Membernamen.  Der Typ dieses Ausdrucks wird durch die Deklaration des Namens bestimmt.  Es ist ein l\-Wert \(das heißt, er kann auf der linken Seite eines Zuweisungsoperatorausdrucks angezeigt werden\), wenn der deklarierende Name ein l\-Wert ist.  Der Bereichsauflösungsoperator lässt zu, dass auf einen globalen Namen verwiesen wird, selbst wenn dieser Name im aktuellen Bereich ausgeblendet ist.  Ein Beispiel für die Verwendung des Bereichsauflösungsoperators finden Sie unter [Scope](../cpp/scope-visual-cpp.md).  
  
 Ein in Klammern eingefasster Ausdruck ist ein primärer Ausdruck, dessen Typ und Wert mit denen des nicht in Klammern stehenden Ausdrucks identisch sind.  Es ist ein l\-Wert, wenn der nicht in Klammern stehende Ausdruck ein l\-Wert ist.  
  
 Im Kontext der oben gezeigten primären Ausdruckssyntax bedeutet *name*  alles in der Syntax, das für [Names](assetId:///1c49cc24-08d5-4884-b170-ba8ed42d80db) beschrieben wird. Wenn jedoch der Bereichsauflösungsoperators vor dem Namen verwendet wird, sind Typen von Namen, die in einer Klasse auftreten können, nicht zulässig.  Dazu gehören Funktionsnamen für benutzerdefinierte Konvertierung und Destruktornamen.  
  
 Zu den Beispielen von primären Ausdrücken gehören:  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 Alle unten gezeigten Beispiele gelten als *names*, und daher sind sie primäre Ausdrücke in verschiedenen Formen:  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## Siehe auch  
 [Ausdruckstypen](../cpp/types-of-expressions.md)