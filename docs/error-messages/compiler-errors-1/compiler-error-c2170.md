---
title: Compilerfehler C2170 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2170
dev_langs:
- C++
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8520e9ea71d90e7f97c6296d4326abb1fd4c7609
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2170"></a>Compilerfehler C2170
'Bezeichner': nicht als Funktion deklariert, kann nicht systemintern sein  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Pragma `intrinsic` für ein anderes Element als eine Funktion verwendet wird.  
  
2.  Pragma `intrinsic` wird für eine Funktion ohne systeminterne Form verwendet.
