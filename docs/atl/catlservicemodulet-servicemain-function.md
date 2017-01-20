---
title: "CAtlServiceModuleT::ServiceMain Function"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
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