---
title: Compilerfehler C2142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2142
dev_langs:
- C++
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11fd3cd62b236daa93424f53a0896888a89fe33d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170397"
---
# <a name="compiler-error-c2142"></a>Compilerfehler C2142
unterschiedliche Funktionsdeklarationen, die Variable nur in einem von ihnen angegebenen Parameter  
  
 Eine Deklaration der Funktion enthält keine Variablenparameterliste. Eine andere Deklaration nicht. ANSI C (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)) nur.  
  
 Im folgende Beispiel wird C2142 generiert:  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```