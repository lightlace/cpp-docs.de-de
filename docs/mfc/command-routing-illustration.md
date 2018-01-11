---
title: Befehl Routing Abbildung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24ac591005d5df6b18102d296352b8b2528ba839
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-routing-illustration"></a>Befehlsroutingerläuterung
Um zu veranschaulichen, betrachten Sie eine Befehlsnachricht alle löschen Menüelements in einem MDI-Anwendung bearbeiten im Menü aus. Nehmen Sie an, dass die Handlerfunktion für diesen Befehl erfolgt auf eine Memberfunktion, die von der Anwendung Dokumentklasse sein. So sieht wie dieses Befehls den Handler erreicht, nachdem der Benutzer das Menüelement auswählt:  
  
1.  Das Hauptrahmenfenster erhält die Befehlsnachricht zuerst.  
  
2.  MDI-Hauptrahmenfenster kann der derzeit aktiven untergeordneten MDI-Fensters Dank der Befehl behandeln.  
  
3.  Das standardmäßige routing von einem untergeordneten MDI-Rahmenfenster kann seinen Ansichtszustand Dank mit dem Befehl vor dem Überprüfen ihre eigene meldungszuordnung.  
  
4.  Die Sicht überprüft zuerst, ihre eigene meldungszuordnung und leitet suchen kein Handler neben den Befehl an die zugeordnete Dokument.  
  
5.  Das Dokument überprüft seine meldungszuordnung und sucht nach einem Handler. Dieses Dokument-Memberfunktion aufgerufen und das routing wird beendet.  
  
 Wenn das Dokument einen Handler nicht vorhanden wäre, würde es neben den Befehl an seine Dokumentvorlage weiterleiten. Anschließend würde der Befehl auf die Ansicht, und klicken Sie dann das Rahmenfenster zurückgeben. Abschließend würden das Rahmenfenster seine meldungszuordnung überprüfen. Wenn auch dieser Überprüfung fehlgeschlagen ist, würde der Befehl an das Hauptrahmenfenster für MDI- und dann auf das Anwendungsobjekt weitergeleitet werden – das endgültige Ziel nicht behandelten Befehle.  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

