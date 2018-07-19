---
title: Compilerfehler C2422 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89a808e4b324b11c88be38ae7d8815bee4e232cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196346"
---
# <a name="compiler-error-c2422"></a>Compilerfehler C2422
Ungültige Segment Außerkraftsetzung in "Operand"  
  
 Inline-Assemblycode verwendet fälschlicherweise Außerkraftsetzung-Segment-Operator (Doppelpunkt) bei einem Operanden.  Mögliche Ursachen sind:  
  
-   Die Registrierung vor der Operator ist kein Segmentregister.  
  
-   Die Registrierung vor der Operator ist nicht das einzige Segmentregister im Operanden.  
  
-   Die Außerkraftsetzung Segment-Operator wird in ein Dereferenzierungsoperator (Klammern) angezeigt.  
  
-   Der Ausdruck nach der Außerkraftsetzung Segment-Operator ist nicht unmittelbarer Operand oder einen arbeitsspeicheroperanden.  
  
 Im folgende Beispiel wird C2422 generiert:  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```