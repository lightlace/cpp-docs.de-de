---
title: "&#196;ndern des Zeichencodes (ATL-Lernprogramm, Teil 4) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT-Makro"
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# &#196;ndern des Zeichencodes (ATL-Lernprogramm, Teil 4)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig zeigt der Zeichencode des Steuerelements ein Quadrat und den Text **PolyCtl** an.  In diesem Schritt ändern Sie den Code, um interessanteres einige anzuzeigen.  Die folgenden Aufgaben werden beteiligt:  
  
-   Ändern der Headerdatei  
  
-   Ändern der `OnDraw`\-Funktion  
  
-   Hinzufügen einer Methode, um die Polygon\-Punkte zu berechnen  
  
-   Initialisieren der Füllfarbe  
  
## Ändern der Headerdatei  
 Beginnen Sie, indem Sie Unterstützung für die mathematischen Funktionen `sin` und `cos` hinzufügen, die leiten die Polygonpunkte verwendet werden und mit einem Array erstellt, um Positionen zu speichern.  
  
#### Um die Headerdatei ändern  
  
1.  Fügen Sie die Zeile `#include <math.h>` am Anfang von PolyCtl.h hinzu.  Die Anfang der Datei sollte wie folgt aussehen:  
  
     [!CODE [NVC_ATL_Windowing#47](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#47)]  
  
2.  Sobald die Polygonpunkte abgeleitet, werden sie in einem Array vom Typ `POINT` gespeichert, sodass fügen Sie das Array nach der Definition von `m_nSides` in PolyCtl.h hinzu:  
  
     [!CODE [NVC_ATL_Windowing#48](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#48)]  
  
## Ändern der OnDraw\-Methode  
 Jetzt können Sie die `OnDraw`\-Methode in PolyCtl.h ändern.  Der Code, den Sie hinzufügen, erstellt einen neuen Stift und einen Pinsel erstellt, mit denen, das Polygon zu zeichnen und dann die `Ellipse` und `Polygon` Win32\-API\-Funktionen aufruft, um die tatsächliche Zeichnen auszuführen.  
  
#### Um die OnDraw\-Funktion ändern  
  
1.  Ersetzen Sie die vorhandene `OnDraw`\-Methode in PolyCtl.h durch folgenden Code:  
  
     [!CODE [NVC_ATL_Windowing#49](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#49)]  
  
## Hinzufügen einer Methode, um die Polygon\-Punkte zu berechnen  
 Fügen Sie eine Methode hinzu, `CalcPoints` aufgerufen, das die Koordinaten der Punkte berechnet, die den Umfang des Polygons bilden.  Diese Berechnungen basieren auf der RECT\-Variable, die an die Funktion übergeben wird.  
  
#### Um die CalcPoints\-Methode hinzufügen  
  
1.  Fügen Sie die Deklaration von `CalcPoints` dem öffentlichen Abschnitt der `IPolyCtl``CPolyCtl`\-Klasse in PolyCtl.h hinzu:  
  
     [!CODE [NVC_ATL_Windowing#50](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#50)]  
  
     Der letzte Teil des öffentlichen Abschnitt der `CPolyCtl`\-Klasse sieht wie folgt aus:  
  
     [!CODE [NVC_ATL_Windowing#51](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#51)]  
  
2.  Fügen Sie diese Implementierung der Funktion `CalcPoints` Ende von PolyCtl.cpp hinzu:  
  
     [!CODE [NVC_ATL_Windowing#52](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#52)]  
  
## Initialisieren der Füllfarbe  
 Initialisieren Sie `m_clrFillColor` mit einer Standardfarbe.  
  
#### Um die Füllfarbe initialisieren  
  
1.  Verwenden Sie grün, wie die Standardfarbe durch Hinzufügen dieser Zeile zum `CPolyCtl`\-Konstruktor in PolyCtl.h:  
  
     [!CODE [NVC_ATL_Windowing#53](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#53)]  
  
 Der Konstruktor sieht nun wie folgt aus:  
  
 [!CODE [NVC_ATL_Windowing#54](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#54)]  
  
## Erstellen und Testen des Steuerelements  
 Erstellen Sie das Steuerelement neu.  Stellen Sie sicher, dass die Datei PolyCtl.htm\- wird geschlossen, wenn sie immer noch geöffnet, und dann auf **Polygon erstellen** auf dem Menü **Erstellen** geklickt hat.  Sie können das Steuerelement von der Seite PolyCtl.htm\-, aber diese malverwendung noch einmal anzeigen der Testcontainer für ActiveX\-Steuerelemente.  
  
#### Um den Testcontainer für ActiveX\-Steuerelemente verwenden  
  
1.  Erstellen Sie den Testcontainer für ActiveX\-Steuerelemente an.  Weitere Informationen finden Sie unter [TSTCON\-Beispiel: Testcontainer für ActiveX\-Steuerelemente](../top/visual-cpp-samples.md).  
  
2.  im Testcontainer auf dem Menü **Bearbeiten**, auf **Neues Steuerelement einfügen**.  
  
3.  Suchen Sie das Steuerelement, das `PolyCtl Class` aufgerufen wird, und klicken Sie auf **OK**.  Sie finden ein grünes Dreieck innerhalb eines Kreises.  
  
 Versuchen Sie, die Anzahl vonseiten zu ändern, indem Sie die folgende Prozedur befolgen.  Um Eigenschaften auf einer dualen Schnittstelle aus Testcontainer zu ändern, verwenden Sie **Invoke Methods**.  
  
#### Um die Eigenschaft eines Steuerelements aus dem Testcontainer ändern  
  
1.  im Testcontainer klicken Sie auf **Methoden aufrufen** auf dem Menü **System**.  
  
     Das Dialogfeld wird angezeigt. **Methode aufrufen**  
  
2.  Wählen Sie die **PropPut**\-Version der **Sides**\-Eigenschaft vom **Methodenname** Dropdown\-Listenfeld aus.  
  
3.  Typ `5`**Parameterwert** im Feld auf, und klicken Sie auf **Wert festgelegtAufrufen**.  
  
 Beachten Sie, dass das Steuerelement nicht ändert.  Obwohl Sie die Anzahl vonseiten intern ändern, indem Sie die `m_nSides`\-Variable festlegen, dass diese nicht das Steuerelement neu zu zeichnen.  Wenn Sie zu einer anderen Anwendung wechseln und zurück in Testcontainer wechseln, werden Sie feststellen, dass das Steuerelement die richtige Anzahl vonseiten neu gestrichelt und hat verfügt.  
  
 Um dieses Problem zu beheben, fügen Sie einen Aufruf der Funktion definiert `FireViewChange` hinzu, in `IViewObjectExImpl`, nach dem Festlegen der Anzahl vonseiten.  Wenn das Steuerelement in ein eigenes Fenster ausgeführt wird, ruft die Methode `FireViewChange``InvalidateRect` direkt auf.  Wenn das Steuerelement das Ausführen fensterlos ist, wird die `InvalidateRect`\-Methode um der Siteschnittstelle des Containers aufgerufen.  Dadurch wird das Steuerelement, sich neu zu zeichnen.  
  
#### So fügen Sie einen Aufruf FireViewChange hinzufügen  
  
1.  Aktualisieren Sie PolyCtl.cpp, indem Sie den Aufruf in `FireViewChange` zur `put_Sides`\-Methode hinzufügen.  Wenn Sie damit fertig sind, sollte die `put_Sides`\-Methode wie folgt aussehen:  
  
     [!CODE [NVC_ATL_Windowing#55](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#55)]  
  
 Nach dem `FireViewChange` hinzugefügt hat, versuchen Neukompilierungen und das Steuerelement noch einmal im Testcontainer für ActiveX\-Steuerelemente.  Dieses Mal, wenn Sie die Anzahl vonseiten ändern und auf `Invoke` klicken, sollten Sie die kann sofort anzeigen.  
  
 Im nächsten Schritt fügen Sie ein Ereignis hinzu.  
  
 [Zurück zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [Klicken Sie zu Schritt 5](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)   
 [Testen der Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md)