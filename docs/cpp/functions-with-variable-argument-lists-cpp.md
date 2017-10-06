---
title: Funktionen mit Variablenargumentlisten (C++) | Microsoft Docs
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
- arguments [C++], variable number of
- variable argument lists
- declarators, functions
- argument lists [C++], variable number of
- declaring functions [C++], variables
- function calls, variable number of arguments
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e7a1f434b9c286bfa625d703023080f55586f0a8
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="functions-with-variable-argument-lists--c"></a>Funktionen mit Variablenargumentlisten Listen (C++)
Funktionsdeklarationen, in denen der letzte Member von  das Auslassungszeichen (...) ist, können eine variable Anzahl von Argumenten akzeptieren. In diesen Fällen stellt C++ die Typüberprüfung nur für die explizit deklarierten Argumente bereit. Sie können Variablenargumentlisten verwenden, wenn Sie eine Funktion so allgemein gestalten müssen, dass sogar die Anzahl und Typen von Argumenten variieren können. Die Funktionsreihe ist ein Beispiel für Funktionen, die Variable Argumentlisten verwenden. `printf` *Argument-Declaration-List*  
  
## <a name="functions-with-variable-arguments"></a>Funktionen mit Variablenargumenten  
 Um auf Argumente nach den deklarierten Argumenten zuzugreifen, verwenden Sie die Makros, die in der Standardincludedatei STDARG.H enthalten sind, wie dies im Folgenden beschrieben wird.  
  
 **Microsoft-spezifisch**  
  
 Mit Microsoft C++ kann das Auslassungszeichen als Argument angegeben werden, wenn das Auslassungszeichen das letzte Argument ist und ein Komma als Präfix hat. Daher ist die Deklaration `int Func( int i, ... );` gültig, `int Func( int i ... );` jedoch nicht.  
  
 **Ende Microsoft-spezifisch**  
  
 Die Deklaration einer Funktion, die eine variable Anzahl von Argumenten akzeptiert, erfordert selbst dann mindestens ein Platzhalterargument, wenn sie nicht verwendet wird. Wenn dieses Platzhalterargument nicht angegeben ist, gibt es keine Möglichkeit, auf die übrigen Argumente zugreifen.  
  
 Wenn Argumente des Typs `char` als Variablenargumente übergeben werden, werden sie in den Typ `int` konvertiert. Auf ähnliche Weise, wenn Argumente des Typs **"float"** übergeben werden als Variable Argumente, sie sind in den Typ konvertiert **doppelte**. Argumente anderer Typen unterliegen den üblichen Ganzzahl- und Gleitkomma-Erweiterungen. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen.  
  
 Funktionen, für die Variablenlisten erforderlich sind, werden mithilfe von Auslassungspunkten (...) in der Argumentliste deklariert. Verwenden Sie die Typen und Makros, die in der STDARG.H-Includedatei beschrieben werden, um auf Argumente zuzugreifen, die von einer Variablenliste übergeben werden. Weitere Informationen zu diesen Makros finden Sie unter [Va_arg, Va_copy, Va_end, Va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). in der Dokumentation für die C-Laufzeitbibliothek.  
  
 Das folgende Beispiel zeigt die Funktionsweise der Makros zusammen mit den Typ (deklariert in STDARG. H): 
  
```  
// variable_argument_lists.cpp  
#include <stdio.h>  
#include <stdarg.h>  
  
//  Declaration, but not definition, of ShowVar.  
void ShowVar( char *szTypes, ... );  
int main() {  
   ShowVar( "fcsi", 32.4f, 'a', "Test string", 4 );  
}  
  
//  ShowVar takes a format string of the form  
//   "ifcs", where each character specifies the  
//   type of the argument in that position.  
//  
//  i = int  
//  f = float  
//  c = char  
//  s = string (char *)  
//  
//  Following the format specification is a variable   
//  list of arguments. Each argument corresponds to   
//  a format character in the format string to which   
// the szTypes parameter points   
void ShowVar( char *szTypes, ... ) {  
   va_list vl;  
   int i;  
  
   //  szTypes is the last argument specified; you must access   
   //  all others using the variable-argument macros.  
   va_start( vl, szTypes );  
  
   // Step through the list.  
   for( i = 0; szTypes[i] != '\0'; ++i ) {  
      union Printable_t {  
         int     i;  
         float   f;  
         char    c;  
         char   *s;  
      } Printable;  
  
      switch( szTypes[i] ) {   // Type to expect.  
         case 'i':  
            Printable.i = va_arg( vl, int );  
            printf_s( "%i\n", Printable.i );  
         break;  
  
         case 'f':  
             Printable.f = va_arg( vl, double );  
             printf_s( "%f\n", Printable.f );  
         break;  
  
         case 'c':  
             Printable.c = va_arg( vl, char );  
             printf_s( "%c\n", Printable.c );  
         break;  
  
         case 's':  
             Printable.s = va_arg( vl, char * );  
             printf_s( "%s\n", Printable.s );  
         break;  
  
         default:  
         break;  
      }  
   }  
   va_end( vl );  
}  
//Output:   
// 32.400002  
// a  
// Test string  
```  
  
 Das vorherige Beispiel verdeutlicht diese wichtigen Konzepte:  
  
1.  Sie müssen eine Listenmarkierung als Variable vom Typ `va_list` erstellen, bevor auf beliebige Variablenargumente zugegriffen wird. Im vorherigen Beispiel wird die Markierung als `vl` bezeichnet.  
  
2.  Auf die einzelnen Argumente wird unter Verwendung des Makros `va_arg` zugegriffen. Sie müssen dem `va_arg`-Makro den Typ des abzurufenden Arguments mitteilen, sodass es die richtige Anzahl von Bytes aus dem Stapel übertragen kann. Wenn Sie einen falschen Typ Größe festlegen, die sich von der unterscheidet, die vom aufrufenden Programm für `va_arg` angegeben wurde, sind die Ergebnisse unvorhersehbar.  
  
3.  Sie sollten das erhaltene Ergebnis explizit in den gewünschten Typ umwandeln, indem Sie das `va_arg`-Makro verwenden.  
  
 Sie müssen das `va_end`-Makro aufrufen, um die Variablenargumentverarbeitung zu beenden.
