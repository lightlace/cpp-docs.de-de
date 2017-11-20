---
title: Compilerwarnung (Stufe 1) C4052 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4052
dev_langs:
- C++
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 41d12dc64884d81f205c775c426d1fa5e1c589aa
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4052"></a>Compilerwarnung (Stufe 1) C4052
Unterschiedliche Funktionsdeklarationen; eine enthält variable Argumente  
  
 Eine Deklaration der Funktion enthält keine variablen Argumente. Wird ignoriert.  
  
 Im folgenden Beispiel wird C4052 generiert:  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```