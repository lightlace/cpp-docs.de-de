---
title: Sizeof-Operator | Microsoft-Dokumentation
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
ms.openlocfilehash: 58724d2e17947c69d1aaf2ed0af66137fe20cc74
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943292"
---
# <a name="sizeof-operator"></a>sizeof-Operator
Gibt die Größe seines Operanden in Bezug auf die Größe des Typs **Char**.  
  
> [!NOTE]
>  Informationen zu den `sizeof ...` -Operator, finden Sie unter [Auslassungszeichen- und Variadic-Vorlagen](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Ergebnis der **"sizeof"** -Operators ist vom Typ `size_t`, ein ganzzahliger Typ, in der Includedatei \<stddef.h >. Mithilfe dieses Operators können Sie es vermeiden, rechnerabhängige Datengrößen in Ihren Programmen anzugeben.  
  
 Der Operand, der **"sizeof"** kann einen der folgenden sein:  
  
-   Ein Typname. Verwendung von **"sizeof"** mit einem Typnamen muss der Namen in Klammern eingeschlossen werden.  
  
-   Ein Ausdruck. Bei Verwendung mit einem Ausdruck **"sizeof"** kann mit oder ohne Klammern angegeben werden. Der Ausdruck wird nicht ausgewertet.  
  
 Wenn die **"sizeof"** -Operator auf ein Objekt des Typs angewendet wird **Char**, es 1 ergibt. Wenn die **"sizeof"** -Operator auf ein Array angewendet wird, bietet Sie die Gesamtzahl der Bytes im Array, nicht die Größe des Zeigers, der vom Arraybezeichner dargestellt. Um die Größe des Zeigers, der vom Arraybezeichner dargestellt zu erhalten, übergeben sie als Parameter an eine Funktion, die verwendet **"sizeof"**. Zum Beispiel:  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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
  
```Output  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Wenn die **"sizeof"** Operator angewendet wird, um eine **Klasse**, **Struktur**, oder **Union** Typ, der das Ergebnis ist die Anzahl der Bytes in einem Objekt, Geben Sie außerdem Auffüllung hinzugefügt, um Member an Wortgrenzen auszurichten. Daher stimmt das Ergebnis möglicherweise nicht mit der Größe überein, die durch Addieren der Speicheranforderungen der einzelnen Member berechnet wird. Die [/Zp](../build/reference/zp-struct-member-alignment.md) Compileroption und das [Pack](../preprocessor/pack.md) Pragma beeinflussen die Ausrichtungsgrenzen für Member.  
  
 Die **"sizeof"** -Operator gibt niemals 0 ist, auch für eine leere Klasse.  
  
 Die **"sizeof"** Operator kann nicht mit den folgenden Operanden verwendet werden:  
  
-   Funktionen. (Allerdings **"sizeof"** auf Zeigern auf Funktionen angewendet werden können.)  
  
-   Bitfelder.  
  
-   Nicht definierte Klassen.  
  
-   Der Typ **"void"**.  
  
-   Dynamisch zugeordnete Arrays.  
  
-   Externe Arrays.  
  
-   Unvollständige Typen.  
  
-   In Klammern gesetzte Namen unvollständiger Typen.  
  
 Wenn die **"sizeof"** -Operator auf einen Verweis angewendet wird, das Ergebnis ist der gleiche wie **"sizeof"** hatte angewendet wurde, auf das Objekt selbst.  
  
 Wenn ein Array ohne Größenangabe das letzte Element einer Struktur ist die **"sizeof"** Operator gibt die Größe der Struktur ohne das Array zurück.  
  
 Die **"sizeof"** -Operator wird häufig verwendet, um die Anzahl der Elemente in einem Array mit einem Ausdruck der Form zu berechnen:  
  
```cpp 
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit Unäroperatoren](../cpp/expressions-with-unary-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)