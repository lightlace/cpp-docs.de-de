---
title: Compilerwarnung (Stufe 4) C4820 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4820
dev_langs:
- C++
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea99ca177a90281ca02e44265f603045b72845f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4820"></a>Compilerwarnung (Stufe 4) C4820
'Bytes' Bytes Abstand nach dem Konstrukt 'member_name'  
  
 Der Typ und die Reihenfolge der Elemente verursacht den Compilerfehler Füllzeichen am Ende einer Struktur hinzufügen. Finden Sie unter [ausrichten](../../cpp/align-cpp.md) für Weitere Informationen zu Auffüllung in einer Struktur.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Im folgenden Beispiel wird C4820 generiert:  
  
```  
// C4820.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4820)   
  
// Delete the following 4 lines to resolve.  
__declspec(align(2)) struct MyStruct {  
   char a;  
   int i;   // C4820  
};  
  
// OK  
#pragma pack(1)  
__declspec(align(1)) struct MyStruct2 {  
   char a;  
   int i;  
};  
```