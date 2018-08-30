---
title: Compilerwarnung (Stufe 1) C4311 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4311
dev_langs:
- C++
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adfd27a116ae5747a2dd899ce51c38f01055f356
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218539"
---
# <a name="compiler-warning-level-1-c4311"></a>Compilerwarnung (Stufe 1) C4311
'Variable': Zeigerverkürzung von 'Typ' zu 'Typ'  
  
 Diese Warnung erkennt Abschneidefehler bei 64-Bit-Zeigern. Wenn Code beispielsweise für eine 64-Bit-Architektur kompiliert wird, wird der Wert eines Zeigers (64 Bit) abgeschnitten, falls er einem `int` (32 Bit) zugewiesen wurde. Weitere Informationen finden Sie unter [Regeln für die Verwendung von Zeigern](/windows/desktop/WinProg64/rules-for-using-pointers).  
  
 Weitere Informationen zu den häufigsten Gründen von Warnung C4311 finden Sie unter [Häufige Compilerfehler](/windows/desktop/WinProg64/common-compiler-errors).  
  
 Im folgenden Codebeispiel wird C4311 beim Kompilieren für ein 64-Bit-Ziel generiert und dann veranschaulicht, wie Sie dieses Problem beheben können:  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```