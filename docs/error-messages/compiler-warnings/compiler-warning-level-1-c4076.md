---
title: Compilerwarnung (Stufe 1) C4076 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7918ae093210c38bacfe89f0d4770eda2dee2e35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4076"></a>Compilerwarnung (Stufe 1) C4076
"Typmodifizierer": Kann nicht mit Typ "Typname" verwendet werden  
  
 Ein Typmodifizierer kann unabhängig davon, ob er **signed** oder `unsigned`ist, nicht mit einem Typ verwendet werden, der nicht ganzzahlig ist. ***Typmodifizierer*** wird ignoriert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4076 generiert:  
  
```  
// C4076.cpp  
// compile with: /W1 /LD  
unsigned double x;   // C4076  
```