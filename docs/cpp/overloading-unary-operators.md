---
title: "&#220;berladen von un&#228;ren Operatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inkrementoperatoren, Überladen"
  - "Operatoren [C++], Unär"
  - "plus-Operator"
  - "Überladen von Dereferenzierungsoperatoren"
  - "Neu definierbare unäre Operatoren"
  - "Unäre Operatoren"
  - "Unäre Operatoren, Minus"
  - "Unäre Operatoren, Plus"
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berladen von un&#228;ren Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die unären Operatoren, die überladen werden können, sind Folgende:  
  
1.  `!` \([logisches NOT](../cpp/logical-negation-operator-exclpt.md)\)  
  
2.  `&` \([Adresse von](../cpp/address-of-operator-amp.md)\)  
  
3.  `~` \([Einerkomplement](../cpp/one-s-complement-operator-tilde.md)\)  
  
4.  `*` \([Zeigerdereferenzierung](../cpp/indirection-operator-star.md)\)  
  
5.  `+` \([unäres Plus](../cpp/additive-operators-plus-and.md)\)  
  
6.  `-` \([unäre Negation](../cpp/additive-operators-plus-and.md)\)  
  
7.  `++` \([Inkrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)\)  
  
8.  `--` \([Dekrement](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)\)  
  
9. Konvertierungsoperatoren  
  
 Die Postfixinkrement\- und Dekrementoperatoren \(`++` and **––**\) werden in [Increment and Decrement](../cpp/increment-and-decrement-operator-overloading-cpp.md) getrennt behandelt.  
  
 Konvertierungsoperatoren werden auch in einem getrennten Thema behandelt; Informationen finden Sie unter [Konvertierungen](../cpp/user-defined-type-conversions-cpp.md).  
  
 Die folgenden Regeln sind für alle anderen unären Operatoren erfüllt.  Um eine Funktion für einen unären Operator als nicht statischen Member zu deklarieren, müssen Sie sie im folgenden Format deklarieren:  
  
 `ret-type operator` `op` `()`  
  
 dabei ist `ret-type` der Rückgabetyp und `op` ist einer der in der vorhergehenden Tabelle aufgelisteten Operatoren.  
  
 Um eine Funktion für einen unären Operator als globale Funktion zu deklarieren, müssen Sie sie im folgenden Format deklarieren:  
  
 `ret-type operator` `op` \(`arg` \)  
  
 wo `ret-type` und `op`, wie beschrieben, für Memberoperatorfunktionen sind und das `arg` ein Argument des Klassentyps ist, mit dem Vorgänge ausgeführt werden sollen.  
  
> [!NOTE]
>  Es gibt keine Einschränkung für die Rückgabetypen der unären Operatoren.  Beispielsweise macht es Sinn für ein logisches NOT \(`!`\), einen Ganzzahlwert zurückzugeben. Das wird aber nicht erzwungen.  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)