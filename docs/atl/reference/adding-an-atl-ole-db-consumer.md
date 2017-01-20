---
title: "Hinzuf&#252;gen eines ATL-OLE DB-Consumers"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-OLE DB-Consumer"
  - "ATL-Projekte, Hinzufügen von ATL-OLE DB-Consumern"
  - "OLE DB, Hinzufügen von ATL-OLE DB-Consumern zu Projekten"
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen eines ATL-OLE DB-Consumers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe dieses Assistenten fügen Sie einem Projekt einen ATL\-OLE DB\-Consumer hinzu.  Ein ATL\-OLE DB\-Consumer besteht aus einer OLE DB\-Accessorklasse und Datenbindungen, die für den Zugriff auf eine Datenquelle erforderlich sind.  Voraussetzung ist, dass das Projekt als ATL COM\-Anwendung oder als MFC\- bzw. Win32\-Anwendung mit integrierter ATL\-Unterstützung erstellt wurde \(diese wird vom ATL\-OLE DB\-Consumer\-Assistenten automatisch hinzugefügt\).  
  
 **Hinweis**  können Sie einen OLE DB\-Consumer zu einem MFC\-Projekt hinzufügen.  Wenn Sie dies tun, fügt der ATL OLE DB\-Consumer\-Assistent dem Projekt die notwendige COM\-Unterstützung hinzu.  Dabei wird davon ausgegangen, dass Sie beim Erstellen des MFC\-Projekts das Kontrollkästchen **ActiveX\-Steuerelemente** \(auf der Seite **Erweiterte Features** des MFC\-Projektanwendungs\-Assistenten\) aktiviert haben, das standardmäßig aktiviert ist.  Durch das Auswählen dieser Option wird sichergestellt, dass die Anwendung **CoInitialize** und **CoUninitialize** aufruft.  Wenn Sie beim Erstellen des MFC\-Projekts das Kontrollkästchen **ActiveX\-Steuerelemente** nicht aktiviert haben, müssen Sie **CoInitialize** und **CoUninitialize** im Hauptcode aufrufen.  
  
### So fügen Sie dem Projekt einen ATL\-OLE DB\-Consumer hinzu  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf das Projekt.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
2.  Doppelklicken Sie im Visual C\+\+\-Ordner auf das Symbol **ATL\-OLE DB\-Consumer**, oder markieren Sie es, und klicken Sie auf **Öffnen**.  
  
     Der ATL\-OLE DB\-Consumer\-Assistent wird geöffnet.  
  
3.  Legen Sie die Einstellungen fest, wie unter [ATL\-OLE DB\-Consumer\-Assistent](../../atl/reference/atl-ole-db-consumer-wizard.md) beschrieben.  
  
4.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.  Der Code für den neu erstellten OLE DB\-Consumer wird in das Projekt eingefügt.  
  
## Siehe auch  
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)