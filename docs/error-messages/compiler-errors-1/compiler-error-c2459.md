---
title: Compilerfehler C2459 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2459
dev_langs:
- C++
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 78d92952b53c15d6170b32a711848111a4b6fd28
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2459"></a>Compilerfehler C2459
'Bezeichner': definiert wird; als anonyme Mitglied kann nicht hinzugefügt werden.  
  
 Eine Klasse, Struktur oder Union wird in einen eigenen Bereich von einem Mitglied einer anonymen Union neu definiert.  
  
 Im folgende Beispiel wird C2459 generiert:  
  
```  
// C2459.cpp  
// compile with: /c  
class C {  
   union { int C; };   // C2459  
   union { int D; };  
};  
```