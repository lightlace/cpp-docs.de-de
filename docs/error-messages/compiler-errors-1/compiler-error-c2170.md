---
title: Compilerfehler C2170 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2170
dev_langs: C++
helpviewer_keywords: C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 118caa1ce0d5b1b2472153bf6fed58844901e9fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2170"></a>Compilerfehler C2170
'Bezeichner': nicht als Funktion deklariert, kann nicht systemintern sein  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Pragma `intrinsic` für ein anderes Element als eine Funktion verwendet wird.  
  
2.  Pragma `intrinsic` wird für eine Funktion ohne systeminterne Form verwendet.