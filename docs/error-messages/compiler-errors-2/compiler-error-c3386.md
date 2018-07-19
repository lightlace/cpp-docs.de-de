---
title: Compilerfehler C3386 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d378c92fbeff4e8738450e2e49c42c00bd46a6c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258074"
---
# <a name="compiler-error-c3386"></a>Compilerfehler C3386
'Typ': __declspec(dllexport) /\__declspec(dllimport) kann nicht auf einen verwalteten oder WinRTtype angewendet werden  
  
 Die `dllimport` und [Dllexport](../../cpp/dllexport-dllimport.md) `__declspec` Modifizierer sind nicht gültig für einen verwalteten oder Windows-Runtime Typ.  
  
 Im folgenden Beispiel wird C3386 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```