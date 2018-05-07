---
title: Compilerfehler C2466 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e55e5c130b0a0454577a7155b704a18933b86198
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2466"></a>Compilerfehler C2466
ein Array von Konstanten Größe 0 kann nicht zugeordnet werden.  
  
 Ein Array ist reserviert oder mit der Größe 0 (null) deklariert. Der Konstante Ausdruck für die Arraygröße muss eine ganze Zahl größer als 0 (null) sein. Eine Arraydeklaration eine Nullindex ist zulässig, nur für eine Klasse, Struktur oder union-Member und nur mit Microsoft-Erweiterungen (["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Im folgende Beispiel wird C2466 generiert:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```