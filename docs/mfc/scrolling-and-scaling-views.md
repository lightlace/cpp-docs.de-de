---
title: "Bildlauf und Skalierung f&#252;r Ansichten | Microsoft Docs"
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
  - "Meldungshandler"
  - "Meldungsbehandlung, Bildlaufleisten in Ansichtsklasse"
  - "Skalierung von Ansichten"
  - "Bildlaufleisten, Meldungen"
  - "Bildlauf von Ansichten"
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Bildlauf und Skalierung f&#252;r Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC unterstützt Ansichten, die den Bildlauf durchführen und Ansichten, die automatisch an die Größe des Rahmenfensters skaliert, das sie anzeigt.  Klasse `CScrollView` unterstützt beide Arten von Ansichten.  
  
 Weitere Informationen zum Bildlauf und Skalierung, Klasse finden Sie unter [CScrollView](../mfc/reference/cscrollview-class.md) in der *MFC\-Referenz*.  Ein Bildlaufbeispiel finden Sie unter [Sie Kritzeln Beispiel](../top/visual-cpp-samples.md).  
  
## Worüber möchten Sie mehr erfahren?  
  
-   Bildlauf einer Ansicht  
  
-   Skalieren einer Ansicht  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f321fcf7c88bc6e3f892ae0fc9b2f0d8" class\="tgtSentence"\>Ansichtskoordinaten\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> Bildlauf einer Ansicht  
 Häufig ist die Größe eines Dokuments größer, als die Größe seiner Ansicht anzeigen kann.  Dies kann auftreten, da die Daten des Dokuments je, oder der Benutzer das Fenster verkleinert, das die Ansicht Formen.  In solchen Fällen muss der Bildlauf unterstützen.  
  
 Jede Ansicht kann Bildlaufleistenmeldungen in den `OnHScroll` \- und `OnVScroll`\-Memberfunktionen bearbeiten.  Sie können entweder BildlaufleistenNachrichtenverarbeitung in diesen Funktionen implementieren und die ganze Arbeit selbst durchführen, oder Sie können die `CScrollView`\-Klasse verwenden, um Bildlauf für Sie zu behandeln.  
  
 `CScrollView` führt Folgendes aus:  
  
-   Verwaltet Fenster und Anzeigebereichsgrößen und \-Zuordnungsmodi  
  
-   Führt automatisch als Reaktion auf Bildlaufleistenmeldungen  
  
 Sie können wie viel angeben, um für eine "Seite" \(wenn der Benutzer in einem Schaft für Bildlaufleiste klickt\) und eine "Zeile" liegen \(wenn der Benutzer in einem Bildlaufpfeil klickt\).  Planen Sie diese Werte, um die Art der Ansicht zu entsprechen.  Sie möchten beispielsweise in Schritten mit 1 Pixel für eine Grafikansicht jedoch in Schrittweiten auf Grundlage die Zeilenhöhe in den Textdokumenten wechseln.  
  
##  <a name="_core_scaling_a_view"></a> Skalieren einer Ansicht  
 Wenn Sie die Ansicht die Größe des Rahmenfensters automatisch anpassen möchten, können Sie `CScrollView` zum Skalieren anstelle des Bildlaufs verwenden.  Die logische Ansicht wird gestreckt oder verkleinert, um den Clientbereich des Fensters genau anzupassen.  Eine skalierte Ansicht enthält keine Bildlaufleisten.  
  
## Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)