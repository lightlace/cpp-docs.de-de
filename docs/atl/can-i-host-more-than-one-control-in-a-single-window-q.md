---
title: Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten? | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5fa1a1b914d7d9725e8f2d9858f0481bb7aa24a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten?
Es ist nicht möglich, mehr als ein Steuerelement in einem einzelnen Fenster der ATL-Host zu hosten. Jede Hostfenster soll genau ein Steuerelement zu einem Zeitpunkt aufnehmen (Dies ermöglicht einen einfachen Mechanismus für die Behandlung der Nachricht Reflektion und pro Steuerelement Umgebungseigenschaften). Wenn Sie mehrere Steuerelemente in einem einzelnen Fenster anzeigen möchten, ist es jedoch problemlos auf mehrere Hostfenster als untergeordnete Elemente des diesem Fenster zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

