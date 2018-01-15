---
title: "Vorgehensweise: Hinzufügen von Unterstützung für den Neustart-Manager | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a413f28909a52e3bc82e9d8f2694d559bf8a885c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-restart-manager-support"></a>Gewusst wie: Hinzufügen von Unterstützung für den Neustart-Manager
Der Neustart-Manager ist ein Feature, das [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] für [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]hinzugefügt wurde. Mit dem Neustart-Manager wird der Anwendung Unterstützung hinzugefügt, wenn sie unerwartet geschlossen oder neu gestartet wird. Das Verhalten des Neustart-Managers hängt vom Typ Ihrer Anwendung ab. Ist Ihre Anwendung ein Dokument-Editor, wird der Anwendung durch den Neustart-Manager ermöglicht, den Status und den Inhalt jedes geöffneten Dokuments automatisch zu speichern, und der Neustart-Manager startet Ihre Anwendung nach einem unerwarteten Schließen neu. Ist Ihre Anwendung kein Dokument-Editor, wird die Anwendung vom Neustart-Manager neu gestartet, dieser kann den Status der Anwendung jedoch nicht standardmäßig speichern.  
  
 Nach dem Neustart wird von der Anwendung ein Aufgabendialogfeld angezeigt, wenn die Anwendung eine Unicode-Anwendung ist. Wenn sie eine ANSI-Anwendung ist, zeigt die Anwendung ein Windows-Meldungsfeld an. An diesem Punkt wählt der Benutzer aus, ob die automatisch gespeicherten Dokumente wiederhergestellt werden sollen. Wenn der Benutzer die automatisch gespeicherten Dokumente nicht wiederherstellt, werden die temporären Dateien vom Neustart-Manager verworfen.  
  
> [!NOTE]
>  Sie können das Standardverhalten des Neustart-Managers hinsichtlich Speichern von Daten und Neustarten der Anwendung überschreiben.  
  
 Standardmäßig bieten MFC-Anwendungen, die mit Projekt-Assistenten in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] erstellt wurden, Unterstützung für den Neustart-Manager, wenn die Anwendungen auf einem Computer ausgeführt werden, auf dem [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]installiert ist. Wenn Sie nicht möchten, dass Ihre Anwendung den Neustart-Manager unterstützt, können Sie den Neustart-Manager im neuen Projekt-Assistenten deaktivieren.  
  
### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>So fügen Sie einer vorhandenen Anwendung Unterstützung für den Neustart-Manager hinzu  
  
1.  Öffnen eine vorhandene MFC-Anwendung in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
2.  Öffnen Sie die Quelldatei für Ihre Hauptanwendung. Standardmäßig ist dies die CPP-Datei, die denselben Namen wie Ihre Anwendung hat. Die Hauptanwendungsquelldatei für „MeinProjekt“ ist beispielsweise „MeinProjekt.cpp“.  
  
3.  Suchen Sie nach dem Konstruktor für Ihre Hauptanwendung. Hat Ihr Projekt beispielsweise den Namen „MeinProjekt“, ist `CMyProjectApp::CMyProjectApp()`der Konstruktor.  
  
4.  Fügen Sie dem Konstruktor die folgende Codezeile hinzu.  
  
 ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
 ```  
  
5.  Stellen Sie sicher, dass in der `InitInstance` -Methode Ihrer Anwendung deren übergeordnete `InitInstance` -Methode aufgerufen wird: [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) oder `CWinAppEx::InitInstance`hinzugefügt wurde. Aufgabe der `InitInstance` -Methode ist es, den `m_dwRestartManagerSupportFlags` -Parameter zu überprüfen.  
  
6.  Kompilieren Sie Ihre Anwendung, und führen Sie sie aus.  
  
## <a name="see-also"></a>Siehe auch  
 [CDataRecoveryHandler-Klasse](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)   
 [CWinApp-Klasse](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)   
 [CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)

