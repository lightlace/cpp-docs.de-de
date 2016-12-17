---
title: "Befehlsroutingerl&#228;uterung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsbehandlung, Routingbefehle"
  - "Befehlsrouting, OnCmdMsg-Handler"
  - "MFC, Befehlsrouting"
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Befehlsroutingerl&#228;uterung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um zu illustrieren, halten Sie eine Befehlsmeldung eines freien Gelegenheiten für alles Menüelement im Menü Bearbeiten einer MDI\-Anwendung.  Angenommen, die Handlerfunktion für dieses Befehls geschieht, um eine Memberfunktion der Dokumentklasse der Anwendung.  Im Folgenden wird gezeigt, wie dieser Befehl den Handler erreicht, nachdem der Benutzer das Menüelement auswählt:  
  
1.  Das Hauptrahmenfenster empfängt die Befehlsmeldung zuerst.  
  
2.  Das Haupt\-MDI\-Rahmenfenster gibt dem derzeit aktiven untergeordneten MDI\-Fenster eine Möglichkeit, den Befehl zu behandeln.  
  
3.  Das Standardrouting eines untergeordneten MDI\-Rahmenfensters gibt seine Ansicht eine Möglichkeit auf den Befehl, bevor es eine eigene Meldungszuordnung überprüft.  
  
4.  Die Ansicht überprüft eigene Meldungszuordnung zuerst und findet kein Handler, Routen zur folgenden Befehl mit dem zugeordneten Dokument.  
  
5.  Das Dokument überprüft die Meldungszuordnung und sucht einen Handler.  Diese Dokumentmemberfunktion wird und die Routinghalt aufgerufen.  
  
 Wenn das Dokument kein Handler hat, kann er als Nächstes den Befehl zu der Normal\-Vorlage weiterleiten.  Anschließend würde der Befehl zur Ansicht und dann an das Rahmenfenster zurückkehren.  Schließlich wird das Rahmenfenster die Meldungszuordnung überprüfen.  Wenn diese Überprüfungen auch wurde, wird der Befehl an Haupt\-MDI\-Rahmenfenster und dann zum Anwendungsobjekt \- das letztendliche Ziel der nicht behandelten Befehlen weitergeleitet.  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)