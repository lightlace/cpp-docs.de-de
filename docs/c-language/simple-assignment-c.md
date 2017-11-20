---
title: Einfache Zuweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6f81732b4fccdac6ae0912b7617c28318da3e55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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