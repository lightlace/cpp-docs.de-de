---
title: sizeof-Operator (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sizeof
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 70826d03-3451-41e4-bebb-a820ae66d53f
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 11fa4acae05c5488ce1d90873ec816744c7e83df
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="sizeof-operator-c"></a>sizeof-Operator (C)
Der `sizeof`-Operator gibt die Größe des Speichers in Bytes an, die erforderlich ist, um ein Objekt dieses Operandentyps zu speichern. Mithilfe dieses Operators können Sie es vermeiden, rechnerabhängige Datengrößen in Ihren Programmen anzugeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
sizeof unary-expression  
sizeof ( type-name )  
```  
  
## <a name="remarks"></a>Hinweise  
Der Operand ist entweder ein Bezeichner, bei dem es sich um einen *unären Ausdruck* (unary-expression) handelt, oder ein Typumwandlungsausdruck (d.h. ein Typspezifizierer in Klammern). *unary-expression* kann kein Bitfeldobjekt, keinen unvollständigen Typ und keinen Funktionskennzeichner darstellen. Das Ergebnis ist eine vorzeichenlose Ganzzahlkonstante. Der Standardheader STDDEF.H definiert diesen Typ als **size_t**.  
  
Wenn Sie den Operator `sizeof` auf einen Arraybezeichner anwenden, stellt das Ergebnis die Größe des gesamten Arrays und nicht nur die Größe des Zeigers dar, der vom Arraybezeichner dargestellt wird.  
  
Wenn Sie den Operator `sizeof` auf den Namen eines Struktur- oder Union-Typs oder auf den Bezeichner eines Struktur- oder Union-Typs anwenden, stellt das Ergebnis die Anzahl von Bytes in der Struktur oder Union einschließlich interner und nachfolgender Füllzeichen dar. Diese Größe enthält möglicherweise interne und nachfolgende Füllzeichen, die verwendet werden, um die Member der Struktur oder Union an Arbeitsspeichergrenzen auszurichten. Daher stimmt das Ergebnis möglicherweise nicht mit der Größe überein, die durch Addieren der Speicheranforderungen der einzelnen Member berechnet wird.  
  
Wenn ein Array ohne Größenangabe das letzte Element einer Struktur ist, gibt der `sizeof`-Operator die Größe der Struktur ohne das Array zurück.  
  
```  
buffer = calloc(100, sizeof (int) );  
```  
  
In diesem Beispiel wird mit dem `sizeof`-Operator die Größe von einem `int` (die computerspezifisch ist) als Argument an eine Laufzeitfunktion mit dem Namen `calloc` übergeben. Der Wert, der von dieser Funktion zurückgegeben wird, wird in `buffer` gespeichert.  
  
```  
static char *strings[] = {  
      "this is string one",  
      "this is string two",  
      "this is string three",  
   };  
const int string_no = ( sizeof strings ) / ( sizeof strings[0] );   
```  
  
In diesem Beispiel ist `strings` ein Array von Zeigern auf `char`. Die Anzahl von Zeigern ist die Anzahl von Elementen im Array, ist jedoch nicht festgelegt. Es ist einfach, die Anzahl von Zeigern zu ermitteln, indem der `sizeof`-Operator verwendet wird, um die Anzahl von Elementen im Array zu berechnen. Der ganzzahlige **const**-Wert `string_no` wird mit dieser Zahl initialisiert. Da es sich um einen **const**-Wert handelt, kann `string_no` nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
[C-Operatoren](c-operators.md)  
[Integrierte C++-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
  
