---
title: Bezeichner in primären Ausdrücken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9f39f7ce609ea06a2d991ac79c2b1151625bc1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384758"
---
# <a name="identifiers-in-primary-expressions"></a>Bezeichner in primären Ausdrücken
Bezeichner können folgende Typen haben: ganzzahlig, **Float**, `enum`, `struct`, **Union**, Array, Zeiger oder Funktionstyp. Ein Bezeichner ist ein primärer Ausdruck, vorausgesetzt, er wurde als Festlegen eines Objekts deklariert (in diesem Fall ein l-Wert) oder als Funktion (in diesem Fall ist es ein Funktionsbezeichner). Eine Definition des l-Werts finden Sie unter [L-Wert- und R-Wert-Ausdrücke](../c-language/l-value-and-r-value-expressions.md).  
  
 Der Zeigerwert, der durch einen Arraybezeichner dargestellt wird, ist keine Variable. Daher kann der Arraybezeichner nicht den linken Operanden eines Zuweisungsvorgangs bilden und ist kein änderbarer L-Wert.  
  
 Ein Bezeichner, der als Funktion deklariert wurde, stellt einen Zeiger dar, dessen Wert die Adresse der Funktion darstellt. Der Zeiger adressiert eine Funktion, die einen Wert eines bestimmten Typs zurückgibt. Daher dürfen Funktionsbezeichner auch keine L-Werte in Zuweisungsvorgängen sein. Weitere Informationen finden Sie unter [Identifiers](../c-language/c-identifiers.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)