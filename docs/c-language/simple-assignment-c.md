---
title: Einfache Zuweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a60ec2f6f6466b579f917d02dabc24736c5a2e92
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="simple-assignment-c"></a>Einfache Zuweisung (C)
Der einfache Zuweisungsoperator weist seinen rechten Operanden dem linken Operanden zu. Der Wert des rechten Operanden wird in den Typ des Zuweisungsausdrucks konvertiert und ersetzt den Wert, der im Objekt gespeichert wird, das durch den linken Operanden festgelegt ist. Es gelten die Konvertierungsregeln für die Zuweisung (siehe [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 In diesem Beispiel wird der Wert von `y` in den Typ **double** konvertiert und `x` zugewiesen.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zuweisungsoperatoren](../c-language/c-assignment-operators.md)
