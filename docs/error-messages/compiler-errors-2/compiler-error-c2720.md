---
title: Compilerfehler Fehler C2720 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2720
dev_langs:
- C++
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6215cd2e83f1fa3a48c3cbd4970cd2d3466fc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233529"
---
# <a name="compiler-error-c2720"></a>Compiler-Fehler C2720 generiert  
  
> "*Bezeichner*": "*Spezifizierer*" Speicherklassenspezifizierer für Member unzulässig  
  
Die Speicherklasse kann für Klassenmember außerhalb der Variablendeklaration verwendet werden. Um diesen Fehler zu beheben, entfernen Sie den nicht benötigten [Speicherklasse](../../cpp/storage-classes-cpp.md) Spezifizierer aus der Definition des Members außerhalb der Klassendeklaration.  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Beispiel wird C2720 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```cpp  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
```