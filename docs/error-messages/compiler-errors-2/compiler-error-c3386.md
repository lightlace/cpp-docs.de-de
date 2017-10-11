---
title: Compilerfehler C3386 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8b912d1d75ae120f993c3641ff2e2b561910b4aa
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
