---
title: Hinzufügen eines ATL-OLE DB-Consumers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90b16c84c0dc2c921722c4c80a1e2bdf0e091d9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356353"
---
# <a name="adding-an-atl-ole-db-consumer"></a>Hinzufügen eines ATL-OLE DB-Consumers
Verwenden Sie diesen Assistenten zum Hinzufügen eines ATL-OLE DB-Consumers zu einem Projekt ein. Ein ATL-OLE DB-Consumer besteht aus einer OLE DB-Accessor-Klasse und datenbindungen notwendig, eine Datenquelle zugreifen. Das Projekt muss wurde als eine ATL-COM-Anwendung oder als ein MFC- oder Win32-Anwendung mit ATL-Unterstützung (ATL-OLE DB-Consumer-Assistenten automatisch hinzugefügt) erstellt.  
  
 **Hinweis** können Sie einen OLE DB-Consumer zu einem MFC-Projekt hinzufügen. Wenn Sie dies tun, fügt der ATL-OLE DB-Consumer-Assistent die notwendige COM-Unterstützung zu Ihrem Projekt. Dabei wird vorausgesetzt, dass Sie beim Erstellen von MFC-Projekt ausgewählt der **ActiveX-Steuerelemente** Kontrollkästchen (in der **erweiterte Funktionen** auf der Seite der Assistent für MFC-Anwendung), die standardmäßig aktiviert ist. Nach Auswahl dieser Option wird sichergestellt, dass die Anwendung aufruft, **CoInitialize** und **CoUninitialize**. Wenn Sie nicht ausgewählt haben **ActiveX-Steuerelemente** , wenn Sie die MFC-Projekt erstellt haben, müssen Sie aufrufen **CoInitialize** und **CoUninitialize** im Haupt-Code.  
  
### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Hinzufügen ein ATL-OLE DB-Consumers zu Ihrem Projekt  
  
1.  In der Klassenansicht mit der rechten Maustaste des Projekts. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.  
  
2.  Doppelklicken Sie in der Visual C++-Ordner auf dem **ATL-OLE DB-Consumer** Symbol oder wählen Sie ihn, und klicken Sie auf **öffnen**.  
  
     ATL-OLE DB-Consumer-Assistent wird geöffnet.  
  
3.  Hiermit werden Einstellungen wie in beschrieben [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).  
  
4.  Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen. Der neu erstellte OLE DB-Consumer-Code wird in Ihrem Projekt eingefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)

