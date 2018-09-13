---
title: Zeigerdeklarationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer declarations
- declarations, pointers
- const keyword [C]
- pointers, declarations
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f7e5f8933aabe36362938a23c28ed1cd562a579
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205392"
---
# <a name="pointer-declarations"></a>Zeigerdeklarationen
Eine "Zeigerdeklaration" benennt eine Zeigervariable und gibt den Typ des Objekts an, auf das die Variable zeigt. Eine Variable, die als Zeiger deklariert ist, enthält eine Speicheradresse.  
  
## <a name="syntax"></a>Syntax

*declarator*:  
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*  

*direct-declarator*:  
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*  
&nbsp;&nbsp;&nbsp;&nbsp;**(** *declarator* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **[** *constant-expression*<sub>opt</sub> **]**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **(** *parameter-type-list* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **(** *identifier-list*<sub>opt</sub> **)**  

*pointer*:  
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>opt</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>opt</sub> *pointer*  

*type-qualifier-list*:  
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier*  
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier-list* *type-qualifier*  
  
 *type-specifier* gibt den Typ des Objekts an, wobei es sich um jeden Basis-, Struktur- oder Union-Typ handeln kann. Zeigervariablen können auf Funktionen, Arrays und andere Zeiger zeigen. (Weitere Informationen zum Deklarieren und Interpretieren komplexerer Zeigertypen finden Sie unter [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md).)  
  
 Sie können die Spezifikation des vom Zeiger referenzierten Typs verzögern, indem Sie *void* für den **type-specifier** angeben. Ein solches Element wird als „Zeiger auf **void**“ bezeichnet und in der Form `void *` geschrieben. Mit einer Variable, die als Zeiger auf *void* deklariert wird, können Sie auf ein Objekt beliebigen Typs verweisen. Zum Ausführen der meisten Vorgänge für den Zeiger oder das Objekt, auf das dieser zeigt, müssen Sie jedoch den Typ, auf den der Zeiger zeigt, explizit pro Vorgang angeben. (Variablen des Typs **char** <strong>\*</strong> und des Typs **void** <strong>\*</strong> sind ohne eine Typumwandlung zuweisungskompatibel.) Diese Konvertierung kann durch eine Typumwandlung geschehen (weitere Informationen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md)).  
  
 Der *type-qualifier* kann entweder **const** oder **volatile** oder beides sein. Diese Typqualifizierer geben an, dass der Zeiger nicht vom Programm selbst geändert werden kann (**const**) bzw. dass der Zeiger von einem Prozess, der nicht vom Programm gesteuert wird, zulässigerweise geändert werden kann (**volatile**). (Weitere Informationen zu **const** und **volatile** finden Sie unter [Typqualifizierer](../c-language/type-qualifiers.md).)  
  
 Der *Deklarator* benennt die Variable und kann einen Typmodifizierer enthalten. Wenn der *Deklarator* z. B. ein Array darstellt, wird der Typ des Zeigers in einen Zeiger auf ein Array geändert.  
  
 Sie können einen Zeiger auf einen Struktur-, Union- oder Enumerationstyp deklarieren, bevor Sie den Struktur-, Union- oder Enumerationstyp definieren. Sie deklarieren den Zeiger, indem Sie das Struktur- oder Uniontag wie in den Beispielen unten verwenden. Derartige Deklarationen sind zulässig, da dem Compiler die Größe der Struktur oder Union nicht bekannt sein muss, um Speicherplatz für die Zeigervariable zuzuweisen.  
  
## <a name="examples"></a>Beispiele  
 Die folgenden Beispiele veranschaulichen Zeigerdeklarationen.  
  
```  
char *message; /* Declares a pointer variable named message */  
```  
  
 Der *message*-Zeiger zeigt auf eine Variable mit **char**-Typ.  
  
```  
int *pointers[10];  /* Declares an array of pointers */  
```  
  
 Das *pointers*-Array hat zehn Elemente. Jedes Element ist ein Zeiger auf eine Variable mit **int**-Typ.  
  
```  
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */  
```  
  
 Die *pointer*-Variable zeigt auf ein Array mit zehn Elementen. Jedes Element in diesem Array ist vom Typ **int**.  
  
```  
int const *x;      /* Declares a pointer variable, x,  
                      to a constant value */   
```  
  
 Der Zeiger *x* kann geändert werden, um auf einen anderen **int**-Wert zu zeigen, aber der Wert, auf den er zeigt, kann nicht geändert werden.  
  
```  
const int some_object = 5 ;  
int other_object = 37;  
int *const y = &fixed_object;  
int volatile *const z = &some_object;  
int *const volatile w = &some_object;  
```  
  
 Die Variable *y* in diesen Deklarationen wird als konstanter Zeiger auf einen **int**-Wert deklariert. Der Wert, auf den er zeigt, kann geändert werden, aber der Zeiger selbst muss stets auf denselben Speicherort zeigen: die Adresse von *fixed_object*. Ebenso ist *z* ein konstanter Zeiger, der aber auch deklariert wird, um auf **int** zu zeigen, dessen Wert nicht vom Programm geändert werden kann. Obwohl der Wert **const int**, auf den *z* zeigt, nicht vom Programm geändert werden kann, wird durch den zusätzlichen Spezifizierer **volatile** festgelegt, dass es zulässig ist, wenn der Wert durch einen derzeit mit dem Programm ausgeführten Prozess geändert wird. Die Deklaration von *w* gibt an, dass das Programm den Wert nicht ändern kann, auf den gezeigt wird, und dass das Programm den Zeiger nicht ändern kann.  
  
```  
struct list *next, *previous; /* Uses the tag for list */  
```  
  
 In diesem Beispiel werden zwei Zeigervariablen, *next* und *previous*, deklariert, die auf den Strukturtyp *list* zeigen. Diese Deklaration kann vor der Definition des *list*-Strukturtyps stehen (siehe das nächste Beispiel), sofern die *list*-Typdefinition die gleiche Sichtbarkeit wie die Deklaration hat.  
  
```  
struct list   
{  
    char *token;  
    int count;  
    struct list *next;  
} line;  
```  
  
 Die *line*-Variable hat den Strukturtyp mit dem Namen *list*. Der *list*-Strukturtyp hat drei Member. Der erste Member ist ein Zeiger auf einen **char**-Wert, der zweite ist ein **int**-Wert, und der dritte ist ein Zeiger auf eine andere *list*-Struktur.  
  
```  
struct id   
{  
    unsigned int id_no;  
    struct name *pname;  
} record;  
```  
  
 Die *record*-Variable hat den Strukturtyp *id*. Beachten Sie, dass *pname* als Zeiger auf einen anderen Strukturtyp mit dem Namen *name* deklariert wird. Diese Deklaration kann vor der Definition des *name*-Typs stehen.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)