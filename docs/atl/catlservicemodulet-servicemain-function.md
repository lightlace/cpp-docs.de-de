---
title: 'CAtlServiceModuleT:: ServiceMain-Funktion | Microsoft-Dokumentation'
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
ms.openlocfilehash: 9dff3fa3f3ed20406955570f2ad72531f4e44f11
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848120"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain-Funktion
Der dienststeuerungs-Manager (SCM) Ruft `ServiceMain` Wenn Sie die Systemsteuerung für die Dienste-Anwendung öffnen, wählen Sie den Dienst, und klicken Sie auf **starten**.  
  
 Nach dem dienststeuerungs-Manager ruft `ServiceMain`, ein Dienst muss dienststeuerungs-Manager eine Handlerfunktion erteilen. Mithilfe dieser Funktion können den SCM-Status des Diensts zu erhalten und übergeben Sie spezifische Anweisungen (z. B. durch das Anhalten oder Beenden). Dienststeuerungs-Manager ruft diese Funktion ab, wenn der Dienst übergibt `_Handler` an die Win32-API-Funktion, [' RegisterServiceCtrlHandler '](http://msdn.microsoft.com/library/windows/desktop/ms685054). (`_Handler` ist eine statische Memberfunktion, die die nicht statische Memberfunktion ruft [Handler](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Beim Start sollte ein Dienst dienststeuerungs-Manager von den aktuellen Status auch darüber informieren. Dies geschieht durch die Übergabe von SERVICE_START_PENDING an die Win32-API-Funktion, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain` Ruft dann `CAtlExeModuleT::InitializeCom`, die Win32-API-Funktion aufruft [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). In der Standardeinstellung `InitializeCom` übergibt das Flag COINIT_MULTITHREADED an die Funktion. Dieses Flag gibt an, dass das Programm ein Freethread-Server sein.  
  
 Jetzt `CAtlServiceModuleT::Run` wird aufgerufen, um die eigentliche Arbeit des Diensts führen. `Run` wird weiterhin ausgeführt, bis der Dienst beendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

