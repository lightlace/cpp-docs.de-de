---
title: Union-Deklarationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c52752c1e05cb3c9f2b18a827fb493ba503ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="union-declarations"></a>Union-Deklarationen
Eine „Unionsdeklaration“ gibt einen Satz Variablenwerte und optional ein Tag an, der die Union benennt. Die Variablenwerte werden als "Member" der Union bezeichnet und können unterschiedliche Typen aufweisen. Unions ähneln varianten Datensätzen in anderen Sprachen.  
  
## <a name="syntax"></a>Syntax  
 *struct-or-union-specifier*:  
 *struct-or-union identifier* opt **{** *struct-declaration-list* **}**  
  
 *struct-or-union identifier*  
  
 *struct-or-union*:  
 **struct**  
  
 **union**  
  
 *struct-declaration-list*:  
 *struct-declaration*  
  
 *struct-declaration-list struct-declaration*  
  
 Der Unioninhalt wird definiert als  
  
 *struct-declaration*:  
 *specifier-qualifier-list struct-declarator-list*  **;**  
  
 *specifier-qualifier-list*:  
 *type-specifier specifier-qualifier-list* opt  
  
 *type-qualifier specifier-qualifier-list* opt  
  
 *struct-declarator-list*:  
 *struct-declarator*  
  
 *struct-declarator-list*  **,**  *struct-declarator*  
  
 Eine Variable des Typs **Union** speichert einen der Werte, die von diesem Typ definiert sind. Die gleichen Regeln steuern Struktur- und Uniondeklarationen. Unions können auch Bitfelder aufweisen.  
  
 Member von Unions können nicht nicht über einen unvollständigen Typ, `void`-Typ oder Funktionstyp verfügen. Daher können Member keine Instanz der Union sein, können aber Zeiger auf den Uniontyp sein, der deklariert wird.  
  
 Eine Uniontypdeklaration ist nur eine Vorlage. Arbeitsspeicher wird nicht reserviert, bis die Variable deklariert ist.  
  
> [!NOTE]
>  Wenn eine Union von zwei Typen deklariert wird und ein Wert gespeichert ist, aber mit dem anderen Typ auf die Union zugegriffen wird, sind die Ergebnisse unzuverlässig. Beispielsweise wird eine Union von **float** und `int` deklariert. Ein **float**-Wert wird gespeichert, aber später greift das Programm auf den Wert als `int` zu. In einer solchen Situation ist der Wert der internen Speicherung von **float**-Werten abhängig. Der Ganzzahlwert wäre nicht zuverlässig.  
  
## <a name="examples"></a>Beispiele  
 Nachstehend einige Beispiele für Unions:  
  
```  
union sign   /* A definition and a declaration */  
{  
    int svar;  
    unsigned uvar;  
} number;  
```  
  
 In diesem Beispiel wird eine Unionvariable mit dem `sign`-Typ definiert und die Variable `number` mit zwei Membern deklariert: `svar`, eine ganze Zahl mit Vorzeichen, und `uvar`, eine ganze Zahl ohne Vorzeichen. Diese Deklaration ermöglicht das Speichern des aktuellen Werts von `number` als Wert mit Vorzeichen oder ohne Vorzeichen. Das Tag, das diesem Uniontyp zugeordnet ist, ist `sign`.  
  
```  
union               /* Defines a two-dimensional */  
{                   /*  array named screen */  
    struct      
    {   
      unsigned int icon : 8;    
      unsigned color : 4;  
    } window1;  
    int screenval;  
} screen[25][80];  
```  
  
 Das `screen`-Array enthält 2.000 Elemente. Jedes Element des Arrays ist eine einzelne Union mit zwei Membern: `window1` und `screenval`. Der Member `window1` ist eine Struktur mit zwei Bitfeldmembern, `icon` und `color`. Der `screenval`-Member ist ein `int`. Zu jedem Zeitpunkt enthält jedes union-Element entweder `int`, dargestellt durch `screenval`, oder die Struktur, dargestellt durch `window1`.  
  
 **Microsoft-spezifisch**  
  
 Geschachtelte Unions können anonym deklariert werden, wenn sie Member einer anderen Struktur oder Union sind. Dies ist ein Beispiel für eine namenlose Union:  
  
```  
struct str  
{  
    int a, b;  
    union            / * Unnamed union */  
    {  
      char c[4];  
      long l;  
      float f;  
   };  
   char c_array[10];  
} my_str;  
.  
.  
.  
my_str.l == 0L;  /* A reference to a field in the my_str union */  
```  
  
 Unions werden häufig in einer Struktur geschachtelt, die ein Feld enthält, das den Typ der Daten angibt, die in der Union zu einem bestimmten Zeitpunkt enthalten sind. Dies ist ein Beispiel für die Deklaration einer solchen Union:  
  
```  
struct x  
{  
    int type_tag;  
    union  
    {  
      int x;  
      float y;  
    }  
}  
```  
  
 Weitere Informationen über den Verweis auf Unions finden Sie unter [Struktur- und Union-Elemente](../c-language/structure-and-union-members.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)