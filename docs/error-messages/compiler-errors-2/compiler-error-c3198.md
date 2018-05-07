---
title: Compiler-Fehler C3198 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3198
dev_langs:
- C++
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0516e7cae12e544195d157781e6ed86923470420
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3198"></a>Compiler-Fehler C3198 generiert
Ungültige Verwendung eines Gleitkommapragmas: Fenv_access-Pragma unterstützt nur im präzise-Modus  
  
 [Fenv_access](../../preprocessor/fenv-access.md) Pragma wurde verwendet, unter einer [/fp](../../build/reference/fp-specify-floating-point-behavior.md) andere Einstellung als **/fp: präzise**.  
  
 Im folgende Beispiel wird C3198 generiert:  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```