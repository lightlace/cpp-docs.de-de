---
title: "reinterpret_cast-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "reinterpret_cast"
  - "reinterpret_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reinterpret_cast-Schlüsselwort [C++]"
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# reinterpret_cast-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht, dass ein beliebiger Zeiger in einen anderen Zeigertyp konvertiert wird.  Ermöglicht es außerdem, einen beliebigen ganzzahligen Typ in einen beliebigen Zeigertyp und umgekehrt zu konvertieren.  
  
## Syntax  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## Hinweise  
 Eine falsche Verwendung des Operators `reinterpret_cast` kann schnell zu einem erhöhten Sicherheitsrisiko führen.  Sofern nicht die gewünschte Konvertierung grundsätzlich auf niedriger Ebene stattfindet, sollten Sie einen der anderen Umwandlungsoperatoren verwenden.  
  
 Der Operator `reinterpret_cast` kann z. B. für Konvertierungen von `char*` in `int*` oder `One_class*` in `Unrelated_class*` verwendet werden, die grundsätzlich unsicher sind.  
  
 Das Ergebnis von `reinterpret_cast` kann nur für die Umwandlung zurück in den ursprünglichen Typ sicher verwendet werden.  Andere Verwendungsmöglichkeiten sind bestenfalls nicht portierbar.  
  
 Der Operator `reinterpret_cast` kann die Attribute**Const**, `volatile` oder **\_\_unaligned** nicht umwandeln.  Weitere Informationen über das Entfernen dieser Attribute finden Sie unter [const\_cast\-Operator](../cpp/const-cast-operator.md).  
  
 Der `reinterpret_cast`\-Operator konvertiert einen NULL\-Zeigerwert in den NULL\-Zeigerwert des Zieltyps.  
  
 Eine praktische Verwendung von `reinterpret_cast` besteht in einer Hashfunktion, die einen Wert einem Index so zuordnet, dass zwei verschiedene Werte am Ende selten den gleichen Index aufweisen.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 Mit `reinterpret_cast` kann der Zeiger als ganzzahliger Typ behandelt werden.  Das Ergebnis ist dann eine Bitverschiebung oder ein XOR\-Vorgang, um einen eindeutigen Index zu erstellen \(eindeutig mit hoher Wahrscheinlichkeit\).  Der Index wird dann von einer standardmäßigen Umwandlung im C\-Format in den Rückgabetyp der Funktion abgeschnitten.  
  
## Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)