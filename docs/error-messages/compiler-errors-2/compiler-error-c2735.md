---
title: Compiler-Fehler C2735 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2735
dev_langs: C++
helpviewer_keywords: C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1008ef6178a4220bac718e08ba31a36d5db3242f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2735"></a>Compiler-Fehler C2735 generiert
' Schlüsselwort ' ist in der formalen Parameter Typspezifizierer nicht zulässig.  
  
 Das Schlüsselwort ist in diesem Kontext ungültig.  
  
 Im folgende Beispiel wird C2735 generiert:  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```