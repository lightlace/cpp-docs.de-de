---
title: "sizeof-Operator (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sizeof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sizeof-Operator"
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# sizeof-Operator (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `sizeof`\-Operator gibt die Größe des Speichers in Bytes an, die erforderlich ist, um ein Objekt dieses Operandentyps zu speichern.  Mithilfe dieses Operators können Sie es vermeiden, rechnerabhängige Datengrößen in Ihren Programmen anzugeben.  
  
## Syntax  
  
```  
  
      sizeof unary-expression  
sizeof ( type-name )  
```  
  
## Hinweise  
 Der Operand ist entweder ein Bezeichner, der ein *unary\-expression* ist, oder ein Typumwandlungsausdruck \(d. h. ein Typspezifizierer in Klammern\).  *unary\-expression* kann kein Bitfeldobjekt, keinen unvollständigen Typ und keinen Funktionskennzeichner darstellen.  Das Ergebnis ist eine vorzeichenlose Ganzzahlkonstante.  Der Standardheader STDDEF.H definiert diesen Typ als **size\_t**.  
  
 Wenn Sie den Operator `sizeof` auf einen Arraybezeichner anwenden, stellt das Ergebnis die Größe des gesamten Arrays und nicht nur die Größe des Zeigers dar, der vom Arraybezeichner dargestellt wird.  
  
 Wenn Sie den Operator `sizeof` auf den Namen eines Struktur\- oder Union\-Typs oder auf den Bezeichner eines Struktur\- oder Union\-Typs anwenden, stellt das Ergebnis die Anzahl von Bytes in der Struktur oder Union einschließlich interner und nachfolgender Füllzeichen dar.  Diese Größe enthält möglicherweise interne und nachfolgende Füllzeichen, die verwendet werden, um die Member der Struktur oder Union an Arbeitsspeichergrenzen auszurichten.  Daher stimmt das Ergebnis möglicherweise nicht mit der Größe überein, die durch Addieren der Speicheranforderungen der einzelnen Member berechnet wird.  
  
 Wenn ein Array ohne Größenangabe das letzte Element einer Struktur ist, gibt der `sizeof`\-Operator die Größe der Struktur ohne das Array zurück.  
  
```  
buffer = calloc(100, sizeof (int) );  
```  
  
 In diesem Beispiel wird mit dem `sizeof`\-Operator die Größe von einem `int` \(die computerspezifisch ist\) als Argument an eine Laufzeitfunktion mit dem Namen `calloc` übergeben.  Der Wert, der von dieser Funktion zurückgegeben wird, wird in `buffer` gespeichert.  
  
```  
static char *strings[] ={  
          "this is string one",  
          "this is string two",  
          "this is string three",  
         };  
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );   
```  
  
 In diesem Beispiel ist `strings` ein Array von Zeigern auf `char`.  Die Anzahl von Zeigern ist die Anzahl von Elementen im Array, ist jedoch nicht festgelegt.  Es ist einfach, die Anzahl von Zeigern zu ermitteln, indem der `sizeof`\-Operator verwendet wird, um die Anzahl von Elementen im Array zu berechnen.  Der ganzzahlige **const**\-Wert `string_no` wird mit dieser Zahl initialisiert.  Da es sich um einen **const**\-Wert handelt, kann `string_no` nicht geändert werden.  
  
## Siehe auch  
 [C\+\+\-Operatoren](../misc/cpp-operators.md)