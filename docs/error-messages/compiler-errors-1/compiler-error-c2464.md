---
title: Compilerfehler C2464 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3992f1ecc19beb5c4fa1208fe82a93deab546260
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2464"></a>Compilerfehler C2464
'Bezeichner': kann nicht "new" verwenden, um einen Verweis zuweisen  
  
 Der Verweisbezeichner zugeordnet wurde die `new` Operator. Verweise sind also nicht Speicherobjekte, `new` nicht möglich, einen Zeiger auf diese zurück. Verwenden Sie die standardmäßigen Variablendeklaration-Syntax, um einen Verweis zu deklarieren.  
  
 Im folgende Beispiel wird C2464 generiert:  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```