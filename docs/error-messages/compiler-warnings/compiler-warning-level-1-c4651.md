---
title: Compilerwarnung (Stufe 1) C4651 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0015102a44b71f342b125532d20849590157ee0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283366"
---
# <a name="compiler-warning-level-1-c4651"></a>Compilerwarnung (Stufe 1) C4651
"Definition" nach dem vorkompilierten Header, aber nicht für die aktuelle Kompilierung angegeben  
  
 Die Definition wurde angegeben, wenn der vorkompilierte Header generiert wurde, aber nicht in dieser Kompilierung.  
  
 Die Definition werden innerhalb des vorkompilierten Headers, jedoch nicht in den Rest des Codes wirksam.  
  
 Wenn ein vorkompilierter Header mit DSYMBOL erstellt wurde, generiert der Compiler diese Warnung, wenn die Kompilierung "/ Yu" DSYMBOL besitzt.  DSYMBOL an die Befehlszeile "/ Yu" hinzufügen, wird diese Warnung aufgelöst.