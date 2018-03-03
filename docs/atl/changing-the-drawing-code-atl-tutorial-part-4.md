---
title: "Ändern des Zeichencodes (ATL-Lernprogramm, Teil 4) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ccbf7dab7d39a80efa2b0b0b88b615c55cd9e56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Ändern des Zeichencodes (ATL-Lernprogramm, Teil 4)
Standardmäßig zeigt Code zum Zeichnen des Steuerelements ein Quadrat und den Text **PolyCtl**. In diesem Schritt ändern Sie den Code, um etwas interessanteres anzuzeigen. Die folgenden Aufgaben sind beteiligt:  
  
-   Ändern die Headerdatei  
  
-   Ändern der `OnDraw` Funktion  
  
-   Hinzufügen einer Methode, um die Polygonpunkten zu berechnen.  
  
-   Initialisieren der Füllfarbe  
  
## <a name="modifying-the-header-file"></a>Ändern die Headerdatei  
 Starten Sie durch Hinzufügen der Unterstützung für die mathematischen Funktionen `sin` und `cos`, die verwendet werden, wird die polygonpunkten berechnen und durch Erstellen eines Arrays zum Speichern von positioniert.  
  
#### <a name="to-modify-the-header-file"></a>So ändern Sie die Headerdatei  
  
1.  Fügen Sie die Zeile `#include <math.h>` an den Anfang PolyCtl.h hinzu. Am Anfang der Datei sollte wie folgt aussehen:  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  Sobald die Polygonpunkte berechnet werden, werden sie in ein Array vom Typ gespeichert werden `POINT`, fügen Sie das Array daher hinzu, nach der Definition von `m_nSides` in PolyCtl.h hinzu:  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## <a name="modifying-the-ondraw-method"></a>Ändern die OnDraw-Methode  
 Jetzt geändert werden sollte die `OnDraw` Methode in PolyCtl.h hinzu. Sie fügen Code erstellt eine neue Stift und Pinsel mit der das Polygon gezeichnet werden soll, und ruft dann die `Ellipse` und `Polygon` Win32-API-Funktionen, um die tatsächliche Zeichnung zu erstellen.  
  
#### <a name="to-modify-the-ondraw-function"></a>So ändern Sie die OnDraw-Funktion  
  
1.  Ersetzen Sie die vorhandene `OnDraw` Methode in PolyCtl.h hinzu, durch den folgenden Code:  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Hinzufügen einer Methode, um die Polygonpunkten zu berechnen.  
 Hinzufügen eine Methode mit dem Namen `CalcPoints`, berechnet, die die Koordinaten der Punkte, die dem Umkreis des Polygons bilden. Diese Berechnungen basiert auf die RECT-Variable, die an die Funktion übergeben wird.  
  
#### <a name="to-add-the-calcpoints-method"></a>So fügen Sie die CalcPoints-Methode hinzu  
  
1.  Fügen Sie der Deklaration des `CalcPoints` auf die `IPolyCtl` öffentlichen Abschnitt der der `CPolyCtl` Klasse in PolyCtl.h hinzu:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     Der letzte Teil des öffentlichen Abschnitt der `CPolyCtl` Klasse wird wie folgt aussehen:  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  Fügen Sie diese Implementierung der `CalcPoints` Funktion an das Ende des PolyCtl.cpp:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## <a name="initializing-the-fill-color"></a>Initialisieren der Füllfarbe  
 Initialisieren `m_clrFillColor` mit einer Standardfarbe.  
  
#### <a name="to-initialize-the-fill-color"></a>Um die Füllfarbe zu initialisieren.  
  
1.  Verwenden von Grün als Standardfarbe durch Hinzufügen dieser Zeile den `CPolyCtl` Konstruktor in PolyCtl.h hinzu:  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 Der Konstruktor sieht nun wie folgt:  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements  
 Erstellen Sie das Steuerelement neu. Stellen Sie sicher, dass die Datei "PolyCtl.htm" wird geschlossen, wenn es noch geöffnet ist, und klicken Sie dann auf **Polygon erstellen** auf die **erstellen** Menü. Sie können das Steuerelement erneut von der Seite "PolyCtl.htm" anzeigen, aber verwenden Sie dieses Mal den Testcontainer für ActiveX-Steuerelemente.  
  
