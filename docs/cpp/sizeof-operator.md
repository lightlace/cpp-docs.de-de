---
title: Sizeof-Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff35b6ef4674121a645fb3d80c96f5da3edded9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="sizeof-operator"></a>sizeof-Operator
Gibt die Größe seines Operanden in Bezug auf die Größe des Typs `char` aus.  
  
> [!NOTE]
>  Informationen zu den `sizeof ...` -Operator, finden Sie unter [Auslassungszeichen- und Variadic-Vorlagen](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Ergebnis der `sizeof` -Operators ist vom Typ `size_t`, ein ganzzahliger Typ, der in der Includedatei definierten \<stddef.h >. Mithilfe dieses Operators können Sie es vermeiden, rechnerabhängige Datengrößen in Ihren Programmen anzugeben.  
  
 Der Operand für `sizeof` kann Folgendes sein:  
  
-   Ein Typname. Um `sizeof` mit einem Typnamen zu verwenden, muss der Name in Klammern eingeschlossen sein.  
  
-   Ein Ausdruck. Bei Verwendung mit einem Ausdruck kann `sizeof` mit oder ohne Klammern angegeben werden. Der Ausdruck wird nicht ausgewertet.  
  
 Wenn der `sizeof`-Operator auf ein Objekt vom Typ `char` angewendet wird, wird der Wert 1 zurückgegeben. Wenn der `sizeof`-Operator auf ein Array angewendet wird, gibt er die Gesamtzahl von Bytes in diesem Array zurück, nicht die Größe des Zeigers, der vom Arraybezeichner dargestellt wird. Zum Abrufen der Größe des Zeigers, der durch den Arraybezeichner dargestellt wird, übergeben Sie ihn als Parameter an eine Funktion, die `sizeof` verwendet. Zum Beispiel:  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Wenn der `sizeof`-Operator auf einen Typ `class`, `struct` oder `union` angewendet wird, ist das Ergebnis die Anzahl der Bytes in einem Objekt dieses Typs zuzüglich möglicher Abstände, die hinzugefügt werden, um Member an Wortgrenzen auszurichten. Daher stimmt das Ergebnis möglicherweise nicht mit der Größe überein, die durch Addieren der Speicheranforderungen der einzelnen Member berechnet wird. Die [/Zp](../build/reference/zp-struct-member-alignment.md) Compileroption und das [Pack](../preprocessor/pack.md) Pragma beeinflussen die Ausrichtungsgrenzen für Member.  
  
 Der `sizeof`-Operator gibt niemals 0 (null) aus, auch nicht für eine leere Klasse.  
  
 Der `sizeof`-Operator darf nicht mit den folgenden Operanden verwendet werden:  
  
-   Funktionen. (Jedoch kann `sizeof` auf Zeigern auf Funktionen angewendet werden.)  
  
-   Bitfelder.  
  
-   Nicht definierte Klassen.  
  
-   Typ `void`.  
  
-   Dynamisch zugeordnete Arrays.  
  
-   Externe Arrays.  
  
-   Unvollständige Typen.  
  
-   In Klammern gesetzte Namen unvollständiger Typen.  
  
 Wenn der `sizeof`-Operator auf einen Verweis angewendet wird, ist das Ergebnis das gleiche wie bei Anwendung von `sizeof` auf das Objekt selbst.  
  
 Wenn ein Array ohne Größenangabe das letzte Element einer Struktur ist, gibt der `sizeof`-Operator die Größe der Struktur ohne das Array zurück.  
  
 Der `sizeof`-Operator wird häufig verwendet, um die Anzahl von Elementen in einem Array mithilfe eines Ausdrucks im folgenden Format zu berechnen:  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)