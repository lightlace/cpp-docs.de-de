---
title: "Unterstützung für Aktivierungskontexte im MFC-Modulstatus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9a15941848a9e8d5bdf35dfebf273f7684fbb8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Unterstützung für Aktivierungskontexte im MFC-Modulstatus
MFC erstellt einen Aktivierungskontext mithilfe einer Manifestressource, die vom Benutzermodul bereitgestellt. Weitere Informationen wie Aktivierungskontext erstellt werden finden Sie unter den folgenden Themen:  
  
-   [Aktivierungskontext](http://msdn.microsoft.com/library/aa374153)  
  
-   [Anwendungsmanifeste](http://msdn.microsoft.com/library/aa374191)  
  
-   [Assemblymanifeste](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Kontext-Mechanismus zur MFC-Aktivierung Windows SDK-Aktivierungskontext ähnelt, mit dem Unterschied, dass MFC-API der Windows SDK Aktivierung Kontext nicht verwendet, bei diesen Windows SDK-Themen zu lesen.  
  
 Aktivierungskontext funktioniert in MFC-Anwendungen, Benutzer-DLLs und MFC-Erweiterungs-DLLs auf folgende Weise:  
  
-   MFC-Anwendungen verwenden Ressourcen-ID 1 für ihre Manifestressource. In diesem Fall die MFC-Bibliothek erstellt keine eigenen Aktivierungskontext, verwendet jedoch den Standardkontext für die Anwendung.  
  
-   Benutzer der MFC-DLLs verwenden Ressourcen-ID 2 für ihre Manifestressource. In diesem Fall erstellt MFC einen Aktivierungskontext für jede Benutzer-DLL-Datei, damit anderer Benutzer DLLs verschiedene Versionen der gleichen Bibliotheken (z. B. die Common Controls-Bibliothek) verwenden kann.  
  
-   MFC-Erweiterungs-DLLs abhängig ist, deren hosting Anwendungen oder Benutzer DLLs ihre Aktivierungskontext herstellen.  
  
 Obwohl der Aktivierungszustand der Kontext geändert werden kann, mithilfe der Prozesse, die unter beschriebenen [mithilfe der Aktivierung Kontext API](http://msdn.microsoft.com/library/aa376620), mithilfe des Mechanismus der MFC-Aktivierung Kontext kann nützlich sein, bei der Entwicklung von DLL-basierte-Plug-in-Architekturen ist es nicht leicht (oder nicht möglich) manuell Aktivierungsstatus vor und nach Aufrufen der einzelnen externen-Plug-ins wechseln.  
  
 Der Aktivierungskontext wird erstellt, [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Es zerstört wird, der `AFX_MODULE_STATE` Destruktor. Eine Aktivierung Kontexthandle in aufbewahrt `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` beschreiben [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)  
  
 Die [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) Makro aktiviert und deaktiviert den Aktivierungskontext. `AFX_MANAGE_STATE`ist für statische MFC-Bibliotheken sowie MFC-DLLs aktiviert, damit MFC-Code in den richtigen Aktivierungskontext ausgewählt, die von der DLL für die Benutzer ausführen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktivierungskontext](http://msdn.microsoft.com/library/aa374153)   
 [Anwendungsmanifeste](http://msdn.microsoft.com/library/aa374191)   
 [Assemblymanifeste](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

