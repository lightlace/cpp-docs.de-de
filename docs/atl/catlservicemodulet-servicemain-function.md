---
title: "CAtlServiceModuleT::ServiceMain Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceMain"
  - "CServiceModule::ServiceMain"
  - "CServiceModule.ServiceMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ServiceMain method"
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::ServiceMain Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Dienststeuerungs\-Manager \(SCM\) ruft `ServiceMain` auf, wenn Sie die Dienste\-Systemsteuerungs\-Anwendung öffnen, den Dienst auswählen und auf **Start** klicken.  
  
 Nachdem das SCM `ServiceMain` aufruft, muss ein Dienst dem SCM eine Handlerfunktion geben.  Diese Funktion ermöglicht das SCM Abrufen des Status des Diensts und bestimmte Anweisungen übergeben \(wie Anhalten oder Beenden\).  Das SCM ruft diese Funktion wenn die Dienstübergaben **\_Handler** an die Win32\-API, [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054).  \(**\_Handler** ist eine statische Memberfunktion, die die nicht statische Memberfunktion [Handler](../atl/catlservicemodulet-handler-function.md) aufruft\).  
  
 Am Start sollte ein Dienst das SCM über seinen aktuellen Status auch informieren.  Das geschieht, indem **SERVICE\_START\_PENDING** zur Win32\-API, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) übergibt.  
  
 `ServiceMain` ruft dann `CAtlExeModuleT::InitializeCom` auf, das die Win32\-API [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) aufruft.  Standardmäßig wird das `InitializeCom`**COINIT\_MULTITHREADED**\-Flag für die Funktion.  Dieses Flag gibt an, dass das Programm, ein Freethreadserver sein soll.  
  
 Jetzt wird `CAtlServiceModuleT::Run` aufgerufen, um die zentrale Arbeit des Diensts auszuführen.  **Run** wird fortgesetzt, um auszuführen, bis der Dienst beendet wurde.  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)