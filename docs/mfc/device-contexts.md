---
title: "Ger&#228;tekontexte | Microsoft Docs"
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
  - "BeginPaint-Methode, CPaintDC"
  - "CClientDC-Klasse, und GetDC-Methode"
  - "CClientDC-Klasse, und ReleaseDC-Methode"
  - "CDC-Klasse, Objekte"
  - "Clientbereiche"
  - "Clientbereiche, und Gerätekontext"
  - "CMetaFileDC-Klasse, und OnPrepareDC-Methode"
  - "CPaintDC-Klasse, Gerätekontext für das Pixelbild"
  - "Gerätekontexte [C++]"
  - "Gerätekontexte [C++], Informationen über Gerätekontexte"
  - "Gerätekontexte [C++], CDC-Klasse"
  - "Geräteunabhängige Zeichnung"
  - "Zeichnen, Gerätekontext"
  - "Zeichnen, direkt in Windows"
  - "Zeichnen, in Maus- und Gerätekontexten"
  - "EndPaint-Methode"
  - "Rahmenfenster [C++], Gerätekontexte"
  - "GDI-Objekte [C++], Gerätekontexte"
  - "GetDC-Methode und CClientDC-Klasse"
  - "Grafikobjekte, Gerätekontexte"
  - "Metadateien und Gerätekontexte"
  - "Maus [C++], Zeichnungs- und Gerätekontexte"
  - "OnPrepareDC-Methode"
  - "Pixelbild- und Gerätekontext"
  - "Drucker [C++], Gerätekontexte"
  - "ReleaseDC-Methode"
  - "Benutzeroberfläche [C++], Gerätekontexte"
  - "Fenster [C++], und Gerätekontext"
  - "Fenster [C++], direkt zeichnen in"
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ger&#228;tekontexte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Gerätekontext ist eine Windows\-Datenstruktur, die Informationen über die Zeichnungsattribute eines Geräts wie eine Anzeige oder Drucker enthält.  Alle Zeichnungsaufrufe werden durch ein Gerätekontextobjekt ausgeführt, sodass Windows\-APIs zum Zeichnen von Linien, von Formen und Text kapselt.  Gerätekontexte ermöglichen geräteunabhängige Zeichnungen in Windows.  Gerätekontexte können verwendet werden, um dem Bildschirm, den Drucker oder auf eine Metadatei zu zeichnen.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) kapseln Objekte des allgemeinen Vorgehensweise von Windows, um die Funktion `BeginPaint`, dann Zeichnung im Gerätekontext auf, und rufen die `EndPaint`\-Funktion auf.  Der `CPaintDC`\-Konstruktor ruft `BeginPaint` für Sie auf, und der Destruktor ruft `EndPaint` auf.  Der vereinfachte Prozess ist, das [CDC](../mfc/reference/cdc-class.md)\-Objekt erstellt, gezeichnet und anschließend zerstört das `CDC`\-Objekt.  Im Framework wird viel sogar dieses Prozesses automatisiert.  Insbesondere der Funktion wird `OnDraw` bereits vorbereitetes `CPaintDC` \(über `OnPrepareDC`\) übergeben, und Sie zeichnen einfach in es.  Es wird durch das Framework zerstört und der zugrunde liegende Gerätekontext wird Windows nach Rückgabe aus dem Aufruf von `OnDraw` der Funktion freigegeben.  
  
 Objekte [CClientDC](../mfc/reference/cclientdc-class.md) kapseln das Arbeiten mit einem Gerätekontext, der nur den Clientbereich eines Fensters gezeigt.  Der `CClientDC`\-Konstruktor ruft die Funktion `GetDC` und die Destruktoraufrufe die Funktion `ReleaseDC` auf.  [CWindowDC](../mfc/reference/cwindowdc-class.md) kapseln Objekte einem Gerätekontext, der das gesamte Fenster darstellt, einschließlich seiner Frames.  
  
 Objekte [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) kapseln Zeichnungen eine Windows\-Metadatei.  Im Gegensatz zu `CPaintDC`, das an `OnDraw` übergeben wird, muss [OnPrepareDC](../Topic/CView::OnPrepareDC.md) in diesem Fall selbst aufrufen.  
  
## Maus\-Zeichnung  
 Die häufigste Zeichnungen in einem Rahmenprogramm \- und somit die meisten Gerätekontextarbeit \- ist dies in der Memberfunktion `OnDraw` der Ansicht.  Sie können jedoch Gerätekontextobjekte weiterhin zu anderen Zwecken verwenden.  Um beispielsweise für Nachverfolgungsfeedback Mausbewegung in einer Ansicht bereitzustellen, müssen Sie direkt in die Ansicht ohne Warteaufgerufen werden `OnDraw`, zeichnen.  
  
 In einem solchen Fall können Sie ein [CClientDC](../mfc/reference/cclientdc-class.md) Gerätekontextobjekt verwenden, um direkt in der Ansicht zu zeichnen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="a12b51e88715aef1e34dc9b8f4447117" class\="tgtSentence"\>Gerätekontexte \(Definition\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Interpretieren der Benutzereingaben über eine Ansicht](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f3dbb554cb14503827bf0ebda53953d7" class\="tgtSentence"\>Linien und Kurven\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [\<caps:sentence id\="tgt26" sentenceid\="365f749101c5eabc8b3be48de1dc3d6b" class\="tgtSentence"\>Ausgefüllte Formen\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [\<caps:sentence id\="tgt27" sentenceid\="dc86a6302992c2d9f64d0fc6a8cfef75" class\="tgtSentence"\>Schriftarten und Text\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="62848e3ce5804aa985513a7922ff87b2" class\="tgtSentence"\>Farben\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="ee85800dfcba9a5bdf11f101e1bbadeb" class\="tgtSentence"\>Transformationen und Koordinatensysteme\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)