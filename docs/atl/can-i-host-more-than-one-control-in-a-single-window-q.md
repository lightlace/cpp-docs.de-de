---
title: Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten? | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be87c0bad9ab250593847cc24d16158030040054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten?
Es ist nicht möglich, mehr als ein Steuerelement in einem einzelnen Fenster der ATL-Host zu hosten. Jede Hostfenster soll genau ein Steuerelement zu einem Zeitpunkt aufnehmen (Dies ermöglicht einen einfachen Mechanismus für die Behandlung der Nachricht Reflektion und pro Steuerelement Umgebungseigenschaften). Wenn Sie mehrere Steuerelemente in einem einzelnen Fenster anzeigen möchten, ist es jedoch problemlos auf mehrere Hostfenster als untergeordnete Elemente des diesem Fenster zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

