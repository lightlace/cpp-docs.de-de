---
title: Schwerwiegender Fehler C1307 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d06ce51ada7cd9159b8e02ff627bf12ebb7293d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227134"
---
# <a name="fatal-error-c1307"></a>Schwerwiegender Fehler C1307
Das Programm wurde seit dem Erfassen der Profildaten bearbeitet.  
  
 Bei Verwendung [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), der Linker ein Eingabemodul, die nach/LTCG: PGINSTRUMENT neu kompiliert wurde erkannt und, dass das Modul bis zu dem Zeitpunkt geändert wurde, in denen nicht mehr vorhandenen Profildaten relevant sind. Beispielsweise, wenn in der neu kompilierten Modul Aufrufdiagramms geändert haben, generiert der Compiler C1307.  
  
 Zum Beheben dieses Fehlers führen Sie/LTCG: PGINSTRUMENT aus, wiederholen Sie alle Testläufe und führen Sie die/LTCG: PGOPTIMIZE. Wenn Sie nicht ausgeführt werden können, und wiederholen alle Testläufe/LTCG: PGINSTRUMENT ausgeführt wird, verwenden Sie/LTCG: PGUPDATE anstelle von/LTCG: PGOPTIMIZE, um das optimierte Image zu erstellen.