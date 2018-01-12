---
title: "Wann benötige ich AtlAxWinTerm aufrufen? | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinTerm
dev_langs: C++
helpviewer_keywords: AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c52c5295108ef01dc23ea9f945850e91a9806d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>Wann benötige ich AtlAxWinTerm aufrufen?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) hebt die Registrierung der **"AtlAxWin80"** Fensterklasse. Sie sollten diese Funktion aufrufen, (falls Sie sich nicht mehr benötigen, die zum Erstellen von Host-Windows), nachdem alle vorhandenen Hostfenster zerstört wurden. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch beim Beenden des Prozesses.  
  
## <a name="see-also"></a>Siehe auch  
 Wann benötige ich AtlAxWinInit aufrufen  
[Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

