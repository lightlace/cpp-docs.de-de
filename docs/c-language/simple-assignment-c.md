---
title: Einfache Zuweisung (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31914118283c9d0c5c502e3426ba12e86d7c7680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32385168"
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