---
title: "&#196;nderungen bei Konvertierungsoperatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konvertierungsoperatoren"
  - "Konvertierungen, Explizit"
  - "explicit-Schlüsselwort [C++]"
  - "Operatoren [C++], Explizite Typkonvertierung"
  - "Typkonvertierung, Explizite Konvertierungen"
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# &#196;nderungen bei Konvertierungsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax für Konvertierungsoperatoren hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Ein Beispiel ist die Verwendung von `op_Implicit`, um eine Konvertierung anzugeben.  Hier sehen Sie eine der Sprachspezifikation entnommene Definition von `MyDouble`:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Das bedeutet, dass der Algorithmus zur Konvertierung einer gegebenen ganzen Zahl in `MyDouble` durch den Operator `op_Implicit` bereitgestellt wird.  Darüber hinaus bedeutet es, dass die Konvertierung implizit durch den Compiler ausgeführt wird.  Ebenso stellen die beiden Operatoren `op_Explicit` die entsprechenden Algorithmen zur Konvertierung eines gegebenen `MyDouble`\-Objekts in eine ganze Zahl oder eine verwaltete `String`\-Entität bereit.  Der Compiler führt die Konvertierung jedoch nur aus, wenn sie vom Benutzer explizit angefordert wird.  
  
 In C\# sieht dies folgendermaßen aus:  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 Der C\#\-Code hat deutlich mehr Ähnlichkeit mit C\+\+ als in Managed Extensions for C\+\+.  In der neuen Syntax ist das nicht der Fall.  
  
 Die ISO\-C\+\+\-Kommission führte das Schlüsselwort `explicit` ein, um unbeabsichtigte Folgen zu mindern. Eine `Array`\-Klasse, die ein einzelnes ganzzahliges Argument als Dimension erhält, konvertiert z. B. implizit jede ganze Zahl in ein `Array`\-Objekt, obwohl das sicherlich nicht dem gewünschten Ergebnis entspricht.  Eine Möglichkeit, dies zu verhindern, ist ein Designidiom eines zweiten Arguments \(als Dummy\) für einen Konstruktor.  
  
 Andererseits ist es keine gute Idee, beim Entwurf eines Klassentyps in C\+\+ ein Konvertierungspaar bereitzustellen.  Das beste Beispiel dafür ist die Standard\-Zeichenfolgenklasse.  Die implizite Konvertierung besteht in dem Einzelargumentkonstruktor, der eine Zeichenfolge im C\-Format annimmt.  Allerdings stellt er nicht den entsprechenden impliziten Konvertierungsoperator bereit, der ein Zeichenfolgenobjekt in eine Zeichenfolge mit C\-Format konvertiert, sondern verlangt vom Benutzer, dass er explizit eine benannte Funktion aufruft, in diesem Fall `c_str()`.  
  
 Somit erscheint die Zuordnung von implizitem\/explizitem Verhalten zu einem Konvertierungsoperator \(ebenso wie die Kapselung des Konvertierungssatzes in eine einzige Deklarationsform\) als Verbesserung der ursprünglichen C\+\+\-Unterstützung von Konvertierungsoperatoren, die letztendlich zu dem `explicit`\-Schlüsselwort führte.  Die Unterstützung von Konvertierungsoperatoren durch die [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)]\-Programmiersprache ist aufgrund des Standardverhaltens des Operators, der eine implizite Anwendung des Konvertierungsalgorithmus unterstützt, etwas weniger aussagekräftig als in C\#:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Eine weitere Änderung besteht darin, dass ein Einzelargumentkonstruktor behandelt wird, als ob er `explicit` deklariert wäre.  Dies bedeutet, dass eine explizite Umwandlung erforderlich ist, um seine Aufrufe auszulösen.  Beachten Sie jedoch Folgendes: Wenn ein expliziter Konvertierungsoperator definiert ist, wird dieser an Stelle des Einzelargumentkonstruktors aufgerufen.  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)