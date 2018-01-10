---
title: Compilerfehler C2422 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2422
dev_langs: C++
helpviewer_keywords: C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 852a495406a8baf147fc53262f8fe856fce726b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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