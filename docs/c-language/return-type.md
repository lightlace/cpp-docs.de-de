---
title: "Rückgabetyp | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9768baa53e39f1b3243aba24385d592010c3d81a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="return-type"></a>Rückgabetyp
Der Rückgabetyp einer Funktion legt die Größe und den Typ des Werts fest, der von der Funktion zurückgegeben wird, und dem Typspezifizierer in der folgenden Syntax entspricht:  
  
## <a name="syntax"></a>Syntax  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* ist Microsoft-spezifisch */  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 *type-specifier* kann einen beliebigen grundlegenden, Struktur- oder Union-Typ angeben. Wenn Sie *type-specifier* nicht einschließen, wird der Rückgabetyp `int` angenommen.  
  
 Der Rückgabetyp, der in der Funktionsdefinition angegeben ist, muss dem Rückgabetyp in der Funktionsdeklarationen an anderer Stelle im Programm entsprechen. Eine Funktion gibt einen Wert zurück, wenn eine `return`-Anweisung ausgeführt wird, die einen Ausdruck enthält. Der Ausdruck wird ausgewertet, in den Rückgabewert konvertiert, falls erforderlich, und an den Punkt zurückgegeben, an dem die Funktion aufgerufen wurde. Wenn eine Funktion mit dem Rückgabetyp `void` deklariert wird, generiert eine Return-Anweisung, die einen Ausdruck enthält, eine Warnung, und der Ausdruck wird nicht ausgewertet.  
  
 Die folgenden Beispiele veranschaulichen Funktionsrückgabewerte.  
  
```  
typedef struct    
{  
    char name[20];  
    int id;  
    long class;  
} STUDENT;  
  
/* Return type is STUDENT: */  
  
STUDENT sortstu( STUDENT a, STUDENT b )  
{  
    return ( (a.id < b.id) ? a : b );  
}  
```  
  
 Dieses Beispiel definiert den `STUDENT`-Typ mit einer `typedef`-Deklaration und definiert die Funktion `sortstu`, sodass diese über den `STUDENT`-Rückgabetyp verfügt. Die Funktion wählt eines ihrer beiden Strukturargumente aus und gibt dieses zurück. Bei nachfolgenden Aufrufen der Funktion überprüft der Compiler, ob die Argumenttypen `STUDENT` sind.  
  
> [!NOTE]
>  Effizienz wird erhöht, indem Zeiger auf die Struktur, statt auf die gesamte Struktur übergeben werden.  
  
```  
char *smallstr( char s1[], char s2[] )  
{  
    int i;  
  
    i = 0;  
    while ( s1[i] != '\0' && s2[i] != '\0' )  
        i++;  
    if ( s1[i] == '\0' )  
        return ( s1 );  
    else  
        return ( s2 );  
}  
```  
  
 In diesem Beispiel wird eine Funktion definiert, die einen Zeiger an ein Zeichenarray zurückgibt. Die Funktion ruft zwei Zeichenarrays (Zeichenfolgen) als Argumente ab und gibt einen Zeiger auf die kürzere der beiden Zeichenfolgen zurück. Ein Zeiger auf ein Array zeigt auf das erste der Arrayelemente und hat seinen Typ. Daher ist der Rückgabetyp der Funktion ein Zeiger auf den Typ `char`.  
  
 Funktionen müssen vor dem Aufrufen nicht mit dem Rückgabetyp `int` deklariert werden, obwohl Prototypen empfohlen werden, um eine ordnungsgemäße Typüberprüfung für Argumente und Rückgabewerte zu ermöglichen.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Funktionsdefinitionen](../c-language/c-function-definitions.md)