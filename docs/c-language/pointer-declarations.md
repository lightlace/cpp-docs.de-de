---
title: "Zeigerdeklarationen"
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
  - "C"
helpviewer_keywords: 
  - "const-Schlüsselwort [C]"
  - "Deklarationen, Zeiger"
  - "Zeigerdeklarationen"
  - "Zeiger, Deklarationen"
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Zeigerdeklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Zeigerdeklaration" benennt eine Zeigervariable und gibt den Typ des Objekts an, auf das die Variable zeigt.  Eine Variable, die als Zeiger deklariert ist, enthält eine Speicheradresse.  
  
## Syntax  
 `declarator`:  
 `pointer` opt *direct\-declarator*  
  
 *direct\-declarator*:  
 *identifier*  
  
 **\(**  *declarator*  **\)**  
  
 *direct\-declarator*  **\[**  *constant\-expression* opt **\]**  
  
 *direct\-declarator*  **\(**  *parameter\-type\-list*  **\)**  
  
 *direct\-declarator*  **\(**  *identifier\-list* opt **\)**  
  
 `pointer`:  
 **\*** *type\-qualifier\-list* opt  
  
 **\*** *type\-qualifier\-list* opt `pointer`  
  
 *type\-qualifier\-list*:  
 *type\-qualifier*  
  
 *type\-qualifier\-list type\-qualifier*  
  
 *type\-specifier* gibt den Typ des Objekts an, wobei es sich um jeden Basis\-, Struktur\- oder Union\-Typ handeln kann.  Zeigervariablen können auf Funktionen, Arrays und andere Zeiger zeigen. \(Weitere Informationen zum Deklarieren und Interpretieren komplexerer Zeigertypen finden Sie unter [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md).\)  
  
 Sie können die Spezifikation des vom Zeiger referenzierten Typs verzögern, indem Sie `void` für den *type\-specifier* angeben.  Ein solches Element wird als "Zeiger auf `void`" bezeichnet und in der Form `void *` geschrieben.  Mit einer Variable, die als Zeiger auf `void` deklariert wird, können Sie auf ein Objekt beliebigen Typs verweisen.  Zum Ausführen der meisten Vorgänge für den Zeiger oder das Objekt, auf das dieser zeigt, müssen Sie jedoch den Typ, auf den der Zeiger zeigt, explizit pro Vorgang angeben. \(Variablen des Typs **char \*** und des Typs **void \*** sind ohne eine Typumwandlung zuweisungskompatibel.\) Diese Konvertierung kann durch eine Typumwandlung geschehen \(weitere Informationen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md) \).  
  
 *type\-qualifier* kann **const**, `volatile` oder beides sein.  Diese Typqualifizierer geben an, dass der Zeiger nicht vom Programm selbst geändert werden kann \(**const**\) bzw. dass der Zeiger von einem Prozess, der nicht vom Programm gesteuert wird, zulässigerweise geändert werden kann \(`volatile`\). \(Weitere Informationen zu **const** und `volatile` finden Sie unter [Typqualifizierer](../c-language/type-qualifiers.md).\)  
  
 Der `declarator` benennt die Variable und kann einen Typmodifizierer enthalten.  Wenn der `declarator` z. B. ein Array darstellt, wird der Typ des Zeigers in einen Zeiger auf ein Array geändert.  
  
 Sie können einen Zeiger auf einen Struktur\-, Union\- oder Enumerationstyp deklarieren, bevor Sie den Struktur\-, Union\- oder Enumerationstyp definieren.  Sie deklarieren den Zeiger, indem Sie das Struktur\- oder Uniontag wie in den Beispielen unten verwenden.  Derartige Deklarationen sind zulässig, da dem Compiler die Größe der Struktur oder Union nicht bekannt sein muss, um Speicherplatz für die Zeigervariable zuzuweisen.  
  
## Beispiele  
 Die folgenden Beispiele veranschaulichen Zeigerdeklarationen.  
  
```  
char *message; /* Declares a pointer variable named message */  
```  
  
 Der `message`\-Zeiger zeigt auf eine Variable mit `char`\-Typ.  
  
```  
int *pointers[10];  /* Declares an array of pointers */  
```  
  
 Das `pointers`\-Array hat 10 Elemente. Jedes Element ist ein Zeiger auf eine Variable mit `int`\-Typ.  
  
```  
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */  
```  
  
 Die Zeigervariable zeigt auf ein Array mit 10 Elementen.  Jedes Element in diesem Array ist vom Typ `int`.  
  
```  
int const *x;      /* Declares a pointer variable, x,  
                      to a constant value */   
```  
  
 Der Zeiger `x` kann geändert werden, um auf einen anderen `int`\-Wert zu zeigen, aber der Wert, auf den er zeigt, kann nicht geändert werden.  
  
```  
const int some_object = 5 ;  
int other_object = 37;  
int *const y = &fixed_object;  
int volatile *const z = &some_object;  
int *const volatile w = &some_object;  
```  
  
 Die Variable `y` in diesen Deklarationen wird als konstanter Zeiger auf einen `int`\-Wert deklariert.  Der Wert, auf den er zeigt, kann geändert werden, aber der Zeiger selbst muss stets auf denselben Speicherort zeigen: die Adresse von `fixed_object`.  Ebenso ist `z` ein konstanter Zeiger, der aber auch deklariert wird, um auf `int` zu zeigen. Der "int"\-Wert kann nicht vom Programm geändert werden.  Obwohl der Wert **const int**, auf den `z` zeigt, nicht vom Programm geändert werden kann, wird durch den zusätzlichen Spezifizierer `volatile` festgelegt, dass es zulässig ist, wenn der Wert durch einen derzeit mit dem Programm ausgeführten Prozess geändert wird.  Die Deklaration von `w` gibt an, dass das Programm den Wert nicht ändern kann, auf den gezeigt wird, und dass das Programm den Zeiger nicht ändern kann.  
  
```  
struct list *next, *previous; /* Uses the tag for list */  
```  
  
 Dieses Beispiel deklariert zwei Zeigervariablen, `next` und `previous`, die auf den Strukturtyp `list` zeigen.  Diese Deklaration kann vor der Definition des `list`\-Strukturtyps stehen \(siehe das nächste Beispiel\), sofern die `list`\-Typdefinition die gleiche Sichtbarkeit wie die Deklaration hat.  
  
```  
struct list   
{  
    char *token;  
    int count;  
    struct list *next;  
} line;  
```  
  
 Die `line`\-Variable hat den Strukturtyp namens `list`.  Der `list`\-Strukturtyp hat drei Member. Der erste Member ist ein Zeiger auf einen `char`\-Wert, der zweite ist ein `int`\-Wert, und der dritte ist ein Zeiger auf eine andere `list`\-Struktur.  
  
```  
struct id   
{  
    unsigned int id_no;  
    struct name *pname;  
} record;  
```  
  
 Die `record`\-Variable hat den `id`\-Strukturtyp.  `pname` wird als Zeiger auf einen anderen Strukturtyp namens `name` deklariert.  Diese Deklaration kann vor der Definition des `name`\-Typs stehen.  
  
## Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)