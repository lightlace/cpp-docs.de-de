---
title: . DOSSEG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .DOSSEG
dev_langs: C++
helpviewer_keywords: .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a53159911c47d1c88df90c53f3302f813e5bd95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dosseg"></a>.DOSSEG
Sortiert die Segmente gemäß der Konvention des MS-DOS-Segment: CODE zuerst, dann nicht im DGROUP Segmente und klicken Sie dann im DGROUP Segmente.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Segmente in DGROUP befolgen Sie diese Reihenfolge: Segmente nicht in BSS oder Stapel, und klicken Sie dann BSS Segmente und schließlich für den Stapel Segmente. In erster Linie verwendet zum Sicherstellen der Codeansichtsinformationen-Unterstützung in MASM eigenständige Programme. Identisch mit [DOSSEG](../../assembler/masm/dosseg.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)