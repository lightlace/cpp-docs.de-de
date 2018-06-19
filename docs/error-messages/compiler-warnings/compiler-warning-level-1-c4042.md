---
title: Compilerwarnung (Stufe 1) C4042 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4123c18eb9765841a5f6b54446cd064407700
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278384"
---
# <a name="compiler-warning-level-1-c4042"></a>Compilerwarnung (Stufe 1) C4042
'Bezeichner': Ungültige Speicherklasse hat  
  
 Die angegebene Speicherklasse kann nicht mit der folgenden ID in diesem Kontext nicht verwendet werden. Der Compiler verwendet stattdessen die Standardspeicherklasse:  
  
-   `extern`, wenn *Bezeichner* ist eine Funktion.  
  
-   **automatische**, wenn *Bezeichner* ist eine formale Parameter oder eine lokale Variable.  
  
-   Keine Speicherklasse, wenn *Bezeichner* ist eine globale Variable.  
  
 Diese Warnung kann verursacht werden, durch Angeben von anders als eine Speicherklasse **registrieren** in einer Parameterdeklaration.  
  
 Im folgende Beispiel wird C4042 generiert:  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```