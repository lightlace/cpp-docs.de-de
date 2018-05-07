---
title: Compiler-Fehler C2745 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2745
dev_langs:
- C++
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f371629c3811821d9c7dce56cc44137534058c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2745"></a>Compiler-Fehler C2745 generiert
"token": dieses Token kann nicht in einen Bezeichner konvertiert werden  
  
 Bezeichner müssen zulässiger Zeichen bestehen.  
  
 Im folgende Beispiel wird C2745 generiert:  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```