---
title: Compilerwarnung (Stufe 1) C4788 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a43fb9d79c63637b2bff9a27661a9f848ef6dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284198"
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