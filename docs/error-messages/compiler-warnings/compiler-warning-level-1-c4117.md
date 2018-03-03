---
title: Compilerwarnung (Stufe 1) C4117 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4117
dev_langs:
- C++
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dfa9fbe5295db86e4ea4c70bda6d93679393a1b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4117"></a>Compilerwarnung (Stufe 1) C4117
Makroname 'Name' ist reserviert. 'Befehl' wird ignoriert.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Versuchen Sie, ein vordefiniertes Makro zu definieren bzw. dessen Definition aufzuheben.  
  
2.  Versuchen Sie, den **defined**-Präprozessoroperator zu definieren bzw. dessen Definition aufzuheben.  
  
 Im folgenden Beispiel wird C4117 generiert:  
  
```  
// C4117.cpp  
// compile with: /W1  
#define __FILE__ test         // C4117. __FILE__ is a predefined macro  
#define ValidMacroName test   // ok  
  
int main() {  
}  
```