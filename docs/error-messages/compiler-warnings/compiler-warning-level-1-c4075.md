---
title: Compilerwarnung (Stufe 1) C4075 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4075
dev_langs: C++
helpviewer_keywords: C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba20ea087de69afa5c73ff32d6b74dd6a27652ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4075"></a>Compilerwarnung (Stufe 1) C4075
Initialisierungen stehen in nicht erkanntem Initialisierungsbereich  
  
 In einem [#pragma init_seg](../../preprocessor/init-seg.md) wird ein unbekannter Abschnittsname verwendet. Der Compiler ignoriert den **pragma** -Befehl.  
  
 Im folgenden Beispiel wird C4075 generiert:  
  
```  
// C4075.cpp  
// compile with: /W1  
#pragma init_seg("mysegg")   // C4075  
  
// try..  
// #pragma init_seg(user)  
  
int main() {  
}  
```