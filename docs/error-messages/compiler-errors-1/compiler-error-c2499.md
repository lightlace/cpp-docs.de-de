---
title: Compilerfehler C2499 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2499
dev_langs: C++
helpviewer_keywords: C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9727fc22e9b6f41c0b4b574e7c9c21ce9c28c093
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2499"></a>Compilerfehler C2499
'Klasse': eine Klasse kann nicht ihre eigene Basisklasse  
  
 Sie haben versucht, die Klasse anzugeben, die Sie als Basisklasse definieren.  
  
 Im folgenden Beispiel wird C2499 generiert:  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```