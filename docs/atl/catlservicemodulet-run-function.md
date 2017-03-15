---
title: "CAtlServiceModuleT::Run Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Run"
  - "CServiceModule.Run"
  - "CSecurityDescriptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Dienste, Sicherheit"
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CAtlServiceModuleT::Run Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Run** enthält Aufrufe `PreMessageLoop`, zu `RunMessageLoop` und zu `PostMessageLoop`.  Nachdem er aufgerufen wurde speichert `PreMessageLoop` zuerst ID der Thread des Diensts  Der Dienst verwendet diese ID, um zu schließen, indem er eine **WM\_QUIT** Meldung mithilfe der Win32\-API, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) sendet.  
  
 `PreMessageLoop` ruft dann `InitializeSecurity` auf.  Standardmäßig ruft `InitializeSecurity`[CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) mit der Sicherheitsbeschreibung auf, die festgelegt wird, um in NULL, was bedeutet, dass jeder Benutzer Zugriff auf das Objekt verfügt.  
  
 Wenn Sie den Dienst seine eigene Sicherheit nicht angeben möchten, rufen `PreMessageLoop` Überschreibung und nicht `InitializeSecurity` auf, und COM bestimmt dann die Sicherheitseinstellungen aus der Registrierung.  Eine einfache Möglichkeit, Registrierungseinstellungen konfiguriert ist mit dem [DCOMCNFG](../atl/dcomcnfg.md) Hilfsprogramm, das weiter unten in diesem Abschnitt erläutert wird.  
  
 Sobald Sicherheit angegeben wird, wird das Objekt mit COM registriert, damit neue Clients an das Programm herstellen können.  Schließlich wird das Programm dem Dienststeuerungs\-Manager \(SCM\) ausgeführt wird und dass das Programm eine Nachrichtenschleife eingibt.  Das Programm wird ausgeführt, bis es eine fehlgeschlagene Meldung nach Dienstherunterfahren sendet.  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CSecurityDesc Class](../atl/reference/csecuritydesc-class.md)   
 [CSid Class](../atl/reference/csid-class.md)   
 [CDacl Class](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)