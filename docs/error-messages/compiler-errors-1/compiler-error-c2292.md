---
title: Compilerfehler C2292 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2292
dev_langs:
- C++
helpviewer_keywords:
- C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a4810da162223b6e9ca33781a608c416a34aa804
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2292"></a>Compilerfehler C2292
'Bezeichner': am besten case-Vererbung: 'Darstellung1' deklariert, aber 'Darstellung2' erforderlich  
  
 Kompilieren des folgenden Codes mit [/vmb](../../build/reference/vmb-vmg-representation-method.md) ("günstigsten immer" Darstellung) bewirkt, dass Fehler C2292 verursacht.  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```
