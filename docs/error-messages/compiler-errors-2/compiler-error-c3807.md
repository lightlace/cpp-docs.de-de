---
title: Compilerfehler C3807 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc8e760d295cc0a4c2482449038ea09e89547425
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3807"></a>Compilerfehler C3807
'Typ': eine Klasse mit dem ComImport-Attribut kann nicht von "Typ2" abgeleitet werden, nur für die schnittstellenimplementierung ist zulässig.  
  
 Ein Typ, der von abgeleitet <xref:System.Runtime.InteropServices.ComImportAttribute> können nur eine Schnittstelle implementieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3807 generiert.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```
