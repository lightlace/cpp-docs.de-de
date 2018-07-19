---
title: Beziehungen zwischen MFC-Objekten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef6a9e605948fac4f31338f87b4d00bbaa8712f4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931651"
---
# <a name="relationships-among-mfc-objects"></a>Beziehungen zwischen MFC-Objekten
Dokument-/Ansichtarchitektur-Erstellungsprozess in Perspektive zu versetzen, beachten Sie, um ein aktives Programm: ein Dokument, das Rahmenfenster verwendet, um die Ansicht enthält und die Ansicht, die dem Dokument zugeordnet.  
  
-   Ein Dokument hält eine Liste der Ansichten des Dokuments und einen Zeiger zur Dokumentvorlage, die das Dokument erstellt hat.  
  
-   Eine Sicht und dabei einen Zeiger auf das Dokument und ist ein untergeordnetes Element des übergeordneten Fensters Frame.  
  
-   Einem Dokumentrahmenfenster und dabei einen Zeiger auf die zurzeit aktive Sicht.  
  
-   Eine Dokumentvorlage hält eine Liste der geöffneten Dokumente.  
  
-   Die Anwendung behält eine Liste ihrer Dokumentvorlagen.  
  
-   Windows behält den Überblick über allen geöffneten Fenstern, damit sie Nachrichten senden kann.  
  
 Diese Beziehungen werden während der Erstellung der Dokument-/Ansichtarchitektur eingerichtet. Die folgende Tabelle zeigt, wie Objekte in einem ausgeführten Programm auf andere Objekte zugreifen können. Jedes Objekt kann einen Zeiger auf das Anwendungsobjekt abrufen, indem Sie die globale Funktion aufrufen [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).  
  
### <a name="gaining-access-to-other-objects-in-your-application"></a>Zugriff auf andere Objekte in der Anwendung  
  
|Vom Objekt|Gewusst wie: Zugriff auf andere Objekte|  
|-----------------|---------------------------------|  
|Dokument|Verwendung [Sie GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) und [GetNextView](../mfc/reference/cdocument-class.md#getnextview) Zugriff auf das Dokument anzeigen Liste.<br /><br /> Rufen Sie [Sie GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) um das Dokumentvorlage abzurufen.|  
|Ansicht|Rufen Sie [GetDocument](../mfc/reference/cview-class.md#getdocument) des Dokuments abgerufen.<br /><br /> Rufen Sie [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) das Rahmenfenster abgerufen.|  
|Dokumentrahmenfenster|Rufen Sie [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) zum Abrufen der aktuellen Ansicht.<br /><br /> Rufen Sie [Sie GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) der aktuellen Ansicht angefügte Dokument abgerufen.|  
|MDI-Rahmenfenster|Rufen Sie [Sie MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) die derzeit aktiven abzurufenden [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|  
  
 In der Regel ein Framefenster verfügt eine Ansicht, aber in manchen Fällen enthält das gleiche Rahmenfenster wie Splitterfenster, mehrere Ansichten. Das Rahmenfenster und dabei einen Zeiger auf die momentan aktiven Ansicht; der Zeiger wird jedes Mal aktualisiert, an einer anderen Ansicht aktiviert wird.  
  
> [!NOTE]
>  Ein Zeiger auf das Hauptrahmenfenster befindet sich in der [M_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) Membervariable des Anwendungsobjekts. Einen Aufruf von `OnFileNew` in Ihre Überschreibung der `InitInstance` Memberfunktion von `CWinApp` legt *M_pMainWnd* für Sie. Wenn Sie nicht aufrufen `OnFileNew`, müssen Sie den Wert der Variablen in festlegen `InitInstance` selbst. (SDI-COM-Komponente (Server)-Anwendungen möglicherweise nicht die Variable festgelegt, wenn Embedding in der Befehlszeile angegeben ist.) Beachten Sie, dass *M_pMainWnd* ist jetzt ein Member der Klasse `CWinThread` statt `CWinApp`.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

