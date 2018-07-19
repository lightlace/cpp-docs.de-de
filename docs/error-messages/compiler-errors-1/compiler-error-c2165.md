---
title: Compilerfehler C2165 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2165
dev_langs:
- C++
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8d434993ad913efca3fdff58fb7ed9cc0715e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170478"
---
# <a name="compiler-error-c2165"></a>Compilerfehler C2165
'Schlüsselwort': Zeiger auf Daten können nicht geändert werden.  
  
 Das `__stdcall`-, `__cdecl`- oder `__fastcall` -Schlüsselwort versucht, einen Zeiger auf Daten zu ändern.  
  
 Im folgenden Beispiel wird C2165 generiert:  
  
```  
// C2165.cpp  
// compile with: /c  
char __cdecl *p;   // C2165  
char *p;   // OK  
```