---
title: 'TN025: Dokument-, Ansicht- und Frame-Erstellung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.creation
dev_langs: C++
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: da86912b6d5ec1989d55cf6bffbee9732722f8e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Dokument-, Ansicht- und Frame-Erstellung
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Erstellung und zum Eigentum Probleme für WinApps, DocTemplates, Dokumente, Bilder und Ansichten.  
  
## <a name="winapp"></a>WinApp  
 Es ist eine `CWinApp` Objekt im System.  
  
 Wird statisch erstellt und initialisiert, indem interne Implementierung des Frameworks `WinMain`. Leiten Sie von `CWinApp` nützlich, nichts zu tun (Ausnahme: MFC-Erweiterungs-DLLs sollten keine `CWinApp` Instanz – Initialisierung erfolgt in `DllMain` stattdessen).  
  
 Die `CWinApp` Objekt besitzt eine Liste von Dokumentvorlagen (eine `CPtrList`). Es ist mindestens ein Dokumentvorlage pro Anwendung. DocTemplates sind in der Regel aus der Ressourcendatei (d. h. ein Array von Zeichenfolgen) geladen, `CWinApp::InitInstance`.  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```  
  
 Die `CWinApp` Objekt besitzt alle Rahmenfenster in der Anwendung. Das Hauptrahmenfenster für die Anwendung gespeichert werden sollen, im **CWinApp::m_pMainWnd**; legen Sie in der Regel `m_pMainWnd` in die `InitInstance` Implementierung, wenn Sie nicht AppWizard, die Sie erledigen können, haben. Für Einzeldokumentoberfläche (SDI) Dies ist eine `CFrameWnd` , die als das Hauptanwendungsfenster Frame als auch der einzige Dokumentrahmenfenster dient. Bei mehrfachen Dokumentschnittstelle (MDI) ist dies ein MDI-Frame (Klasse `CMDIFrameWnd`), die als das Frame Hauptanwendungsfenster, die das untergeordnete Element enthält dient `CFrameWnd`s. Jedes untergeordnete Fenster ist von der Klasse `CMDIChildWnd` (abgeleitet von `CFrameWnd`) und dient als eine der möglicherweise viele Dokumentrahmenfenster.  
  
## <a name="doctemplates"></a>DocTemplates  
 Die `CDocTemplate` ist der Ersteller und Dokumente. Ist im Besitz der Dokumente, die sie erstellt. Wenn Ihre Anwendung den unten beschriebenen ressourcenbasierte-Ansatz verwendet, müssen sie nicht ableiten `CDocTemplate`.  
  
 Damit eine SDI-Anwendung, die Klasse `CSingleDocTemplate` der nachverfolgt einem geöffneten Dokument. Für eine MDI-Anwendung, die Klasse `CMultiDocTemplate` hält eine Liste (eine `CPtrList`) aller aktuell geöffneten Dokumente, die anhand dieser Vorlage erstellt. `CDocTemplate::AddDocument`und `CDocTemplate::RemoveDocument` stellen Mitglieds der virtuellen Funktionen für das Hinzufügen oder entfernen ein Dokument aus der Vorlage zur Verfügung. `CDocTemplate`ist ein "Friend" **CDocument** , damit wir den geschützten festgelegt, können **CDocument::m_pDocTemplate** rückzeiger auf die zurück auf die Doc-Vorlage verweisen, die das Dokument erstellt hat.  
  
 `CWinApp`Die Standardeinstellung behandelt `OnFileOpen` -Implementierung, die wiederum die Doc-Vorlagen abfragt. Die Implementierung enthält bereits geöffneten Dokumenten gesucht, und entscheiden, welches format Sie für neue Dokumente in zu öffnen.  
  
 `CDocTemplate`verwaltet die UI-Bindung für Dokumente und Bilder.  
  
 `CDocTemplate`verfolgt die Anzahl der unbenannten Dokumente an.  
  
## <a name="cdocument"></a>CDocument  
 Ein **CDocument** ist im Besitz einer `CDocTemplate`.  
  
 Dokumente haben eine Liste der derzeit Ansichten öffnen (abgeleitet `CView`) anzeigen, die das Dokument (eine `CPtrList`).  
  
 Dokumente werden nicht erstellen/Löschen der Sichten, aber sie sind miteinander verbunden, nachdem sie erstellt werden. Wenn ein Dokument geschlossen wird (d. h. durch Datei/schließen), werden alle angefügten Ansichten geschlossen. Wenn die letzte Ansicht für ein Dokument geschlossen wird (d. h., Fenster/schließen) wird das Dokument geschlossen werden.  
  
 Die `CDocument::AddView`, `RemoveView` Schnittstelle wird verwendet, um die Ansicht verwalten. **CDocument** ist ein "Friend" `CView` , damit wir festgelegt, können die **CView::m_pDocument** rückzeiger.  
  
## <a name="cframewnd"></a>CFrameWnd  
 Ein `CFrameWnd` (auch bekannt als Frame) spielt die gleiche Funktion wie in MFC 1.0, aber nun die `CFrameWnd` -Klasse kann in vielen Fällen verwendet werden, ohne das Ableiten einer neuen Klasse. Die abgeleiteten Klassen `CMDIFrameWnd` und `CMDIChildWnd` sind ebenfalls verbessert werden, so viele Standardbefehle bereits implementiert werden.  
  
 Die `CFrameWnd` ist verantwortlich für das Erstellen von Windows im Clientbereich des Frames. Normalerweise ist ein Hauptfenster, füllen das den Clientbereich des Frames.  
  
 Für ein MDI-Rahmenfenster ist der Clientbereich mit dem Steuerelement MDICLIENT gefüllt wiederum das übergeordnete Element der alle untergeordneten MDI-Rahmenfenster ist. Für eine SDI-Rahmenfensters oder eine untergeordnete MDI-Rahmenfenster wird in der Regel der Clientbereich mit gefüllt eine `CView`-Fensterobjekt abgeleitet. Im Fall von `CSplitterWnd`, das den Clientbereich der Ansicht mit gefüllt ist die `CSplitterWnd` Window-Objekt, und die `CView`-abgeleiteten Fensterobjekten (eine pro Teilbereichs) werden als untergeordnete Fenster erstellt die `CSplitterWnd`.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

