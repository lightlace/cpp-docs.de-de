---
title: C-Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f90f25d52a2555eb92938dd29ebb7e5bfc6e96a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="c-operators"></a>C-Operatoren
Die C-Operatoren sind eine Teilmenge der [integrierten C++-Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md).  
  
 Es gibt drei Typen von Operatoren: Ein unärer Ausdruck umfasst entweder einen unären Operator, der einem Operanden vorangestellt wird, oder das `sizeof`-Schlüsselwort, auf das ein Ausdruck folgt. Der Ausdruck kann entweder der Name einer Variabel oder eines Umwandlungsausdrucks sein. Wenn der Ausdruck ein Umwandlungsausdruck ist, muss er in Klammern eingeschlossen werden. Ein binärer Ausdruck besteht aus zwei Operanden, die mit einem binären Operator verknüpft sind. Ein ternärer Ausdruck besteht aus drei Operanden, die vom bedingten Ausdrucksoperator verknüpft sind.  
  
 C enthält die folgenden unären Operatoren:  
  
|Symbol|name|  
|------------|----------|  
|**- ~ !**|Negations- und Ergänzungsoperatoren|  
|**\* &**|Dereferenzierungs- und Address-of-Operatoren|  
|`sizeof`|Größenoperator|  
|**+**|Unärer Plus-Operator|  
|**++ --**|Unäre Inkrement- und Dekrementoperatoren|  
  
 Binäre Operatoren sind von links nach rechts angeordnet. C stellt die folgenden binären Operatoren bereit:  
  
|Symbol|name|  
|------------|----------|  
|**\* / %**|Multiplikative Operatoren|  
|**+ -**|Additive Operatoren|  
|**<\< >>**|Schiebeoperatoren|  
|**\<   >   \<=   >=   ==   !=**|Relationale Operatoren|  
|**&   &#124; ^**|Bitweise Operatoren|  
|**&&   &#124;&#124;**|Logische Operatoren|  
|**,**|Operator für sequenzielle Auswertung|  
  
 Der Basisoperator (**:>**), der von älteren Versionen des 16-Bit-C-Compilers von Microsoft unterstützt wird, ist in [Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md) beschrieben.  
  
 Der bedingte Ausdrucksoperator hat einen niedrigeren Rang als binäre Ausdrücke und unterscheidet sich von ihnen darin, dass er rechtsassoziativ ist.  
  
 Zu Ausdrücken mit Operatoren zählen auch Zuweisungsausdrücke, die die unären oder binären Zuweisungsoperatoren verwenden. Die unären Zuweisungsoperatoren sind die Operatoren für Inkrement (`++`) und Dekrement (**--**). Die binären Zuweisungsoperatoren sind die Einfachzuweisungsoperatoren (**=**) und die Verbundzuweisungsoperatoren. Jeder Verbundzuweisungsoperator ist eine Kombination aus einem anderen binären Operators mit dem Einfachzuweisungsoperator.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md)