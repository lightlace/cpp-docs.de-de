---
title: "Unterst&#252;tzung f&#252;r Aktivierungskontexte im MFC-Modulstatus"
ms.custom: na
ms.date: "12/13/2016"
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
  - "Aktivierungskontext [C++]"
  - "Aktivierungskontext [C++], MFC-Unterstützung"
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Unterst&#252;tzung f&#252;r Aktivierungskontexte im MFC-Modulstatus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC erstellt einen Aktivierungskontext mit einer Manifestressource, die vom Benutzermodul bereitgestellt wird.  Weitere Informationen dazu, wie Aktivierungskontexte erstellt werden, finden Sie unter:  
  
-   [Activation Contexts](http://msdn.microsoft.com/library/aa374153)  
  
-   [Application Manifests](http://msdn.microsoft.com/library/aa374191)  
  
-   [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)  
  
## Hinweise  
 Wenn [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] Sie diese Themen lesen, beachten Sie, dass der MFC\-Aktivierungskontextmechanismus dem [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] Aktivierungskontext mit der Ausnahme ähnelt, dass MFC nicht die [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] Aktivierungs\-Kontext API verwendet.  
  
 Aktivierungskontext funktioniert in MFC\-Anwendungen, Benutzer und in DLLs in Erweiterungs\-DLLs folgendermaßen:  
  
-   MFC\-Anwendungsverwendungs\-Ressourcen\-ID 1 für die Manifestressource.  In diesem Fall erstellt MFC nicht ihren eigenen Aktivierungskontext, verwendet jedoch den Standard\-Anwendungskontext.  
  
-   MFC\-Benutzer DLLs verwenden Ressourcen\-ID 2 für die Manifestressource.  Hier erstellt MFC einen Benutzer Aktivierungskontext für jede DLL, sodass verschiedenen DLLs des Benutzers andere Versionen der gleichen Bibliotheken \(beispielsweise, die Bibliothek zur allgemeinen Steuerelemente\) verwenden.  
  
-   MFC\-Erweiterungs\-DLLs beruhen auf den Hosting\-Anwendungen oder Benutzer DLLs, ihren Aktivierungskontext einzurichten.  
  
 Obwohl der Aktivierungskontextzustand mithilfe der Prozesse geändert werden, die unter [Using the Activation Context API](http://msdn.microsoft.com/library/aa376620) beschrieben werden, mit dem MFC\-Aktivierungskontextmechanismus kann nützlich sein, wenn DLL\-basierte Plug\-In\-Datei Architekturen, Entwickeln, in denen es nicht einfach \(oder\) Aktivierungszustand vor und nach Einzelpersonenaufrufe zu externen Plug\-Ins manuell wechseln nicht möglich ist.  
  
 Der Aktivierungskontext wird in [AfxWinInit](../Topic/AfxWinInit.md).  Sie wird im `AFX_MODULE_STATE` Destruktor zerstört.  Ein Aktivierungskontexthandle wird in `AFX_MODULE_STATE` gespeichert. \(`AFX_MODULE_STATE` wird in [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) beschrieben.\)  
  
 Das Makro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) aktiviert und deaktiviert den Aktivierungskontext.  `AFX_MANAGE_STATE` wird für statischen MFC\-Bibliotheken sowie MFC\-DLLs ermöglicht, MFC\-Code ermöglichen, im richtigen Aktivierungskontext auszuführen, der von der DLL Benutzer ausgewählt wird.  
  
## Siehe auch  
 [Activation Contexts](http://msdn.microsoft.com/library/aa374153)   
 [Application Manifests](http://msdn.microsoft.com/library/aa374191)   
 [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../Topic/AfxWinInit.md)   
 [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md)   
 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md)