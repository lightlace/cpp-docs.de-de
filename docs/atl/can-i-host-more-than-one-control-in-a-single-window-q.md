---
title: Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ceb9444b6371e261115bbf52ef5a249100772d1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356423"
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten?
Es ist nicht möglich, mehr als ein Steuerelement in einem einzelnen Fenster der ATL-Host zu hosten. Jede Hostfenster soll genau ein Steuerelement zu einem Zeitpunkt aufnehmen (Dies ermöglicht einen einfachen Mechanismus für die Behandlung der Nachricht Reflektion und pro Steuerelement Umgebungseigenschaften). Wenn Sie mehrere Steuerelemente in einem einzelnen Fenster anzeigen möchten, ist es jedoch problemlos auf mehrere Hostfenster als untergeordnete Elemente des diesem Fenster zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

