---
title: Compilerwarnung (Stufe 1) C4788 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4788
dev_langs: C++
helpviewer_keywords: C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>Compilerwarnung (Stufe 1) C4788
'Bezeichner': Der Bezeichner wurde auf 'Anzahl' Zeichen gekürzt.  
  
 Durch den Compiler wird die für einen Funktionsnamen zugelassene maximale Länge eingeschränkt. Wenn der Compiler Funclets für EH/SEH-Code generiert wird, bildet Sie der Funclet-Name vorangestellt den Funktionsnamen mit Text, z. B. "__catch," "\__unwind", oder eine andere Zeichenfolge.  
  
 Wenn der erstellte funclet-Name zu lang ist, wird dieser vom Compiler gekürzt, und es wird C4788 ausgegeben.  
  
 Um diese Warnung zu vermeiden, kürzen Sie den ursprünglichen Funktionsnamen. Wenn es sich bei der Funktion um eine C++-Vorlagenfunktion oder -Methode handelt, verwenden Sie für einen Teil des Namens eine Typdefinition. Zum Beispiel:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 Dies kann durch Folgendes ersetzt werden:  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Diese Warnung tritt nur im [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]-Compiler auf.