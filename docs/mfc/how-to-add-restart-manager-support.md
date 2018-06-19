---
title: 'Vorgehensweise: Hinzufügen von Unterstützung für den Neustart-Manager | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a2916bd96bf36333a81b2e8a88e62cc8f562e9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351153"
---
# <a name="how-to-add-restart-manager-support"></a>Gewusst wie: Hinzufügen von Unterstützung für den Neustart-Manager

Die Neustart-Manager ist eine Funktion, die Visual Studio für Windows Vista oder höheren Betriebssystemen hinzugefügt. Mit dem Neustart-Manager wird der Anwendung Unterstützung hinzugefügt, wenn sie unerwartet geschlossen oder neu gestartet wird. Das Verhalten des Neustart-Managers hängt vom Typ Ihrer Anwendung ab. Ist Ihre Anwendung ein Dokument-Editor, wird der Anwendung durch den Neustart-Manager ermöglicht, den Status und den Inhalt jedes geöffneten Dokuments automatisch zu speichern, und der Neustart-Manager startet Ihre Anwendung nach einem unerwarteten Schließen neu. Ist Ihre Anwendung kein Dokument-Editor, wird die Anwendung vom Neustart-Manager neu gestartet, dieser kann den Status der Anwendung jedoch nicht standardmäßig speichern.  
  
 Nach dem Neustart wird von der Anwendung ein Aufgabendialogfeld angezeigt, wenn die Anwendung eine Unicode-Anwendung ist. Wenn sie eine ANSI-Anwendung ist, zeigt die Anwendung ein Windows-Meldungsfeld an. An diesem Punkt wählt der Benutzer aus, ob die automatisch gespeicherten Dokumente wiederhergestellt werden sollen. Wenn der Benutzer die automatisch gespeicherten Dokumente nicht wiederherstellt, werden die temporären Dateien vom Neustart-Manager verworfen.  
  
> [!NOTE]
>  Sie können das Standardverhalten des Neustart-Managers hinsichtlich Speichern von Daten und Neustarten der Anwendung überschreiben.  
  
 Standardmäßig erstellt MFC-Anwendungen mit dem Projektassistenten in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] unterstützen Sie den Neustart-Manager aus, wenn die Anwendungen auf einem Computer ausgeführt werden, die Windows Vista oder höher hat. Wenn Sie nicht möchten, dass Ihre Anwendung den Neustart-Manager unterstützt, können Sie den Neustart-Manager im neuen Projekt-Assistenten deaktivieren.  
  
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

