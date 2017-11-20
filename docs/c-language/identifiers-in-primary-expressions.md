---
title: "Bezeichner in primären Ausdrücken | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce62a6ad0f0cb36678de0756d77155769393f760
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="identifiers-in-primary-expressions"></a>Bezeichner in primären Ausdrücken
Bezeichner können folgende Typen haben: ganzzahlig, **Float**, `enum`, `struct`, **Union**, Array, Zeiger oder Funktionstyp. Ein Bezeichner ist ein primärer Ausdruck, vorausgesetzt, er wurde als Festlegen eines Objekts deklariert (in diesem Fall ein l-Wert) oder als Funktion (in diesem Fall ist es ein Funktionsbezeichner). Eine Definition des l-Werts finden Sie unter [L-Wert- und R-Wert-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
 Der Zeigerwert, der durch einen Arraybezeichner dargestellt wird, ist keine Variable. Daher kann der Arraybezeichner nicht den linken Operanden eines Zuweisungsvorgangs bilden und ist kein änderbarer L-Wert.  
  
 Ein Bezeichner, der als Funktion deklariert wurde, stellt einen Zeiger dar, dessen Wert die Adresse der Funktion darstellt. Der Zeiger adressiert eine Funktion, die einen Wert eines bestimmten Typs zurückgibt. Daher dürfen Funktionsbezeichner auch keine L-Werte in Zuweisungsvorgängen sein. Weitere Informationen finden Sie unter [Identifiers](../c-language/c-identifiers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)