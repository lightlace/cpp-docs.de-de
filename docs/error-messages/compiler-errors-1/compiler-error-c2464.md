---
title: Compilerfehler C2464 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98949ba463f432666753cb39de37bb4bf8f7276f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226025"
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