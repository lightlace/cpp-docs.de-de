---
title: Wann benötige ich AtlAxWinTerm aufrufen? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinTerm
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61830023d3fb67d331784769f32cda4eee8355b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360161"
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>Wann benötige ich AtlAxWinTerm aufrufen?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) hebt die Registrierung der **"AtlAxWin80"** Fensterklasse. Sie sollten diese Funktion aufrufen, (falls Sie sich nicht mehr benötigen, die zum Erstellen von Host-Windows), nachdem alle vorhandenen Hostfenster zerstört wurden. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch beim Beenden des Prozesses.  
  
## <a name="see-also"></a>Siehe auch  
 Wann benötige ich AtlAxWinInit aufrufen  
[Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

