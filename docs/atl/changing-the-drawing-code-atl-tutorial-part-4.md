---
title: Ändern des Zeichencodes (ATL-Lernprogramm, Teil 4) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fed83cd67ff596581440fa317355186653a0cbec
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760424"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Ändern des Zeichencodes (ATL-Lernprogramm, Teil 4)

Standardmäßig zeigt Code zum Zeichnen des Steuerelements ein Quadrat und den Text **PolyCtl**. In diesem Schritt ändern Sie den Code, um etwas interessanteres anzuzeigen. Die folgenden Aufgaben sind beteiligt:

- Ändern die Header-Datei

- Ändern der `OnDraw` Funktion

- Hinzufügen einer Methode, um die Punkte des Polygons zu berechnen.

- Initialisieren der Füllfarbe

## <a name="modifying-the-header-file"></a>Ändern die Header-Datei

Starten Sie durch Hinzufügen von Unterstützung für die mathematischen Funktionen `sin` und `cos`, die Polygonpunkte berechnet und durch Erstellen eines Arrays zum Speichern von positioniert das verwendet wird.

#### <a name="to-modify-the-header-file"></a>So ändern Sie die Header-Datei

1. Fügen Sie die Zeile `#include <math.h>` an den Anfang PolyCtl.h hinzu. Am Anfang der Datei sollte folgendermaßen aussehen:

     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

2. Sobald die Polygonpunkte berechnet werden, werden sie in ein Array vom Typ gespeichert `POINT`, fügen Sie das Array daher nach der Definition der `m_nSides` in PolyCtl.h hinzu:

     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>Ändern die OnDraw-Methode

Nachdem Sie ändern, sollten die `OnDraw` -Methode in PolyCtl.h hinzu. Sie fügen Code erstellt einen neuen Stift und der Pinsel, mit dem Sie das Polygon zeichnen, und ruft dann die `Ellipse` und `Polygon` Win32-API-Funktionen zum eigentlichen Zeichenvorgang ausführen.

#### <a name="to-modify-the-ondraw-function"></a>So ändern Sie die OnDraw-Funktion

1. Ersetzen Sie die vorhandene `OnDraw` Methode in PolyCtl.h hinzu, durch den folgenden Code:

     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Hinzufügen einer Methode, um die Punkte des Polygons zu berechnen.

Fügen Sie eine Methode namens `CalcPoints`, die die Koordinaten der Punkte, aus denen der Umfang des Polygons berechnet. Diese Berechnungen werden auf die RECT-Variable basieren, die an die Funktion übergeben wird.

#### <a name="to-add-the-calcpoints-method"></a>Zum Hinzufügen der CalcPoints-Methode

1. Fügen Sie die Deklaration der `CalcPoints` auf die `IPolyCtl` öffentlichen Abschnitt der der `CPolyCtl` Klasse in PolyCtl.h hinzu:

     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

     Der letzte Teil der öffentliche Teil der `CPolyCtl` Klasse sieht wie folgt:

     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

2. Fügen Sie diese Implementierung von der `CalcPoints` Funktion am Ende der PolyCtl.cpp:

     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>Initialisieren der Füllfarbe

Initialisieren Sie `m_clrFillColor` mit einer Standardfarbe.

#### <a name="to-initialize-the-fill-color"></a>Die Füllfarbe initialisiert werden.

1. Verwenden von Grün als die Standardfarben durch Hinzufügen dieser Zeile zum die `CPolyCtl` Konstruktor in PolyCtl.h hinzu:

     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

Der Konstruktor sieht nun folgendermaßen aus:

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Erstellen Sie das Steuerelement neu. Stellen Sie sicher, dass die Datei "PolyCtl.htm" wird geschlossen, wenn es immer noch geöffnet, und klicken Sie dann auf **Polygon erstellen** auf die **erstellen** Menü. Sie können das Steuerelement erneut von der Seite "PolyCtl.htm" anzeigen, aber dieses Mal verwenden, den Testcontainer für ActiveX-Steuerelemente.

#### <a name="to-use-the-activex-control-test-container"></a>Verwenden Sie den Testcontainer für ActiveX-Steuerelemente

1. Erstellen Sie und starten Sie den Testcontainer für ActiveX-Steuerelemente. Weitere Informationen finden Sie unter [TSTCON-Beispiel: ActiveX-Steuerelementtestcontainer](../visual-cpp-samples.md).

2. Im Test-Container auf die **bearbeiten** Menü klicken Sie auf **neues Steuerelement einfügen**.

3. Suchen Sie das Steuerelement, die aufgerufen wird, `PolyCtl Class`, und klicken Sie auf **OK**. Es wird ein grünes Dreieck innerhalb eines Kreises angezeigt.

Versuchen Sie die Anzahl der Seiten nach dem nächsten Verfahren ändern. Verwenden Sie zum Ändern der Eigenschaften für eine duale Schnittstelle von innerhalb des Testcontainers **Methoden aufrufen**.

#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>So ändern Sie die Eigenschaft eines Steuerelements aus im Test-Container

1. Klicken Sie im Test-Container, auf **Methoden aufrufen** auf die **Steuerelement** Menü.

     Die **Aufrufmethode** Dialogfeld wird angezeigt.

2. Wählen Sie die **PropPut** Version der **Seiten** Eigenschaft aus der **Methodenname** im Dropdown Listenfeld.

3. Typ `5` in die **Parameterwert** auf **Wert festlegen**, und klicken Sie auf **Invoke**.

Beachten Sie, dass das Steuerelement nicht ändert. Obwohl Sie die Anzahl der Seiten intern durch die Einstellung geändert der `m_nSides` Variablen, Dies führte nicht zu dem Steuerelement neu zu zeichnen. Wenn Sie zu einer anderen Anwendung wechseln und wieder in den Testcontainer finden Sie, dass das Steuerelement neu gezeichnet hat und die richtige Anzahl von Seiten.

Um dieses Problem zu beheben, fügen Sie einen Aufruf der `FireViewChange` in definierte Funktion `IViewObjectExImpl`, nachdem Sie die Anzahl der Seiten festlegen. Wenn das Steuerelement, in einem eigenen Fenster ausgeführt wird, `FireViewChange` Ruft die `InvalidateRect` -Methode direkt. Wenn das Steuerelement fensterlose, läuft die `InvalidateRect` Methode wird für den Container-Standort-Schnittstelle aufgerufen werden. Dies erzwingt, dass das Steuerelement selbst neu zeichnet.

#### <a name="to-add-a-call-to-fireviewchange"></a>Einen Aufruf FireViewChange hinzufügen

1. Aktualisieren Sie PolyCtl.cpp durch Hinzufügen des Aufrufs von `FireViewChange` auf die `put_Sides` Methode. Wenn Sie fertig sind, die `put_Sides` Methode sollte wie folgt aussehen:

     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

Nach dem Hinzufügen `FireViewChange`, neu zu erstellen und Testen Sie das Steuerelement erneut in den Testcontainer für ActiveX-Steuerelemente. Dieses Mal, wenn Sie die Anzahl der Seiten ändern, und klicken Sie auf `Invoke`, sollte das Steuerelement sofort zu ändern.

Im nächsten Schritt fügen Sie ein Ereignis.

[Zurück zu Schritt 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [mit Schritt 5 fort](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)   
[Testen der Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md)

