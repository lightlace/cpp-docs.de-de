---
title: Compilerwarnung (Stufe 1) C4489 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4489
dev_langs:
- C++
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1c6cff47d8788edd7fdba6844e07d59654456a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278417"
---
# <a name="compiler-warning-level-1-c4489"></a>Compilerwarnung (Stufe 1) C4489
"Spezifizierer": nicht zulässig auf Schnittstellenmethode 'Methode'; Überschreiben Sie Bezeichner dürfen nur auf Ref hardwareinventurklassen- und Klassenmethoden  
  
 Ein Bezeichner-Schlüsselwort wurde falsch in eine Schnittstellenmethode verwendet.  
  
 Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4489 generiert.  
  
```  
// C4489.cpp  
// compile with: /clr /c /W1  
public interface class I {   
   void f() new;   // C4489  
   virtual void b() override;   // C4489  
  
   void g();   // OK  
};  
```