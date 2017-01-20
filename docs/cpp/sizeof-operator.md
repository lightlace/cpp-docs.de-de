---
title: "sizeof-Operator"
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
  - "sizeof_cpp"
  - "sizeof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sizeof-Operator"
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# sizeof-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Größe seines Operanden in Bezug auf die Größe des Typs `char` aus.  
  
> [!NOTE]
>  Weitere Informationen über den `sizeof ...`\-Operator finden Sie unter [Auslassungszeichen\- und Variadic\-Vorlagen](../cpp/ellipses-and-variadic-templates.md).  
  
## Syntax  
  
```  
sizeof unary-expression sizeof  ( type-name )  
```  
  
## Hinweise  
 Das Ergebnis des `sizeof`\-Operators ist vom Typ `size_t`, ein ganzzahliger Typ, der in der Includedatei STDDEF.H definiert ist.  Mithilfe dieses Operators können Sie es vermeiden, rechnerabhängige Datengrößen in Ihren Programmen anzugeben.  
  
 Der Operand für `sizeof` kann Folgendes sein:  
  
-   Ein Typname.  Um `sizeof` mit einem Typnamen zu verwenden, muss der Name in Klammern eingeschlossen sein.  
  
-   Ein Ausdruck.  Bei Verwendung mit einem Ausdruck kann `sizeof` mit oder ohne Klammern angegeben werden.  Der Ausdruck wird nicht ausgewertet.  
  
 Wenn der `sizeof`\-Operator auf ein Objekt vom Typ `char` angewendet wird, wird der Wert 1 zurückgegeben.  Wenn der `sizeof`\-Operator auf ein Array angewendet wird, gibt er die Gesamtzahl von Bytes in diesem Array zurück, nicht die Größe des Zeigers, der vom Arraybezeichner dargestellt wird.  Zum Abrufen der Größe des Zeigers, der durch den Arraybezeichner dargestellt wird, übergeben Sie ihn als Parameter an eine Funktion, die `sizeof` verwendet.  Beispiel:  
  
## Beispiel  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## Beispielausgabe  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Wenn der `sizeof`\-Operator auf einen Typ `class`, `struct` oder `union` angewendet wird, ist das Ergebnis die Anzahl der Bytes in einem Objekt dieses Typs zuzüglich möglicher Abstände, die hinzugefügt werden, um Member an Wortgrenzen auszurichten.  Daher stimmt das Ergebnis möglicherweise nicht mit der Größe überein, die durch Addieren der Speicheranforderungen der einzelnen Member berechnet wird.  Die [\/Zp](../build/reference/zp-struct-member-alignment.md)\-Compileroption und das [pack](../preprocessor/pack.md)\-Pragma beeinflussen die Ausrichtungsgrenzen für Member.  
  
 Der `sizeof`\-Operator gibt niemals 0 \(null\) aus, auch nicht für eine leere Klasse.  
  
 Der `sizeof`\-Operator darf nicht mit den folgenden Operanden verwendet werden:  
  
-   Funktionen.  \(Jedoch kann `sizeof` auf Zeigern auf Funktionen angewendet werden.\)  
  
-   Bitfelder.  
  
-   Nicht definierte Klassen.  
  
-   Typ `void`.  
  
-   Dynamisch zugeordnete Arrays.  
  
-   Externe Arrays.  
  
-   Unvollständige Typen.  
  
-   In Klammern gesetzte Namen unvollständiger Typen.  
  
 Wenn der `sizeof`\-Operator auf einen Verweis angewendet wird, ist das Ergebnis das gleiche wie bei Anwendung von `sizeof` auf das Objekt selbst.  
  
 Wenn ein Array ohne Größenangabe das letzte Element einer Struktur ist, gibt der `sizeof`\-Operator die Größe der Struktur ohne das Array zurück.  
  
 Der `sizeof`\-Operator wird häufig verwendet, um die Anzahl von Elementen in einem Array mithilfe eines Ausdrucks im folgenden Format zu berechnen:  
  
```  
sizeof array / sizeof array[0]  
```  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)