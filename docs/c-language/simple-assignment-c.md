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
ms.workload: cplusplus
ms.openlocfilehash: 1cf9c5675affb6dcaea78e0cabf2a4427ad03938
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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