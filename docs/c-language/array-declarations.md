---
title: "Arraydeklarationen"
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
  - "Arrays [C++], Deklarieren"
  - "Deklarieren von Arrays"
  - "Mehrdimensionale Arrays"
ms.assetid: 5f958b97-cef0-4058-bbc6-37c460aaed9b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Arraydeklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Arraydeklaration" benennt das Array und gibt den Typ der Elemente an.  Hiermit kann auch die Anzahl von Elementen im Array definiert werden.  Eine Variable mit Arraytyp wird als Zeiger auf den Typ der Arrayelemente betrachtet.  
  
## Syntax  
 `declaration`:  
 *declaration\-specifiers init\-declarator\-list*  opt               **;**  
  
 *init\-declarator\-list*:  
 *init\-declarator*  
  
 *init\-declarator\-list* **,**  *init\-declarator*  
  
 *init\-declarator*:  
 *declarator*  
  
 *declarator*  **\=**  *initializer*  
  
 `declarator`:  
 *pointer*  opt *direct\-declarator*  
  
 *direct\-declarator*:  
 *direct\-declarator*  **\[**  *constant\-expression*  opt **\]**  
  
 Da *constant\-expression* optional ist, hat die Syntax zwei Formen:  
  
-   Die erste Form definiert eine Arrayvariable.  Das *constant\-expression*\-Argument innerhalb der Klammern gibt die Anzahl von Elementen im Array an.  *constant\-expression*, falls vorhanden, muss einen ganzzahligen Typ und einen Wert aufweisen, der größer null ist.  Jedes Element weist den Typ auf, der von *type\-specifier* angegeben ist, der ein beliebiger Typ außer `void` sein kann.  Ein Arrayelement darf kein Funktionstyp sein.  
  
-   Die zweite Form deklariert eine Variable, die an einer anderen Stelle definiert wurde.  Sie lässt das *constant\-expression*\-Argument in Klammern weg, aber nicht die Klammern.  Sie können diese Form nur dann verwenden, wenn Sie das Array zuvor initialisiert und als Parameter oder als Verweis auf ein Array deklariert haben, das explizit an anderer Stelle im Programm definiert ist.  
  
 Bei beiden Formen vergibt *direct\-declarator* den Namen der Variablen und kann den Typ der Variablen ändern.  Die Klammern \(**\[ \]**\) nach *direct\-declarator* ändern den Deklarator in einen Arraytyp.  
  
 Typqualifizierer können in der Deklaration eines Objekts des Arraytyps enthalten sein, die Qualifizierer gelten jedoch für die Elemente und nicht für das Array selbst.  
  
 Sie können ein Array von Arrays \(ein "mehrdimensionales" Array\) deklarieren, indem Sie der Arraydeklaration eine Liste konstanter Ausdrücke in Klammern in dieser Form nachstellen:  
  
```  
  
type-specifier declarator [constant-expression] [constant-expression] ...  
```  
  
 Jeder *constant\-expression* in eckigen Klammern definiert die Anzahl von Elementen in der angegebenen Dimension: zweidimensionale Arrays haben zwei Ausdrücke in Klammern, dreidimensionale Arrays haben drei usw.  Sie können den ersten konstanten Ausdruck weglassen, wenn Sie das Array initialisiert und es als Parameter oder als Verweis auf ein Array deklariert haben, das explizit an anderer Stelle im Programm definiert ist.  
  
 Sie können Arrays von Zeigern auf verschiedene Objekttypen definieren, indem Sie komplexe Deklaratoren verwenden, wie in [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md) beschrieben.  
  
 Arrays werden zeilenweise gespeichert.  Zum Beispiel besteht das nächste Array aus zwei Zeilen mit jeweils drei Spalten:  
  
```  
char A[2][3];  
```  
  
 Die drei Spalten der ersten Zeile werden zuerst gespeichert, danach folgen die drei Spalten der zweiten Zeile.  Dies bedeutet, dass sich der letzte Feldindex am schnellsten unterscheidet.  
  
 Um auf ein einzelnes Element eines Arrays zu verweisen, verwenden Sie einen Indexausdruck, wie unter [Postfix\-Operatoren](../c-language/postfix-operators.md) beschrieben.  
  
## Beispiele  
 Diese Beispiele veranschaulichen Arraydeklarationen:  
  
```  
float matrix[10][15];  
```  
  
 Das zweidimensionale Array namens `matrix` verfügt über 150 Elemente, von denen jedes einen **Gleitkomma**\-Typ besitzt.  
  
```  
struct {  
    float x, y;  
} complex[100];  
```  
  
 Dies ist eine Deklaration eines Arrays von Strukturen.  Dieses Array weist 100 Elemente auf. Jedes Element ist eine Struktur, die zwei Member enthält.  
  
```  
extern char *name[];  
```  
  
 Diese Anweisung deklariert den Typ und den Namen eines Arrays von Zeigern auf `char`.  Die tatsächliche Definition von `name` ist an anderer Stelle zu finden.  
  
 **Microsoft\-spezifisch**  
  
 Der Typ einer Ganzzahl, die zum Speichern der maximalen Größe eines Arrays erforderlich ist, d. h. die Größe von **size\_t**.  **size\_t** ist in der Headerdatei STDDEF.H definiert und ein `unsigned int` mit dem Bereich 0x00000000 bis 0x7CFFFFFF.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)