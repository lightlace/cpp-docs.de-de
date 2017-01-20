---
title: "Typedef-Deklarationen"
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
  - "Deklarationen, typedef"
  - "typedef-Deklarationen"
  - "Typen [C], Deklarationen"
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Typedef-Deklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine typedef\-Deklaration ist eine Deklaration mit typedef als Speicherklasse.  Der Deklarator wird ein neuer Typ.  Sie können typedef\-Deklarationen verwenden, um kürzere oder aussagekräftigere Namen für Typen zu erstellen, die bereits von der C\-Programmiersprache definiert sind, oder für Typen, die deklariert wurden.  Mithilfe von typedef\-Namen können Sie die Implementierungsdetails kapseln, die sich möglicherweise ändern.  
  
 Eine typedef\-Deklaration wird auf die gleiche Weise wie eine Variable oder eine Funktionsdeklaration interpretiert. Der Bezeichner wird allerdings ein Synonym für den Typ, statt den von der Deklaration angegebenen Typ anzunehmen.  
  
## Syntax  
 `declaration`:  
 *declaration\-specifiers init\-declarator\-list*  opt               **;**  
  
 *declaration\-specifiers*:  
 *storage\-class\-specifier declaration\-specifiers*  opt  
  
 *type\-specifier declaration\-specifiers*  opt  
  
 *type\-qualifier declaration\-specifiers*  opt  
  
 *storage\-class\-specifier*:  
 `typedef`  
  
 *type\-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct\-or\-union\-specifier*  
  
 *enum\-specifier*  
  
 *typedef\-name*  
  
 *typedef\-name*:  
 *identifier*  
  
 Beachten Sie, dass in einer typedef\-Deklaration keine Typen erstellt werden.  Es werden Synonyme für vorhandene Typen oder Namen für Typen erstellt, die auf andere Weise angegeben werden können.  Wenn ein typedef\-Name als Typspezifizierer verwendet wird, kann er nur mit bestimmten Typspezifizierern kombiniert werden.  Zulässige Modifizierer sind **const** und `volatile`.  
  
 Typedef\-Namen verwenden denselben Namespace wie gewöhnliche Bezeichner \(weitere Informationen finden Sie unter [Namespaces](../c-language/name-spaces.md)\).  Aus diesem Grund kann ein Programm einen typedef\-Namen und einen Bezeichner für den lokalen Gültigkeitsbereich mit dem gleichen Namen aufweisen.  Beispiel:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Wenn ein Bezeichner für den lokalen Gültigkeitsbereich mit dem gleichen Namen wie eine typedef deklariert wird oder wenn ein Member einer Struktur oder Union im gleichen Gültigkeitsbereich oder im inneren Bereich deklariert wird, muss der Typspezifizierer angegeben werden.  Das folgende Beispiel veranschaulicht diese Einschränkung:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Um den `FlagType`\-Namen für einen Bezeichner, einen Strukturmember oder einen Unionsmember wiederzuverwenden, muss der Typ angegeben werden:  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 Folgendes ist nicht ausreichend:  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 Das liegt daran, dass `FlagType` als ein Teil des Typs angesehen wird, und nicht als Bezeichner, der neu deklariert wird.  Diese Deklaration wird als ungültige Deklaration angesehen, wie etwa  
  
```  
int;  /* Illegal declaration */  
```  
  
 Sie können einen beliebigen Typ mit typedef deklarieren, einschließlich Zeiger\-, Funktions\- und Arraytypen.  Sie können einen typedef\-Namen für einen Zeiger auf einen Struktur\- oder einen Union\-Typ deklarieren, bevor Sie den Struktur\- oder Union\-Typ definieren, solange die Definition die gleiche Sichtbarkeit wie die Deklaration aufweist.  
  
 Typedef\-Namen können verwendet werden, um die Codelesbarkeit zu verbessern.  Alle drei der folgenden Deklarationen von `signal` geben genau den gleichen Typ an, wobei der erste keine typedef\-Namen verwendet.  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## Beispiele  
 Die folgenden Beispiele veranschaulichen typedef\-Deklarationen:  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 Beachten Sie, dass `WHOLE` jetzt in einer Variablendeklaration wie `WHOLE i;` oder `const WHOLE i;` verwendet werden kann.  Die Deklaration `long WHOLE i;` ist hingegen ungültig.  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 Diese Anweisung deklariert `GROUP` als Strukturtyp mit drei Membern.  Da auch ein Strukturtag, `club`, angegeben wird, kann entweder der typedef\-Name \(`GROUP`\) oder das Strukturtag in Deklarationen verwendet werden.  Sie müssen das struct\-Schlüsselwort mit dem Tag verwenden. Das struct\-Schlüsselwort kann nicht mit dem typedef\-Namen verwenden werden.  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 Der Typ `PG` wird als Zeiger auf den `GROUP`\-Typ deklariert, der wiederum als Strukturtyp definiert ist.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 In diesem Beispiel wird der Typ `DRAWF` für eine Funktion bereitgestellt, die keinen Wert zurückgibt und zwei int\-Argumente akzeptiert.  Dies bedeutet beispielsweise, dass die Deklaration  
  
```  
DRAWF box;   
```  
  
 äquivalent ist zur Deklaration  
  
```  
void box( int, int );  
```  
  
## Siehe auch  
 [\(NOTINBUILD\)typedef Specifier](assetId:///cc96cf26-ba93-4179-951e-695d1f5fdcf1)