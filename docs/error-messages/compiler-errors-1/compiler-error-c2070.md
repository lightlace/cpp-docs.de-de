---
title: Compilerfehler Fehler C2070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2070
dev_langs:
- C++
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8eaf9ee345543fe838358c345e68874eecadd72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165177"
---
# <a name="compiler-error-c2070"></a>Compilerfehler Fehler C2070
'Typ': Unzulässiger "sizeof" Operand  
  
 Die ["sizeof"](../../cpp/sizeof-operator.md) Operator erfordert einen Ausdruck oder einen Typnamen.  
  
 Im folgende Beispiel wird C2070 generiert:  
  
```  
// C2070.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(func);   // C2070  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2070b.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(a);  
}  
```