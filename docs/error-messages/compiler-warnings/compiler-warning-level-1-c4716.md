---
title: Compilerwarnung (Stufe 1) C4716 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be620264c315fc9c2ff3cd4cb91bd9d77c8a4d07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4716"></a>Compilerwarnung (Stufe 1) C4716
"Funktion" muss einen Wert zurückgeben  
  
 Die angegebene Funktion keinen Wert zurück.  
  
 Nur Funktionen mit dem Rückgabetyp "void" kann mithilfe den return-Befehl ohne eine begleitende Rückgabewert.  
  
 Wenn diese Funktion aufgerufen wird, wird ein nicht definierter Wert zurückgegeben.  
  
 Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md).  
  
 Im folgenden Beispiel wird C4716 generiert:  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```