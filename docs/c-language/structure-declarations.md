---
title: "Strukturdeklarationen"
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
  - "Anonyme Strukturen"
  - "Eingebettete Strukturen"
  - "Strukturdeklarationen"
  - "Strukturmember"
  - "Typen [C], Deklarationen"
ms.assetid: 5be3be77-a236-4153-b574-7aa77675df7f
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Strukturdeklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Strukturdeklaration" benennt einen Typ und gibt eine Sequenz von Variablenwerten an \(so genannte "Member" oder "Felder" der Struktur\), die unterschiedliche Typen aufweisen können.  Ein optionaler Bezeichner, "Tag" genannt, gibt den Namen des Strukturtyps an und kann in nachfolgenden Verweisen für den Strukturtyp verwendet werden.  Eine Variable des Strukturtyps enthält die gesamte Sequenz, die durch diesen Typ definiert ist.  Strukturen in C ähneln den Typen, die als "Datensätze" in anderen Sprachen bekannt sind.  
  
## Syntax  
 *struct\-or\-union\-specifier*:  
 *struct\-or\-union identifier*  opt **{** *struct\-declaration\-list* **}**  
  
 *struct\-or\-union identifier*  
  
 *struct\-or\-union*:  
 **struct**  
  
 **union**  
  
 *struct\-declaration\-list*:  
 *struct\-declaration*  
  
 *struct\-declaration\-list struct\-declaration*  
  
 Der Strukturinhalt wird folgendermaßen definiert  
  
 *struct\-declaration*:  
 *specifier\-qualifier\-list struct\-declarator\-list*  **;**  
  
 *specifier\-qualifier\-list*:  
 *type\-specifier specifier\-qualifier\-list*  opt  
  
 *type\-qualifier specifier\-qualifier\-list*  opt  
  
 *struct\-declarator\-list*:  
 *struct\-declarator*  
  
 *struct\-declarator\-list*  **,**  *struct\-declarator*  
  
 *struct\-declarator*:  
 `declarator`  
  
 Die Deklaration eines Strukturtyps hält keinen Platz für eine Struktur bereit.  Es ist nur eine Vorlage für spätere Deklarationen von Strukturvariablen.  
  
 Ein zuvor definierter *Identifier* \(Tag\) kann verwendet werden, um auf einen Strukturtyp zu verweisen, der an anderer Stelle definiert ist.  In diesem Fall kann *struct\-declaration\-list* nicht wiederholt werden, solange die Definition sichtbar ist.  Deklarationen von Zeigern auf Strukturen und Typedefs für Strukturtypen können das Strukturtag verwenden, bevor der Strukturtyp definiert ist.  Allerdings muss die Strukturdefinition vor jeder tatsächlichen Verwendung der Größe der Felder gefunden werden.  Dies ist eine unvollständige Definition des Typs und des Typ\-Tags.  Damit diese Definition abgeschlossen werden kann, muss eine Typdefinition später im gleichen Bereich angezeigt werden.  
  
 Mit *struct\-declaration\-list* werden die Typen und Namen der Strukturmember angegeben.  Ein *struct\-declaration\-list*\-Argument enthält mindestens eine Variable oder Bitfelddeklaration.  
  
 Jede Variable, die in der *struct\-declaration\-list* deklariert wurde, wird als Member des Strukturtyps definiert.  Variablendeklarationen in *struct\-declaration\-list* verfügen über das gleiche Format wie andere Variablendeklarationen, die in diesem Abschnitt erläutert werden, mit der Ausnahme, dass die Deklarationen keine Speicherklassenspezifizierer oder \-initialisierer enthalten dürfen.  Die Strukturmember können mit Ausnahme des Typs `void` alle Variablentypen, einen unvollständigen Typ oder einen Funktionstyp aufweisen.  
  
 Ein Member kann nicht mit dem Typ oder der Struktur deklariert werden, in dem\/der er enthalten ist.  Allerdings kann ein Member als Zeiger auf den Strukturtyp deklariert werden, in dem er angezeigt wird, solange der Strukturtyp über einen Tag verfügt.  Dadurch können Sie verknüpfte Listen von Strukturen erstellen.  
  
 Für Strukturen gilt derselbe Gültigkeitsbereich wie für andere Bezeichner.  Strukturbezeichner müssen sich von anderen Struktur\-, Union\- und Enumerations\-Tags derselben Sichtbarkeit unterscheiden.  
  
 Jede *struct\-declaration* in einer *struct\-declaration\-list* muss in der Liste eindeutig sein.  Allerdings müssen sich Bezeichnernamen in einer *struct\-declaration\-list* nicht von gewöhnlichen Variablennamen oder Bezeichnern in anderen Strukturdeklarationslisten unterscheiden.  
  
 Auf geschachtelte Strukturen kann auch so zugegriffen werden, als wären sie auf der Dateibereichsebene deklariert wurden.  Beispielsweise bei dieser Deklaration:  
  
