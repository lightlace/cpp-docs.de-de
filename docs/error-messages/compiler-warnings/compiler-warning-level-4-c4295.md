---
title: Compilerwarnung (Stufe 4) C4295 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1424302c5c109ff79f35c922d1e5051b15655554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4295"></a>Compilerwarnung (Stufe 4) C4295
  
> "*Array*': Array ist zu klein, um ein abschließendes Nullzeichen enthalten.  
  
 Ein Array wurde initialisiert, aber das letzte Zeichen im Array ist nicht Null; Zugreifen auf das Array kann zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
 Im folgenden Beispiel wird C4295 generiert. Um dieses Problem zu beheben, konnten Sie deklarieren die Arraygröße größer, um eine terminierende aufzunehmen null aus dem Initialisierer.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```