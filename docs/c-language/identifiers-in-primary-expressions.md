---
title: "Bezeichner in prim&#228;ren Ausdr&#252;cken | Microsoft Docs"
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
  - "Bezeichner, Festlegen von Objekten"
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Bezeichner in prim&#228;ren Ausdr&#252;cken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bezeichner können folgende Typen haben: ganzzahlig, **Float**, `enum`, `struct`, **Union**, Array, Zeiger oder Funktionstyp.  Ein Bezeichner ist ein primärer Ausdruck, vorausgesetzt, er wurde als Festlegen eines Objekts deklariert \(in diesem Fall ein l\-Wert\) oder als Funktion \(in diesem Fall ist es ein Funktionsbezeichner\).  Eine Definition des l\-Werts erhalten Sie im Artikel über [L\-Wert\- und R\-Wert\-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
 Der Zeigerwert, der durch einen Arraybezeichner dargestellt wird, ist keine Variable. Daher kann der Arraybezeichner nicht den linken Operanden eines Zuweisungsvorgangs bilden und ist kein änderbarer l\-Wert.  
  
 Ein Bezeichner, der als Funktion deklariert wurde, stellt einen Zeiger dar, dessen Wert die Adresse der Funktion darstellt.  Der Zeiger adressiert eine Funktion, die einen Wert eines bestimmten Typs zurückgibt.  Daher dürfen Funktionsbezeichner auch keine L\-Werte in Zuweisungsvorgängen sein.  Weitere Informationen finden Sie im Artikel zu [Bezeichnern](../c-language/c-identifiers.md).  
  
## Siehe auch  
 [C\-Ausdrücke \(primär\)](../c-language/c-primary-expressions.md)