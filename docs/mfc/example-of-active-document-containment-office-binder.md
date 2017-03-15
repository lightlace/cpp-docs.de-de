---
title: "Beispiel f&#252;r einen Active Document-Container: Office Binder | Microsoft Docs"
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
  - "Active Document-Container [C++], Beispiele"
  - "Aktive Dokumente [C++], Container"
  - "Container [C++], aktives Dokument"
  - "Beispiele [C++], Active Document-Einschluss"
  - "MFC-COM [C++], Active Document-Einschluss"
  - "Office Sammelmappen"
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Beispiel f&#252;r einen Active Document-Container: Office Binder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Microsoft Office\-Binder ist ein Beispiel eines Active Document\-Container.  Ein sollte enthält zwei primäre Bereiche, wie Container in der Regel führen.  Der linke Bereich enthält Symbole, die aktiven Dokumenten in der Sammelmappe entsprechen.  Jedes Dokument wird einen *Abschnitt* innerhalb des Binders aufgerufen.  Beispielsweise kann ein Binder Word\-Dokumente, PowerPoint enthalten Dateien, Excel\-Arbeitsblätter, u. a.  
  
 Durch Klicken auf ein Symbol im linken Bereich können das entsprechende aktive Dokument.  Der rechte Bereich des Binders zeigt dann den Inhalt des derzeit ausgewählten aktiven Dokuments an.  
  
 Wenn Sie ein in einem Word\-Dokument Binder öffnen und aktivieren, werden die Word\-Menüleiste und Symbolleisten in der Ansichtsframe, und Sie können den Inhalt des Dokuments mit einem beliebigen Word\-Befehls oder Tools bearbeiten.  Allerdings wird die Menüleiste eine Kombination der Menüleiste des Binders und Word.  Da Binder und Word **Hilfe** Menüs verfügen, wird der Inhalt der beiden Menüs zusammengeführt.  Active Document\-Container wie sollte automatisch bereitstellen **Hilfe** Menüzusammenführung; Weitere Informationen finden Sie unter [Menü Hilfe\-Zusammenführen](../mfc/help-menu-merging.md).  
  
 Wenn Sie ein aktives Dokument eines anderen Anwendungstyps auswählen, wird die Schnittstelle des Binders, um die des aktiven Anwendungstyps des Dokuments angepasst.  Wenn beispielsweise ein Binder ein Excel\-Arbeitsblatt enthält, beachten Sie, dass die Menüs in der Sammelmappe ändern, wenn Sie den Excel\-Arbeitsblattabschnitt auswählen.  
  
 Es ist natürlich Andere Typen Container neben Bindern.  Datei\-Explorer wird die typische DualBereichsschnittstelle, in der der linke Bereich ein Strukturansicht\-Steuerelement verwendet, um eine hierarchische Liste von Verzeichnissen in einem Laufwerk oder in einem Netzwerk anzuzeigen, während im rechten Bereich die Dateien angezeigt, die im aktuell ausgewählten Verzeichnis enthalten sind.  Ein Internet\-BrowserTyp Containern \(wie Microsoft Internet Explorer\), anstelle einer DualBereichsschnittstelle, normalerweise hat einzelnen Frames und stellt Navigation mit den Links bereit.  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containment.md)