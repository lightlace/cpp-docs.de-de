---
title: CAtlServiceModuleT::ServiceMain Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs:
- C++
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9936090793890b1e33f0d5e29787d65f378afa84
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355573"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT::ServiceMain-Funktion
Ruft der dienststeuerungs-Manager (SCM) `ServiceMain` Wenn Sie die Anwendung Dienste in der Systemsteuerung öffnen, wählen Sie den Dienst, und klicken Sie auf **starten**.  
  
 Ruft nach dem SCM `ServiceMain`, ein Dienst muss dem SCM eine Handlerfunktion erteilen. Diese Funktion ermöglicht den SCM, der Status des Dienstes zu erhalten und übergeben Sie spezifische Anweisungen (z. B. durch das Anhalten oder Beenden). SCM ruft diese Funktion aus, wenn der Dienst übergibt **_Handler** der Win32-API-Funktion, [' RegisterServiceCtrlHandler '](http://msdn.microsoft.com/library/windows/desktop/ms685054). (**_Handler** ist eine statische Memberfunktion, die nicht statische Memberfunktion aufruft [Handler](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Beim Start sollte ein Dienst auch SCM über seinen aktuellen Status informieren. Dies geschieht durch übergeben **SERVICE_START_PENDING** der Win32-API-Funktion, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain` Ruft dann `CAtlExeModuleT::InitializeCom`, die Win32-API-Funktion aufruft [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). Standardmäßig `InitializeCom` übergibt die **COINIT_MULTITHREADED** Flag an die Funktion. Dieses Flag gibt an, dass das Programm eine Freethread-Server sein.  
  
 Jetzt `CAtlServiceModuleT::Run` aufgerufen, um die Hauptarbeit des Dienstes vorzunehmen. **Führen Sie** wird weiterhin ausgeführt, bis der Dienst beendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

