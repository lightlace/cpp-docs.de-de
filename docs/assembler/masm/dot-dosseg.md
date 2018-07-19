---
title: . DOSSEG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3817cfe98758faf86ea87d74e02657598c3e806b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054884"
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