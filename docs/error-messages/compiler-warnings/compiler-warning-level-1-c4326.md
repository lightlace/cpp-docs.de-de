---
title: Compilerwarnung (Stufe 1) C4326 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faf38d27c0a8d38e008cb94d65fc8745995dd947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4326"></a>Compilerwarnung (Stufe 1) C4326
Rückgabetyp "Funktion" sollte "Typ1" anstelle von "Typ2" sein.  
  
 Eine Funktion hat einen Typ zurückgegeben, außer ***Typ1***. Beispiel für die Verwendung ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md), Main hat keine zurückgegeben. ein `int`.  
  
 Im folgenden Beispiel wird C4326 generiert:  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```