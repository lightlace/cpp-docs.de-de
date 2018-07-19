---
title: Compilerwarnung (Stufe 1) C4124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: accd58c123bcd74e54176eed5eb974c3df33dbab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279317"
---
# <a name="compiler-warning-level-1-c4124"></a>Compilerwarnung (Stufe 1) C4124
__fastcall mit stapelüberprüfung ist ineffizient  
  
 Die `__fastcall` Schlüsselwort mit stapelüberprüfung aktiviert verwendet wurde.  
  
 Die `__fastcall` Konvention generiert einen schnelleren Code, aber die stapelüberprüfung verursacht langsamere Code. Bei Verwendung `__fastcall`, deaktivieren Sie die stapelüberprüfung mit der **Check_stack** Pragma oder/GS.  
  
 Diese Warnung wird nur für die erste Funktion deklariert, die unter diesen Bedingungen ausgegeben.