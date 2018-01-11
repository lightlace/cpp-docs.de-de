---
title: Compilerwarnung (Stufe 1) C4042 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4042
dev_langs: C++
helpviewer_keywords: C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0801b3fb34b85a6b07127111b38a35ee826028c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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