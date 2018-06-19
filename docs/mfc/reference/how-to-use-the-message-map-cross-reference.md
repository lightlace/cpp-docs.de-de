---
title: 'Vorgehensweise: Verwenden des Meldungszuordnungs-Querverweises | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d59d0bfc75f654cd9f8f15ff851ad42a619e271f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370095"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises
In Einträge, die mit der Bezeichnung \<MemberFxn >, Schreiben Sie eine eigene Memberfunktion für eine abgeleitete [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Geben Sie der Funktion einen beliebigen Namen, den Ihnen gefallen. Andere Funktionen wie `OnActivate`, werden die Memberfunktionen der Klasse `CWnd`. Wenn Sie aufgerufen wird, übergeben sie die Nachricht an die `DefWindowProc` Windows-Funktion. Um die Windows-benachrichtigungsmeldungen zu verarbeiten, überschreiben Sie die entsprechende `CWnd` Funktion in der abgeleiteten Klasse. Ihre Funktion sollte außer Kraft gesetzte-Funktion in Ihrer Basisklasse, mit der Basisklasse aufrufen, und Windows auf die Meldung reagieren.  
  
 Fügen Sie den Funktionsprototyp in allen Fällen, in der `CWnd`-Header der abgeleiteten Klasse, und Code Zuordnungseintrags Nachricht wie dargestellt.  
  
 Die folgenden Begriffe werden verwendet:  
  
|Begriff|Definition|  
|----------|----------------|  
|ID|Alle benutzerdefinierten Menü-Element-ID (**WM_COMMAND** Nachrichten) oder die control-ID (untergeordnete fenstermeldungen Benachrichtigung).|  
|"Nachricht" und "wNotifyCode schalten"|Der Windows-Meldung IDs gemäß Definition in WINDOWS. H.|  
|nMessageVariable|Name einer Variablen, die den Rückgabewert enthält die **RegisterWindowMessage registriert** Windows-Funktion.|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)

