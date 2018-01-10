---
title: LOKALE (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Local
dev_langs: C++
helpviewer_keywords: LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45ee0a98d614ee10cb7393c0e616459526b37531
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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