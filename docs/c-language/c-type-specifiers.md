---
title: C-Typspezifizierer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78cd6292c97f41cb7e862389113404346da80460
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="c-type-specifiers"></a>C-Typspezifizierer
Typspezifizierer in Deklarationen definieren den Typ einer Variablen oder Funktionsdeklaration.  
  
## <a name="syntax"></a>Syntax  
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
  
 Die Typen **signed char**, **signed int**, **signed short int** und **signed long int** werden zusammen mit ihren `unsigned`-Äquivalenten und `enum` als „ganzzahlige“ Typen bezeichnet. Die Typspezifizierer **float**, **double** sowie `long double` werden als „Gleitkommatypen“ bezeichnet. Sie können einen beliebigen ganzzahligen oder Gleitkomma-Typspezifizierer in einer Variablen oder einer Funktionsdeklaration verwenden. Wenn ein *type-specifier* in einer Deklaration nicht angegeben ist, wird dafür `int` angenommen.  
  
 Die optionalen Schlüsselwörter **signed** und `unsigned` können vor oder nach jedem ganzzahligen Typen außer `enum` stehen. Sie können außerdem als Typspezifizierer allein verwendet werden. In diesem Fall werden sie als **signed int** bzw. `unsigned int` interpretiert. Wenn das Schlüsselwort `int` allein verwendet wird, wird angenommen, dass es **signed** ist. Wenn die Schlüsselwörter **long** und **short** allein verwendet werden, werden sie als **long int** und als `short int` interpretiert.  
  
 Enumerationstypen werden als Basistypen betrachtet. Typspezifizierer für Enumerationstypen werden unter [Enumerationsdeklarationen](../c-language/c-enumeration-declarations.md) erläutert.  
  
 Das Schlüsselwort `void` dient drei Zwecken: der Angabe eines Funktionsrückgabewerts, der Angabe einer Argumenttypenliste für eine Funktion, die keine Argumente akzeptiert, und der Angabe eines Zeigers auf einen unbezeichneten Typ. Sie können den `void`-Typ verwenden, um Funktionen zu deklarieren, die keinen Wert zurückgeben, oder um einen Zeiger auf einen nicht angegebenen Typ zu deklarieren. Weitere Informationen zu `void`, wenn es alleine innerhalb der Klammern nach einem Funktionsnamen angezeigt wird, erhalten Sie unter [Argumente](../c-language/arguments.md).  
  
 **Microsoft-spezifisch**  
  
 Die Typüberprüfung ist jetzt ANSI-kompatibel. Dies bedeutet, dass der Typ **short** und der Typ `int` unterschiedliche Typen sind. Zum Beispiel ist dies eine Neudefinition im Microsoft C-Compiler, die von älteren Versionen des Compilers akzeptiert wurde.  
  
```  
int   myfunc();  
short myfunc();  
```  
  
 Im folgenden Beispiel wird ebenfalls eine Warnung über die Dereferenzierung zu unterschiedlichen Typen generiert:  
  
```  
int *pi;  
short *ps;  
  
ps = pi;  /* Now generates warning */  
```  
  
 Der Microsoft C-Compiler generiert auch Warnungen zu Unterschieden im Vorzeichen. Zum Beispiel:  
  
```  
signed int *pi;  
unsigned int *pu  
  
pi = pu;  /* Now generates warning */  
```  
  
 Ausdrücke vom Typ `void` werden im Hinblick auf Nebeneffekte ausgewertet. Sie können den (nicht vorhanden) Wert eines Ausdrucks, der vom Typ `void` ist, in keiner Weise verwenden, noch können Sie einen `void`-Ausdruck (durch implizite oder explizite Konvertierung) in einen beliebigen Typ außer `void` konvertieren. Wenn Sie einen Ausdruck eines anderen Typs in einem Kontext verwenden, in dem ein `void`-Ausdruck erforderlich ist, wird dessen Wert verworfen.  
  
 Zur Einhaltung der ANSI-Spezifikation darf **void\*\*** nicht als **int\*\*** verwendet werden. Nur **void\*** kann als Zeiger auf einen nicht angegebenen Typ verwendet werden.  
  
 **Ende Microsoft-spezifisch**  
  
 Sie können mit `typedef`-Deklarationen zusätzliche Typspezifizierer erstellen, wie unter [Typedef-Deklarationen](../c-language/typedef-declarations.md) beschrieben. Weitere Informationen über die Größe der einzelnen Typen erhalten Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)