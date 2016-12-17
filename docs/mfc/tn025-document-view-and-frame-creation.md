---
title: "TN025: Dokument-, Ansicht- und Frame-Erstellung"
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
  - "vc.creation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dokumente, Ansicht- und Frame-Erstellung"
  - "TN025"
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# TN025: Dokument-, Ansicht- und Frame-Erstellung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Erstellungs\- und Besitzprobleme für WinApps, DocTemplates, Dokumente, Felder und Ansichten.  
  
## WinApp  
 Es gibt ein `CWinApp`\-Objekt im System.  
  
 Es wird als static von der internen Implementierung des Frameworks von `WinMain` erstellt und initialisiert.  Sie müssen von `CWinApp` ableiten, um nützliche dieselben Aktionen \(Ausnahme: Erweiterungs\-DLLs sollten eine `CWinApp`\-Instanz nicht haben \- Initialisierung ist in `DllMain` stattdessen ausgeführt\).  
  
 Das ein `CWinApp`\-Objekt besitzt eine Liste von Dokumentvorlagen \( `CPtrList`\).  Es gibt eine oder mehrere Aufhebungen Normal\-Vorlage pro Anwendung.  DocTemplates werden normalerweise aus der Ressourcendatei \(das heißt, ein Array aus Zeichenfolgen\) in eine `CWinApp::InitInstance` geladen.  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);  
AddDocTemplate(pTemplate);  
```  
  
 Das ein `CWinApp`\-Objekt besitzt Rahmenfenster alle in der Anwendung.  Das Hauptrahmenfenster für die Anwendung sollte in **CWinApp::m\_pMainWnd** gespeichert werden; Regel führen Sie `m_pMainWnd` in der `InitInstance` \- Implementierung, ohne Anwendungs\-Assistenten gelassen, sie für Sie.  Für \(Single Document Interface \(SDI\) ist dieses ein `CFrameWnd`, das als Hauptanwendungsrahmenfenster sowie das einzige Dokumentrahmenfenster dient.  Bei mehrfachen Dokumentschnittstelle \(MDI\) ist dies MDI\-Frame \(Klasse `CMDIFrameWnd`\) diese Dient als das Hauptanwendungsrahmenfenster, das das gesamte untergeordnete `CFrameWnd`s enthält.  Jedes untergeordnete Fenster ist von der `CMDIChildWnd`\-Klasse \(abgeleitet von `CFrameWnd`\) und den dienen als eines möglicherweise viele Dokumentrahmenfenster.  
  
## DocTemplates  
 `CDocTemplate` ist der Ersteller und der Manager von Dokumenten.  Es besteht die Dokumente, die es erstellt.  Wenn die Anwendung den ressourcenbasierten unten beschriebenen Vorgehensweise verwendet, braucht sie nicht, um von `CDocTemplate` abgeleitet.  
  
 Eine SDI\-Anwendung wird die Klasse `CSingleDocTemplate` ein geöffnetes Dokument nachverfolgt.  Für eine MDI\-Anwendung übergibt die Klasse `CMultiDocTemplate` eine Liste \( `CPtrList`\) aller aktuell geöffneten Dokumente, die von dieser Vorlage erstellt werden.  `CDocTemplate::AddDocument` und `CDocTemplate::RemoveDocument` stellen die virtuellen Memberfunktionen zum Hinzufügen oder Entfernen eines Dokuments von der Vorlage bereitgestellt.  `CDocTemplate` ist ein Friend von **CDocument**, sodass wir den geschützten **CDocument::m\_pDocTemplate** Rückseitenzeiger auf Punkt zurück zu der Dokumente. der Quellvorlage festlegen, die das Dokument erstellt.  
  
 `CWinApp` behandelt die standardmäßige `OnFileOpen` Implementierung, die wiederum alle Dokumente. Vorlagen unterstützen.  In die Implementierung einschließt nach bereits geöffneten Dokumenten suchen und den Einsatzmöglichkeiten, welches Format, zu öffnen neuer Dokumenten.  
  
 `CDocTemplate` verwaltet die Benutzeroberflächenbindung für Dokumente und Frame.  
  
 `CDocTemplate` enthält die Anzahl von unbenannten Dokumenten.  
  
## CDocument  
 **CDocument** wird über `CDocTemplate` gehören.  
  
 Dokumente verfügen eine Liste der momentan geöffneten Ansichten \(abgeleitet von `CView`\) dass das Dokument angezeigt \( `CPtrList`\).  
  
 Dokumente erstellen nicht,\/zerstören die Ansichten, jedoch werden aneinander angefügt, nachdem sie erstellt wurden.  Wenn ein Dokument, also nach Dateien\/Schließen\) geschlossen ist, werden alle angefügten Ansichten geschlossen.  Wenn die letzte Ansicht eines Dokument geschlossen wird \(das bedeutet, Fenster\/Schließen\) wird das Dokument geschlossen.  
  
 `CDocument::AddView`, `RemoveView`\-Schnittstelle wird, um die Ansichtsliste zu übergeben.  **CDocument** ist ein Friend von `CView`, sodass wir den **CView::m\_pDocument** Rückseitenzeiger festlegen.  
  
## CFrameWnd  
 `CFrameWnd` \(auch Frames\) gibt der gleichen Rolle wie in MFC 1.0, aber jetzt der `CFrameWnd`\-Klasse wird entworfen, in vielen Fällen verwendet werden, ohne erneut eine neue Klasse zu berechnen.  Die abgeleiteten Klassen `CMDIFrameWnd` und `CMDIChildWnd` werden auch so viele Standardbefehle werden implementiert bereits erhöht.  
  
 `CFrameWnd` ist zum Erstellen von Fenstern im Clientbereich der Frames zuständig.  Normalerweise liegt ein Hauptfenster, das den Clientbereich der Frames ausfüllt.  
  
 Ein MDI\-Framefenster wird der Clientbereich mit dem MDICLIENT\-Steuerelement gefüllt, das wiederum das übergeordnete Element aller untergeordneten MDI\-Rahmenfenster ist.  Ein SDI\-Framefenster oder ein untergeordnetes MDI\-Rahmenfenster wird der Clientbereich normalerweise mit `CView` abgeleitetes Window\-Objekt gefüllt.  Bei `CSplitterWnd` wird der Clientbereich der Ansicht mit dem Window\-Objekt `CSplitterWnd` und `CView` gefüllt abgeleitete Fensterobjekte \(eines pro geteilten Bereich\) werden als untergeordnete Fenster `CSplitterWnd` erstellt.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)