#### <a name="to-use-the-activex-control-test-container"></a>Verwenden Sie den Testcontainer für ActiveX-Steuerelemente  
  
1.  Erstellen Sie und starten Sie den Testcontainer für ActiveX-Steuerelemente. Weitere Informationen finden Sie unter [TSTCON-Beispiel: Testcontainer für ActiveX-Steuerelement](../visual-cpp-samples.md).  
  
2.  Im Test-Container auf die **bearbeiten** Menü klicken Sie auf **neues Steuerelement einfügen**.  
  
3.  Suchen Sie das Steuerelement, der den Namen `PolyCtl Class`, und klicken Sie auf **OK**. Es wird ein grünes Dreieck innerhalb eines Kreises angezeigt.  
  
 Versuchen Sie die Anzahl der Seiten mithilfe des folgenden Verfahrens weiter ändern. Verwenden Sie zum Bearbeiten von Eigenschaften für eine duale Schnittstelle innerhalb des Testcontainers **Methoden aufrufen**.  
  
#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>So ändern Sie die Eigenschaft eines Steuerelements aus innerhalb der Testcontainer  
  
1.  Klicken Sie im Test-Container auf **Methoden aufrufen** auf die **Steuerelement** Menü.  
  
     Die **Aufrufmethode** Dialogfeld wird angezeigt.  
  
2.  Wählen Sie die **PropPut** Version der **Seiten** Eigenschaft aus der **Methodennamen** im Dropdown Listenfeld.  
  
3.  Typ `5` in der **Parameterwert** auf **Wert festlegen**, und klicken Sie auf **Invoke**.  
  
 Beachten Sie, dass das Steuerelement nicht ändert. Obwohl Sie die Anzahl der Seiten intern durch die Einstellung geändert die `m_nSides` Variable, dies nicht dazu, dass das Steuerelement neu gezeichnet werden. Wenn Sie auf eine andere Anwendung wechseln, und wechseln Sie zurück zum Testcontainer, werden Sie feststellen, dass das Steuerelement neu gezeichnet wurde, und verfügt über die richtige Anzahl von Seiten.  
  
 Um dieses Problem zu beheben, fügen Sie einen Aufruf der `FireViewChange` in definierte Funktion `IViewObjectExImpl`, nachdem Sie die Anzahl der Seiten festgelegt. Wenn das Steuerelement, in einem eigenen Fenster ausgeführt wird `FireViewChange` aufrufen, wird die `InvalidateRect` -Methode direkt. Wenn das Steuerelement fensterlose, läuft die `InvalidateRect` -Methode wird die Containerschnittstelle Website aufgerufen werden. Dies erzwingt, dass das Steuerelement selbst neu zeichnet.  
  
#### <a name="to-add-a-call-to-fireviewchange"></a>So fügen Sie einen Aufruf von FireViewChange hinzu  
  
1.  Aktualisieren Sie PolyCtl.cpp durch Hinzufügen des Aufrufs von `FireViewChange` auf die `put_Sides` Methode. Wenn Sie fertig sind, die `put_Sides` Methode sollte wie folgt aussehen:  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 Nach dem Hinzufügen der `FireViewChange`, neu erstellen, und wiederholen Sie dann das Steuerelement erneut in den Testcontainer für ActiveX-Steuerelemente. Dieses Mal, wenn Sie die Anzahl der Seiten ändern, und klicken Sie auf `Invoke`, sehen Sie das Steuerelement, das unmittelbar geändert werden.  
  
 Im nächsten Schritt fügen Sie ein Ereignis.  
  
 [Zurück zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [Mit Schritt 5 fort](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)   
 [Testen der Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md)

