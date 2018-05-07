---
title: 'Profilgesteuerte Optimierung Fehler: PG0165 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acad97411480112d06dadd454d1368dcfdf2c87f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler in profilgesteuerter Optimierung: PG0165
Lesen 'Dateiname.PGD': ' PGD-Version wird nicht unterstützt (Versionskonflikt) ".  
  
 PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als die zum Verwenden *Filename*PGD. Dieser Fehler weist darauf hin, dass diese Compilertoolset nicht verwenden kann, die Daten aus *Filename*PGD zum Optimieren des aktuellen Programms.  
  
 Um dieses Problem zu beheben, Regenerieren *Filename*PGD mithilfe der aktuellen Compilertoolset.