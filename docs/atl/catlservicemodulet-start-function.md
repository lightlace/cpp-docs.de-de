---
title: 'CServiceModule:: Start-Funktion | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs: C++
helpviewer_keywords: Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d4ee7899cda213bf8d8cfd529fd7609976e20d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletstart-function"></a>CServiceModule:: Start-Funktion
Wenn der Dienst ausgeführt wird, **_tWinMain** Aufrufe **CAtlServiceModuleT::WinMain**, die wiederum ruft `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start`ein Array von richtet **SERVICE_TABLE_ENTRY** Strukturen, die jeden Dienst seiner Startfunktion zuordnen. Dieses Array wird dann an die Win32-API-Funktion übergeben [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324). Theoretisch könnte eine EXE-Datei mehrere Dienste behandeln und das Array möglicherweise mehrere **SERVICE_TABLE_ENTRY** Strukturen. Allerdings unterstützt ein ATL-generierter Dienst derzeit nur ein Dienst pro exe-Datei. Das Array verfügt daher über einen einzelnen Eintrag, der den Dienstnamen enthält und **_ServiceMain** wie die Autostart-Funktion. **_ServiceMain** ist eine statische Memberfunktion von `CAtlServiceModuleT` , die nicht statische Memberfunktion aufruft `ServiceMain`.  
  
> [!NOTE]
>  Fehler des **StartServiceCtrlDispatcher** für die Verbindung zum dienststeuerungs-Manager (SCM) wahrscheinlich bedeutet, dass das Programm nicht als Dienst ausgeführt wird. In diesem Fall die Anwendung ruft `CAtlServiceModuleT::Run` direkt, damit das Programm als lokaler Server ausführen kann. Weitere Informationen zum Ausführen des Programms als lokaler Server finden Sie unter [Debuggen Tipps](../atl/debugging-tips.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CServiceModule:: Start](../atl/reference/catlservicemodulet-class.md#start)

