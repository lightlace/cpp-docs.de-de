---
title: Compilerfehler C2537 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6100f77d3a1487bfa1eb12a78ac8187cec43fe64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199956"
---
# <a name="compiler-error-c2537"></a>Compilerfehler C2537
"Spezifizierer": Ungültige Verknüpfungsspezifikation  
  
 Mögliche Ursachen:  
  
1.  Der Bindungsspezifizierer wird nicht unterstützt. Der Bindungsspezifizierer "C" wird unterstützt.  
  
2.  Verknüpfung mit "C" wird für mehr als eine Funktion in einem Satz von überladenen Funktionen angegeben. Dies ist nicht zulässig.  
  
 Im folgende Beispiel wird C2537 generiert:  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```