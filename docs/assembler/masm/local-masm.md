---
title: LOKALE (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed9926d23f2e1e8636f31a6f586609ae22d38acd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="local-masm"></a>LOCAL (MASM)
In der ersten Anweisung, in einem Makro **lokale** definiert Bezeichnungen, die für jede Instanz des Makros eindeutig sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>Hinweise  
 In der zweiten-Direktive in einer Prozedurdefinition (**PROC**), **lokale** erstellt stapelbasierte Variablen, die für die Dauer der Prozedur vorhanden sind. Die *Bezeichnung* möglicherweise als einfache Variable oder ein Array mit *Anzahl* Elemente.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)