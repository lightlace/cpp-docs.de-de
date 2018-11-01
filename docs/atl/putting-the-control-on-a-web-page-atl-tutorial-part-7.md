---
title: Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: 77d608fddfc63862c81ce7c7d259510fb4784910
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659199"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)

Das Steuerelement ist jetzt fertig. Um zu sehen, wie das Steuerelement in einer realen Situation funktioniert, platzieren Sie es auf einer Webseite. Eine HTML-Datei, die das Steuerelement enthält, wurde erstellt, als Sie das Steuerelement definiert haben. Öffnen Sie die Datei PolyCtl.htm **Projektmappen-Explorer**, und sehen Sie das Steuerelement auf einer Webseite.

In diesem Schritt haben Sie das Steuerelement Funktionen hinzugefügt und Skripterstellung für die Webseite, um auf Ereignisse reagieren. Außerdem ändern Sie das Steuerelement, um Internet Explorer zu informieren, dass das Steuerelement für die Skripterstellung sicher ist.

## <a name="adding-new-functionality"></a>Das Hinzufügen neuer Funktionen

### <a name="to-add-control-features"></a>Hinzufügen von Funktionen

1. Öffnen Sie PolyCtl.cpp, und Ersetzen Sie den folgenden Code:

    ```cpp
    if (PtInRegion(hRgn, xPos, yPos))
        Fire_ClickIn(xPos, yPos);
    else
        Fire_ClickOut(xPos, yPos);
    ```

    durch

    ```cpp
    short temp = m_nSides;
    if (PtInRegion(hRgn, xPos, yPos))
    {
        Fire_ClickIn(xPos, yPos);
        put_Sides(++temp);
    }
    else
    {
        Fire_ClickOut(xPos, yPos);
        put_Sides(--temp);
    }
    ```

Die Form wird jetzt hinzufügen oder Entfernen von Seiten, je nachdem, wo Sie klicken.

## <a name="scripting-the-web-page"></a>Skripterstellung für die Webseite

Das Steuerelement ist noch nicht aktiv. Ändern Sie die Website, sodass sie auf die Ereignisse reagiert, die Sie senden.

### <a name="to-script-the-web-page"></a>Zur Skripterstellung für die Webseite

1. Öffnen Sie PolyCtl.htm und wählen Sie die HTML-Ansicht aus. Fügen Sie dem HTML-Code die folgenden Zeilen hinzu. Sie sollten nach `</OBJECT>` und vor `</BODY>` hinzugefügt werden.

    ```html
    <SCRIPT LANGUAGE="VBScript">
    <!--
        Sub PolyCtl_ClickIn(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - adding side")
        End Sub
        Sub PolyCtl_ClickOut(x, y)
            MsgBox("Clicked (" & x & ", " & y & ") - removing side")
        End Sub
    -->
    </SCRIPT>
    ```

1. Speichern Sie die HTM-Datei.

Sie haben einigen VBScript-Code hinzugefügt, der die Seiteneigenschaft vom Steuerelement abruft und die Anzahl der Seiten um eins erhöht, wenn Sie innerhalb des Steuerelements klicken. Wenn Sie außerhalb des Steuerelements klicken, reduzieren Sie die Anzahl der Seiten um eine.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Angeben, dass das Steuerelement für die Skripterstellung sicher ist

Sie können die Webseite mit dem Steuerelement in Internet Explorer anzeigen. Noch benutzerfreundlicher ist es aber, die in Visual C++ integrierte Webbrowseransicht zu verwenden. Um das Steuerelement in der Webbrowseransicht anzuzeigen, mit der rechten Maustaste PolyCtl.htm, und klicken Sie auf **in Browser anzeigen**.

> [!NOTE]
> Wenn das Steuerelement nicht sichtbar ist, wissen Sie, dass es sich bei einigen Browsern Einstellungen Anpassungen ActiveX-Steuerelemente ausführen müssen. Finden Sie im Browser auf die Dokumentation zum Aktivieren von ActiveX-Steuerelemente.

Auf Grundlage der aktuellen Internet Explorer-Sicherheitseinstellungen erhalten Sie möglicherweise ein Dialogfeld mit einer Sicherheitswarnung, die besagt, dass das Steuerelement möglicherweise nicht sicher für die Skriptausführung ist und möglicherweise Schaden anrichten kann. Wenn Sie beispielsweise ein Steuerelement hätten, das eine Datei anzeigen würde, aber auch eine `Delete`-Methode hätte, die eine Datei löscht, wäre es sicher, wenn es nur auf der Seite angezeigt würde. Es wäre aber nicht sicher für die Skriptausführung, denn jemand könnte die `Delete`-Methode aufrufen.

> [!IMPORTANT]
> Für dieses Lernprogramm können Sie die Sicherheitseinstellungen in Internet Explorer ändern, um ActiveX-Steuerelemente auszuführen, die nicht als sicher gekennzeichnet sind. Klicken Sie in der Systemsteuerung auf **Interneteigenschaften** , und klicken Sie auf **Sicherheit** so ändern Sie die entsprechenden Einstellungen. Wenn Sie das Lernprogramm abgeschlossen haben, ändern Sie die Sicherheitseinstellungen zurück zu ihrem ursprünglichen Zustand.

Sie können programmgesteuert Internet Explorer benachrichtigen, dass für dieses spezielle Steuerelement kein Sicherheitswarnungs-Dialogfeld angezeigt werden muss. Hierzu können Sie mit der `IObjectSafety` -Schnittstelle und ATL stellt eine Implementierung dieser Schnittstelle in der Klasse [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Um die Schnittstelle Ihrem Steuerelement hinzuzufügen, fügen Sie `IObjectSafetyImpl` der Liste der geerbten Klassen hinzu, und fügen Sie dafür einen Eintrag in der COM-Zuordnung hinzu.

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>So fügen Sie IObjectSafetyImpl dem Steuerelement hinzu

1. Fügen Sie die folgende Zeile dem Ende der Liste geerbter Klassen in PolyCtl.h hinzu, und fügen Sie der vorherigen Zeile ein Komma hinzu:

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. Fügen Sie die folgende Zeile der COM-Zuordnung in PolyCtl.h hinzu:

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Erstellen Sie das Steuerelement. Sobald der Buildvorgang abgeschlossen ist, öffnen Sie wieder PolyCtl.htm in der Browseransicht. Dieses Mal die Webseite angezeigt werden soll direkt ohne die **Sicherheitswarnungs** Dialogfeld. Klicken Sie innerhalb des Polygons; die Anzahl der Seiten wird um eins erhöht. Klicken Sie außerhalb des Polygons, um die Anzahl der Seiten zu verringern.

[Zurück zu Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Nächste Schritte

Damit ist das ATL-Lernprogramm beendet. Links zu weiteren Informationen über ATL finden Sie die [ATL-Startseite](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
