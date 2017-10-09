---
title: Speicherung von Unions | Microsoft-Dokumentation
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
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: cb349b2c1649b6e4e46fcc92829de87043d0c50a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="storage-of-unions"></a>Speicherung von Unions
Der Speicher, der einer Union-Variable zugeordnet wird, ist der Speicher, der für den größten Member der Union erforderlich ist. Wenn ein kleinerer Member gespeichert wird, kann die Union-Variable nicht verwendeten Speicherbereich enthalten. Alle Member werden im gleichen Speicherbereich gespeichert und beginnen an derselben Adresse. Der gespeicherte Wert wird jedes Mal überschrieben, wenn einem anderen Member ein Wert zugewiesen wird. Zum Beispiel:  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 Die Elemente der `x`-Union fungieren in der Reihenfolge ihrer Deklaration als Zeiger auf einen `char`-Wert, einen `char`-Wert und ein Array von **float**-Werten. Der `x` zugeordnete Speicher ist der Speicher, der für das `f`-Array mit 20 Elementen erforderlich ist, da `f` der längste Union-Member ist. Da kein Tag der Union zugeordnet ist, ist ihr Typ unbenannt oder „anonym“.  
  
## <a name="see-also"></a>Siehe auch  
 [Union-Deklarationen](../c-language/union-declarations.md)
