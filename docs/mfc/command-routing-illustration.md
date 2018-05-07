---
title: Befehl Routing Abbildung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a12a5cd19177761dfbf484c64f528d8def194ca5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

