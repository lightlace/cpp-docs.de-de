---
title: Compilerwarnung (Stufe 1) C4651 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dce099d657341ebc957c95ab0cd14f508f9e36ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4651"></a>Compilerwarnung (Stufe 1) C4651
"Definition" nach dem vorkompilierten Header, aber nicht für die aktuelle Kompilierung angegeben  
  
 Die Definition wurde angegeben, wenn der vorkompilierte Header generiert wurde, aber nicht in dieser Kompilierung.  
  
 Die Definition werden innerhalb des vorkompilierten Headers, jedoch nicht in den Rest des Codes wirksam.  
  
 Wenn ein vorkompilierter Header mit DSYMBOL erstellt wurde, generiert der Compiler diese Warnung, wenn die Kompilierung "/ Yu" DSYMBOL besitzt.  DSYMBOL an die Befehlszeile "/ Yu" hinzufügen, wird diese Warnung aufgelöst.