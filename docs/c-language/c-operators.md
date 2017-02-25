---
title: "C-Operatoren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assoziativität von Operatoren"
  - "Binäre Daten, Binäre Ausdrücke"
  - "Binäre Operatoren"
  - "Operatoren [C]"
  - "Symbole, Operatoren"
  - "Ternäre Operatoren"
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# C-Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die C\-Operatoren sind eine Teilmenge der [C\+\+\-Operatoren](../misc/cpp-operators.md).  
  
 Es gibt drei Typen von Operatoren:  Ein unärer Ausdruck umfasst entweder einen unären Operator, der einem Operanden vorangestellt wird, oder das `sizeof`\-Schlüsselwort, auf das ein Ausdruck folgt.  Der Ausdruck kann entweder der Name einer Variabel oder eines Umwandlungsausdrucks sein.  Wenn der Ausdruck ein Umwandlungsausdruck ist, muss er in Klammern eingeschlossen werden.  Ein binärer Ausdruck besteht aus zwei Operanden, die mit einem binären Operator verknüpft sind.  Ein ternärer Ausdruck besteht aus drei Operanden, die vom bedingten Ausdrucksoperator verknüpft sind.  
  
 C enthält die folgenden unären Operatoren:  
  
|Symbol|Name|  
|------------|----------|  
|**– ~ \!**|Negations\- und Ergänzungsoperatoren|  
|**\* &**|Dereferenzierungs\- und address\-of\-Operatoren|  
|`sizeof`|Größenoperator|  
|**\+**|Unärer Plus\-Operator|  
|**\+\+ ––**|Unäre Inkrement\- und Dekrementoperatoren|  
  
 Binäre Operatoren sind von links nach rechts angeordnet.  C stellt die folgenden binären Operatoren bereit:  
  
|Symbol|Name|  
|------------|----------|  
|**\* \/ %**|Multiplikative Operatoren|  
|**\+ –**|Additive Operatoren|  
|**\<\<**<br /> **\>\>**|Schiebeoperatoren|  
|**\<   \>   \<\=   \>\=   \=\=   \!\=**|Relationale Operatoren|  
|**&   &#124; ^**|Bitweise Operatoren|  
|**&&   &#124;&#124;**|Logische Operatoren|  
|**,**|Operator für sequenzielle Auswertung|  
  
 Der Basisoperator \(**:\>**\), der von älteren Versionen des 16\-Bit\-C\-Compilers von Microsoft unterstützt wird, ist in [Zusammenfassung der C\-Sprachsyntax](../c-language/c-language-syntax-summary.md) beschrieben.  
  
 Der bedingte Ausdrucksoperator hat einen niedrigeren Rang als binäre Ausdrücke und unterscheidet sich von ihnen darin, dass er rechtsassoziativ ist.  
  
 Zu Ausdrücken mit Operatoren zählen auch Zuweisungsausdrücke, die die unären oder binären Zuweisungsoperatoren verwenden.  Die unären Zuweisungsoperatoren sind die Inkrement\(`++`\)\- und Dekrement\(**––**\)\-Operatoren. Die binären Zuweisungsoperatoren sind die Einfachzuweisungsoperatoren \(**\=**\) und die Verbundzuweisungsoperatoren.  Jeder Verbundzuweisungsoperator ist eine Kombination aus einem anderen binären Operators mit dem Einfachzuweisungsoperator.  
  
## Siehe auch  
 [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md)