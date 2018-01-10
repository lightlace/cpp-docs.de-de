---
title: Compilerfehler C2462 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2462
dev_langs: C++
helpviewer_keywords: C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af4b7e303a67ed1eae3d217964818d1b4cd05b96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2462"></a>Compilerfehler C2462
'Bezeichner': Definieren Sie einen Typ kann nicht in 'new-Ausdruck'  
  
 Im Operandenfeld, der keinen Typ definieren die `new` Operator. Fügen Sie die Typdefinition in eine separate Anweisung.  
  
 Im folgende Beispiel wird C2462 generiert:  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```