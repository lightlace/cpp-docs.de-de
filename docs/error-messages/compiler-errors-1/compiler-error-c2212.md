---
title: Compilerfehler C2212 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2212
dev_langs:
- C++
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8515302c7b794a92fe16f3c0baf9c82665aa4d3
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2212"></a>Compilerfehler C2212
'Bezeichner': __based ist nicht verfügbar für Zeiger auf Funktionen  
  
 Zeiger auf Funktionen können nicht deklariert werden `__based`. Wenn Sie Code basierende Daten benötigen, verwenden Sie die `__declspec` Schlüsselwort oder der `data_seg` Pragma.