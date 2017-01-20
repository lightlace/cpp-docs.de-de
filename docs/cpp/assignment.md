---
title: "Zuweisung"
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
  - "Zuweisungsoperatoren, Überladen"
  - "Operatoren [C++], Zuweisung"
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zuweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Zuweisungsoperator \(**\=**\) ist strenggenommen ein binärer Operator.  Seine Deklaration ist mit jedem anderen binären Operator identisch, mit den folgenden Ausnahmen:  
  
-   Es muss eine nicht statische Memberfunktion sein.  Kein `operator=` kann als Nichtmemberfunktion deklariert werden.  
  
-   Es wird nicht von abgeleiteten Klassen geerbt.  
  
-   Eine `operator=`\-Standardfunktion kann vom Compiler für Klassentypen generiert werden, falls nicht vorhanden. \(Weitere Informationen zu `operator=`\-Standardfunktionen finden Sie unter [Memberwise Assignment and Initialization](assetId:///94048213-8b49-4416-8069-b1b7a6f271f9)\).  
  
 Das folgende Beispiel veranschaulicht, wie Sie einen Zuweisungsoperator deklarieren:  
  
```  
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 Beachten Sie, dass das angegebene Argument die rechte Seite des Ausdrucks ist.  Der Operator gibt das Objekt zurück, um das Verhalten des Zuweisungsoperators beizubehalten, der den Wert des linken Rands zurückgibt, nachdem die Zuweisung abgeschlossen ist.  So können Anweisungen geschrieben werden wie:  
  
```  
pt1 = pt2 = pt3;  
```  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)