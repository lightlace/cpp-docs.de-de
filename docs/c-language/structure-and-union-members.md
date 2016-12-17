---
title: "Struktur- und Unionmember"
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
  - ". Operator"
  - "->-Operator, Struktur- und Unionmember"
  - "Punktoperator (.)"
  - "Memberauswahloperatoren"
  - "Operatoren [C], Memberauswahl"
  - "Verweisen auf Strukturmember"
  - "Strukturmemberauswahl"
  - "Strukturmember, Verweisen"
ms.assetid: bb1fe304-af49-4f98-808d-afdc99b3e319
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Struktur- und Unionmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Memberauswahlausdruck bezieht sich auf Member von Strukturen und Unions.  Ein solcher Ausdruck hat den Wert und Typ des ausgewählten Members.  
  
```  
  
        postfix-expression . identifier  
postfix-expression –> identifier  
```  
  
 Diese Liste beschreibt die zwei Arten von Memberauswahlausdrücken:  
  
1.  Bei der ersten Form stellt *postfix\-expression* einen Wert des Typs `struct` oder **union** dar, mit *identifier* wird ein Member der angegebenen Struktur oder Union benannt.  Der Wert des Vorgangs entspricht *identifier* und ist ein L\-Wert, sofern *postfix\-expression* ein L\-Wert ist.  Weitere Informationen erhalten Sie unter [L\-Wert\-und R\-Wert\-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
2.  Bei der zweiten Form stellt *postfix\-expression* einen Zeiger auf eine Struktur oder Union dar, mit *identifier* wird ein Member der angegebenen Struktur oder Union benannt.  Der Wert entspricht *identifier* und ist ein L\-Wert.  
  
 Die beiden Formen der Memberauswahlausdrücke verfügen über ähnliche Auswirkungen.  
  
 Tatsächlich ist ein Ausdruck, der den Memberauswahloperator \(**–\>**\) enthält, eine Kurznotationsversion eines Ausdrucks mithilfe des Punkts \(**.**\), wenn der Ausdruck vor dem Punkt aus dem Dereferenzierungsoperator\(**\***\) besteht, der auf einen Zeigerwert angewendet wird.  Daher eignet sich  
  
```  
  
expression –> identifier  
```  
  
 für die folgende Syntax:  
  
```  
  
(*  
expression  
) . identifier  
```  
  
 wenn *expression* ein Zeigerwert ist.  
  
## Beispiele  
 Die folgenden Beispiele beziehen sich auf diese Strukturdeklaration.  Weitere Informationen zum Dereferenzierungsoperator \(**\***\), der in diesen Beispielen verwendet wird, finden Sie unter [Dereferenzierungs\- und Address\-of\-Operatoren](../c-language/indirection-and-address-of-operators.md).  
  
```  
struct pair   
{  
    int a;  
    int b;  
    struct pair *sp;  
} item, list[10];  
```  
  
 Ein Memberauswahlausdruck für die `item`\-Struktur sieht wie folgt aus:  
  
```  
item.sp = &item;  
```  
  
 Im obigen Beispiel wird die Adresse der `item`\-Struktur dem `sp`\-Member der Struktur zugewiesen.  Dies bedeutet, dass `item` einen Zeiger auf sich selbst enthält.  
  
```  
(item.sp)–>a = 24;  
```  
  
 In diesem Beispiel wird der Zeigerausdruck `item.sp` mit dem Memberauswahloperator \(**–\>**\) verwendet, um dem Member `a` einen Wert zuzuweisen.  
  
```  
list[8].b = 12;  
```  
  
 Diese Anweisung zeigt, wie ein einzelner Strukturmember aus einem Array von Strukturen ausgewählt wird.  
  
## Siehe auch  
 [Operatoren für den Memberzugriff: . und \-\>](../cpp/member-access-operators-dot-and.md)