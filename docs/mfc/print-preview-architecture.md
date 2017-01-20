---
title: "Druckvorschauarchitektur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Druckvorschau"
  - "Seitenansicht, Architektur"
  - "Seitenansicht, Änderungen an MFC"
  - "Seitenansicht, Prozess"
  - "Drucken [MFC], Seitenansicht"
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Druckvorschauarchitektur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie das MFC\-Framework Seitenansichtsfunktionalität implementiert.  Folgende Themen werden behandelt:  
  
-   [Seitenansichtsprozess](#_core_the_print_preview_process)  
  
-   [Ändern der Seitenansicht](#_core_modifying_print_preview)  
  
 Seitenansicht entspricht Bildschirmanzeige und Drucken etwas anders, da, anstatt, ein Bild auf einem Gerät direkt zu zeichnen, muss die Anwendung den Drucker mithilfe des Bildschirms simulieren.  Um dies zu berücksichtigen, definiert die Microsoft Foundation Class\-Bibliothek eine spezielle \(nicht dokumentierten\) Klasse, die von [CDC\-Klasse](../mfc/reference/cdc-class.md) abgeleitet wird, aufgerufen **CPreviewDC**.  Alle `CDC`\-Objekte enthalten zwei Gerätekontexte, aber normalerweise sind sie identisch.  In einem **CPreviewDC**\-Objekt sind sie unterschiedlich: das erste stellt den Drucker dar, der simuliert wird, und das zweite wird der Bildschirm dar, in dem Ausgabe tatsächlich angezeigt wird.  
  
##  <a name="_core_the_print_preview_process"></a> Der Seitenansichts\-Prozess  
 Wenn der Benutzer den Seitenansichtsbefehl vom Menü **Datei** auswählen, erstellt das Framework ein **CPreviewDC**\-Objekt.  Sobald die Anwendung einen Vorgang ausführt, die ein Feature des Druckergerätekontexts festgelegt wird, führt das Framework auch ähnliche Vorgang auf dem Bildschirm\-Gerätekontext aus.  Wenn die Anwendung beispielsweise eine Schriftart für den Druck auswählt, wählt das Framework eine Schriftart für Bildschirmanzeige aus, die die Druckerschriftart simuliert.  Sobald die Anwendung Ausgabe dem Drucker senden ist, sendet das Framework stattdessen die Ausgabe auf dem Bildschirm.  
  
 Seitenansicht unterscheidet sich auch aus dem Drucken in der Reihenfolge, diese, die jede die Seiten eines Dokuments.  Während des Drucks platziert das Framework eine Druckschleife fortgesetzt, bis ein bestimmter Seitenbereich gerendert wurde.  Während der Druckvorschau werden eine oder zwei Seiten jederzeit angezeigt, und dann wartet die Anwendung; keine anderen Seiten werden angezeigt, bis der Benutzer reagiert.  Während der Druckvorschau muss die Anwendung `WM_PAINT` auf Meldungen auch, wie es während der normalen Bildschirmanzeige ausführt.  
  
 Die [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)\-Funktion wird aufgerufen, wenn Seitenansicht aufgerufen wird, wie es am Anfang eines Druckauftrags ist.  Die [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md), an die Funktion übergebene Struktur, enthält mehrere Member, deren Werte Sie festlegen können, um bestimmte Eigenschaften des Seitenansichtsvorgangs anzupassen.  Beispielsweise können Sie den **m\_nNumPreviewPages**\-Member festlegen, um anzugeben, ob das Dokument im aus einer Seite vorhandenen oder Umbruchmodus in der Vorschau anzeigen möchten.  
  
##  <a name="_core_modifying_print_preview"></a> Ändern der Seitenansicht  
 Sie können das Verhalten und Aussehen der Druckvorschau auf vielfältige Weise ändern und leicht.  Beispielsweise können Sie, unter anderem:  
  
-   Veranlassen Sie das Seitenansicht, eine Bildlaufleiste für den einfachen Zugriff auf jeder Seite des Dokuments anzuzeigen.  
  
-   Veranlassen Sie Seitenansicht, die Position des Benutzers im Dokument beibehalten, indem Sie seine Anzeige an der aktuellen Seite beginnen.  
  
-   Veranlassen Sie unterschiedliche Initialisierung, für Drucken und Druckvorschau ausgeführt werden.  
  
-   Sie verursachen Seitenansicht zu den Bildseiteseitenzahlen in eigenen Formaten.  
  
 Wenn Sie wissen, wie lange das Dokument `SetMaxPage` mit dem entsprechenden Wert ist und aufruft, kann das Framework diese Informationen im Seitenansicht sowie während des Druckens verwenden.  Nachdem das Framework die Länge des Dokuments kennt, kann es mit dem Vorschaufenster einer Bildlaufleiste bereitgestellt und dem Benutzer ermöglichen, um das Dokument in der Seitenansicht hin und her zu blättern.  Wenn die Länge des Dokuments festgelegt haben, kann das Framework das Bildlauffeld nicht positionieren, um die aktuelle Position anzugeben, sodass fügt das Framework keine Bildlaufleiste hinzu.  In diesem Fall muss der Benutzer die Seite und die Seite\-Schaltflächen Vorherige auf der Steuerleiste des Vorschaufensters verwenden, um das Dokument zu blättern.  
  
 Die Seitenansicht suchen Sie kann es hilfreich sein, einen Wert zuzuweisen dem `m_nCurPage`\-Member von `CPrintInfo`, obwohl Sie nie so für gewöhnlichen Drucken tun.  Während des normalen Drucks trägt dieser Mitglieder Informationen vom Framework an die Ansichtsklasse.  Dies ist, wie das Framework der Ansicht mitteilt, welche Seite gedruckt werden soll.  
  
 Dagegen wenn Seitenansicht gestartet wird, werden der `m_nCurPage` Mitglieder Informationen in die entgegengesetzte Richtung: von der Ansicht zum Framework.  Das Framework verwendet den Wert dieses Members, um festzustellen, welche Seite zuerst in der Vorschau angezeigt werden soll.  Der Standardwert dieses Members ist 1, sodass die erste Seite des Dokuments zuerst angezeigt.  Sie können `OnPreparePrinting` überschreiben, um diesen Member auf die Seitenzahl festzulegen, die angezeigt wird, als der Seitenansichtsbefehl aufgerufen wurde.  Dadurch, die Anwendung verwaltet die aktuelle Position des Benutzers beim Wechseln vom normalen Anzeigemodus zum Seitenansicht bei.  
  
 Gelegentlich werden Sie verschiedene `OnPreparePrinting` abhängig Initialisierung ausführen, ob sie für einen Druckauftrag oder für Seitenansicht aufgerufen wird.  Sie können dies festlegen, indem Sie die **m\_bPreview**\-Membervariable `CPrintInfo` in der Struktur untersuchen.  Dieser Member wird auf **TRUE** festgelegt, wenn Seitenansicht aufgerufen wird.  
  
 Die `CPrintInfo`\-Struktur enthält außerdem einen Member, der **m\_strPageDesc** genannt wird, der verwendet wird, um die Zeichenfolgen zu formatieren, die am unteren Bildschirmrand in den EinzelSeiten\- und MehrfachverbindungsstelleSeitenmodi angezeigt werden.  Standardmäßig sind diese Zeichenfolgen im Formular "Seite *n*" und "Seiten *n* \- *m*", aber Sie können **m\_strPageDesc**`OnPreparePrinting` ändern und die Zeichenfolgen auf durchdachteres einige festlegen.  Siehe [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md) in der *MFC\-Referenz* weitere Informationen.  
  
## Siehe auch  
 [Drucken und Druckvorschau](../mfc/printing-and-print-preview.md)   
 [Drucken](../mfc/printing.md)   
 [CView Class](../mfc/reference/cview-class.md)   
 [CDC\-Klasse](../mfc/reference/cdc-class.md)