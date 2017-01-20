---
title: "CAtlServiceModuleT::Start Function"
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
  - "CServiceModule.Start"
  - "CServiceModule::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start-Methode"
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Start Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn der Dienst durchgeführt wird, ruft **\_tWinMain CAtlServiceModuleT::WinMain** auf, der wiederum `CAtlServiceModuleT::Start` aufruft.  
  
 `CAtlServiceModuleT::Start` installieren ein Array **SERVICE\_TABLE\_ENTRY**\-Strukturen, die jeden Dienst zu seiner Startfunktion zuordnen.  Dieses Array wird dann zur Win32\-API, [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324) übergeben.  Theoretisch kann eine EXE\-Datei mehrere behandeln und das Array kann über mehrere **SERVICE\_TABLE\_ENTRY**\-Strukturen verfügen.  Derzeit jedoch ATL\-generierte Dienst nur ein Dienst pro EXE.  Deshalb hat das Array einen einzelnen Eintrag, der den Dienstnamen und **\_ServiceMain** als Startfunktion enthält.  **\_ServiceMain** ist eine statische Memberfunktion der `CAtlServiceModuleT`, die die nicht statische Memberfunktion aufruft, `ServiceMain`.  
  
> [!NOTE]
>  Überschneidungen mit **StartServiceCtrlDispatcher**, an den Dienststeuerungs\-Manager \(SCM\) herzustellen wahrscheinlich bedeutet, dass das Programm nicht als Dienst ausgeführt wird.  In diesem Fall ruft das Programm `CAtlServiceModuleT::Run` direkt auf, damit das Programm als lokalen Server ausgeführt werden kann.  Weitere Informationen zum Ausführen des Programms als lokalen Server, finden Sie unter [Tipps zum Debuggen](../atl/debugging-tips.md).  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)