```  
struct a  
{  
    int x;  
    struct b  
    {  
      int y;  
    } var2;  
} var1;  
```  
  
 diese Deklarationen sind beide gültig:  
  
```  
struct a var3;  
struct b var4;  
```  
  
## Beispiele  
 Diese Beispiele veranschaulichen Strukturdeklarationen:  
  
```  
struct employee   /* Defines a structure variable named temp */  
{  
    char name[20];  
    int id;  
    long class;  
} temp;  
```  
  
 Die `employee`\-Struktur hat drei Member: `name`, `id` und `class`.  Der `name`\-Member ist ein Array mit 20 Elementen, und `id` und `class` sind einfache Member vom Typ `int` und **long**.  Der Bezeichner `employee` ist der Strukturbezeichner.  
  
```  
struct employee student, faculty, staff;  
```  
  
 Dieses Beispiel definiert drei Strukturvariablen: `student`, `faculty` und `staff`.  Jede Struktur verfügt über die gleiche Liste von drei Membern.  Member müssen den Strukturtyp `employee` im vorherigen Beispiel definiert haben.  
  
```  
struct           /* Defines an anonymous struct and a */  
{                /* structure variable named complex  */  
    float x, y;  
} complex;  
```  
  
 Die `complex`\-Struktur verfügt über zwei Member vom Typ **float**, `x` und `y`.  Der Strukturtyp hat kein Tag und ist somit unbenannt oder anonym.  
  
```  
struct sample   /* Defines a structure named x */  
{  
    char c;  
    float *pf;  
    struct sample *next;  
} x;  
```  
  
 Die ersten beiden Member der Struktur sind eine `char`\-Variable und ein Zeiger auf einen **float**\-Wert.  Der dritte Member, `next`, wird als Zeiger auf den definierten Strukturtyp deklariert \(`sample`\).  
  
 Anonyme Strukturen können nützlich sein, wenn der angegebene Tag nicht benötigt wird.  Dies ist der Fall, wenn eine Deklaration alle Strukturinstanzen definiert.  Beispiel:  
  
```  
struct  
{  
    int x;  
    int y;  
} mystruct;  
```  
  
 Eingebettete Strukturen sind häufig anonym.  
  
```  
struct somestruct  
{  
    struct    /* Anonymous structure */  
    {  
        int x, y;  
    } point;  
    int type;  
} w;  
```  
  
 **Microsoft\-spezifisch**  
  
 Der Compiler lässt ein Array ohne Größenangabe oder ein Array der Größe 0 \(null\) als letzten Member einer Struktur zu.  Dies kann hilfreich sein, wenn sich die Größe eines konstanten Arrays in verschiedenen Situationen unterscheidet.  Die Deklaration einer solchen Struktur sieht wie folgt aus:  
  
 `struct` *identifier***{** *set\-of\-declarations* *type array\-name***\[ \];};**  
  
 Arrays ohne Größenangabe können nur als letzter Member einer Struktur angegeben werden.  Die Strukturen, die Arraydeklarationen ohne Größenangabe enthalten, können in andere Strukturen geschachtelt werden, solange keine weiteren Member in anderen einschließenden Strukturen deklariert werden.  Arrays von solchen Strukturen sind nicht zulässig.  Der `sizeof`\-Operator nimmt bei Anwendung auf eine Variable dieses Typs oder auf den Typ selbst 0 für die Größe des Arrays an.  
  
 Strukturdeklarationen können auch ohne Deklaration angegeben werden, wenn diese Member einer anderen Struktur oder Union sind.  Die Feldnamen werden in die einschließende Struktur hochgestuft.  Eine namenlose Struktur sieht beispielsweise wie folgt aus:  
  
```  
struct s  
{  
    float y;  
    struct  
    {  
        int a, b, c;  
    };  
    char str[10];  
} *p_s;  
.  
.  
.  
p_s->b = 100;  /* A reference to a field in the s structure */  
```  
  
 Weitere Informationen zu Strukturverweisen erhalten Sie unter [Struktur\- und Unionmember](../c-language/structure-and-union-members.md).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)