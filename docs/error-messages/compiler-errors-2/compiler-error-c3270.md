---
title: Compilerfehler C3270 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3270
dev_langs:
- C++
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d7630795f179955efea6f97feebbf3c02a6802b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247780"
---
# <a name="compiler-error-c3270"></a>Compilerfehler C3270
"Feld": Das FieldOffset-Attribut ist im Kontext von "StructLayout(Explicit)" erforderlich und kann nur in diesem Kontext verwendet werden  
  
Ein Feld wurde mit markiert **FieldOffset**, das ist nur zulässig, wenn **StructLayout(Explicit)"** ist aktiviert.  
  
Im folgenden Beispiel wird C3270 generiert:  
  
```  
// C3270_2.cpp  
// compile with: /clr /c  
using namespace System::Runtime::InteropServices;  
  
[ StructLayout(LayoutKind::Sequential) ]  
// try the following line instead  
// [ StructLayout(LayoutKind::Explicit) ]  
public value struct MYUNION  
{  
   [FieldOffset(0)] int a;   // C3270  
   // ...  
};  
```  
