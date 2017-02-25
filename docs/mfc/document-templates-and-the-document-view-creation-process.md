---
title: "Dokumentvorlagen und der Erstellungsvorgang f&#252;r Dokumente und Ansichten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate-Klasse"
  - "Dokumentvorlagen, und Ansichten"
  - "Dokument-/Ansichtsarchitektur, Erstellen von Dokument/Ansicht"
  - "Symbole, für mehrfache Dokumentvorlagen"
  - "MFC, Dokumentvorlagen"
  - "mehrfache Dokumentvorlage"
  - "einfache Dokumentvorlage"
  - "Vorlagen, Dokumentvorlagen"
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Dokumentvorlagen und der Erstellungsvorgang f&#252;r Dokumente und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um komplexen Erstellung von Dokumenten mit ihren zugeordneten Ansichten und Rahmenfenstern verwalten, verwendet das Framework zwei Dokumentvorlagenklassen: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) für SDI\-Anwendungen und [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) für MDI\-Anwendungen.  `CSingleDocTemplate` kann ein Dokument von einem Typ auf einmal erstellen und speichern.  `CMultiDocTemplate` verwaltet eine Liste einer geöffneten Dokumente aus einem Typ.  
  
 Eine Anwendungsunterstützungsmehrfachverbindungsstellendokumenttypen.  Beispielsweise unterstützt möglicherweise eine Anwendung und Textdokumente Grafikdokumente.  In einer solchen Anwendung wenn der Benutzer den neuen Befehl im Menü Datei auswählt, zeigt eines Dialogfelds eine Liste möglicher neuen Dokumenttypen geöffnet werden.  Für jeden unterstützten Dokumenttyp verwendet die Anwendung eine andere Verzweigungsrichtlinie Dokumentvorlagenobjekt.  Die folgende Abbildung zeigt die Konfiguration einer MDI\-Anwendung, die Unterstützung Dokumenttypen und verschiedenen geöffneten Dokumente angezeigt werden.  
  
 ![MDI&#45;Anwendung mit zwei Dokumenttypen](../mfc/media/vc387h1.png "vc387H1")  
MDI\-Anwendung mit zwei Dokumenttypen  
  
 Dokumentvorlagen werden durch das Anwendungsobjekt erstellt und verwaltet.  Eine die Hauptaufgaben, die während `InitInstance`\-Funktion der Anwendung ausgeführt werden, ist, mindestens Dokumentvorlagen die entsprechende Weise zu erstellen.  Diese Funktion wird in [Dokumentvorlagen\-Erstellung](../mfc/document-template-creation.md) beschrieben.  Das Anwendungsobjekt speichert einen Zeiger auf jeder Normal\-Vorlage in der Vorlagenliste und stellt eine Schnittstelle zum Hinzufügen von Dokumentvorlagen bereit.  
  
 Wenn Sie zwei oder mehr Dokumenttypen unterstützen müssen, müssen Sie einen zusätzlichen Aufruf [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) hinzufügen für jeden Dokumenttyp.  
  
 Ein Symbol wird für jede Normal\-Vorlage anhand der Position in der Liste der Anwendung von Dokumentvorlagen registriert.  Die Reihenfolge von Dokumentvorlagen wird durch die Reihenfolge bestimmt, die sie durch Aufrufe von `AddDocTemplate` hinzugefügt werden.  MFC ist, dass die erste Symbolressource in der Anwendung das Anwendungssymbol, ist die folgende Symbolressource ist das erste Dokumentsymbol, z. B. an.  
  
 Eine dritte Normal\-Vorlage von drei für die Anwendung.  Wenn eine Symbolressource in der Anwendung an Index 3 gibt, wird das Symbol für die Normal\-Vorlage verwendet.  Wenn nicht, wird das Symbol an Index 0 als Standard verwendet.  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument\/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC\-Objekten](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)