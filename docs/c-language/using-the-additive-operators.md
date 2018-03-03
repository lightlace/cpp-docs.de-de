---
title: Verwenden von additiven Operatoren | Microsoft-Dokumentation
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
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94e2a63412e4fecd5f358659cc4bf02f90df57ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-additive-operators"></a>Verwenden von additiven Operatoren
Die folgenden Beispiele, welche die Additions- und Subtraktionsoperatoren veranschaulichen, verwenden diese Deklarationen:  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Diese Anweisungen sind gleichwertig:  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 Der Wert von `i` wird mit der Länge eines **float** multipliziert und zu `&x[4]` hinzugefügt. Das Zeigerwertergebnis ist die Adresse von `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 In diesem Beispiel wird die Adresse des dritten Elements von `x` (angegeben durch `x[i-2]`) von der Adresse des fünften Elements von `x` (angegeben durch `x[i]`) subtrahiert. Die Differenz wird durch die Länge eines **float** geteilt. Das Ergebnis ist der Ganzzahlwert 2.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Operatoren (additiv)](../c-language/c-additive-operators.md)