---
title: Compilerwarnung (Stufe 1) C4952 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42696dfae816742c958bca23e25e311e834dd62a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292141"
---
# <a name="compiler-warning-level-1-c4952"></a>Compilerwarnung (Stufe 1) C4952
'function': Es wurden keine Profildaten in der Programmdatenbank 'pgd_file' gefunden.  
  
 Bei der Verwendung von [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` erneut kompiliert wurde und eine neue Funktion (***Funktion***) aufweist.  
  
 Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.  
  
 Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.