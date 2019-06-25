---
title: Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)
ms.custom: get-started-article
ms.date: 05/06/2019
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
ms.openlocfilehash: db6dcc57ff9f3748d802e76617ef18dea8f9506c
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344358"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)

Das Steuerelement ist jetzt fertig. Um zu sehen, wie das Steuerelement in einer realen Situation funktioniert, platzieren Sie es auf einer Webseite. Eine HTML-Datei, die das Steuerelement enthält, wurde erstellt, als Sie das Steuerelement definiert haben. Öffnen Sie die Datei PolyCtl.htm **Projektmappen-Explorer**, und sehen Sie das Steuerelement auf einer Webseite.

In diesem Schritt müssen Sie das Steuerelement Funktionen hinzugefügt und Skripterstellung für die Webseite, um auf Ereignisse reagieren. Außerdem ändern Sie das Steuerelement, um Internet Explorer zu wissen, dass das Steuerelement für die Skripterstellung sicher ist.

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

Das Steuerelement nicht etwas noch so ändern Sie die Webseite, um auf die Ereignisse zu reagieren, die Sie senden.

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

Sie haben einigen VBScript-Code hinzugefügt, der die Seiteneigenschaft vom Steuerelement abruft. Es erhöht die Anzahl der Seiten um 1, wenn Sie innerhalb des Steuerelements klicken. Wenn Sie außerhalb des Steuerelements klicken, reduzieren Sie die Anzahl der Seiten um eine.

## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Angeben, dass das Steuerelement für die Skripterstellung sicher ist

Sie können die Webseite mit dem Steuerelement nur in Internet Explorer anzeigen. Andere Browser unterstützen ActiveX-Steuerelemente nicht mehr aufgrund von Sicherheitslücken.

> [!NOTE]
> Wenn das Steuerelement nicht sichtbar ist, wissen Sie, dass es sich bei einigen Browsern Einstellungen Anpassungen ActiveX-Steuerelemente ausführen müssen. Lesen Sie im Browser auf die Dokumentation zum Aktivieren von ActiveX-Steuerelemente.

Basierend auf Ihrer aktuellen Internet Explorer-Sicherheitseinstellungen, erhalten Sie möglicherweise ein Dialogfeld "Sicherheitswarnung". Es gibt an, dass das Steuerelement möglicherweise nicht sicher für die skriptausführung und möglicherweise Schaden. Wenn Sie beispielsweise ein Steuerelement hätten, das eine Datei anzeigen würde, aber auch eine `Delete`-Methode hätte, die eine Datei löscht, wäre es sicher, wenn es nur auf der Seite angezeigt würde. Es wäre aber nicht sicher für die Skriptausführung, denn jemand könnte die `Delete`-Methode aufrufen.

> [!IMPORTANT]
> Für dieses Lernprogramm können Sie die Sicherheitseinstellungen in Internet Explorer ändern, um ActiveX-Steuerelemente auszuführen, die nicht als sicher gekennzeichnet sind. Klicken Sie in der Systemsteuerung auf **Interneteigenschaften** , und klicken Sie auf **Sicherheit** so ändern Sie die entsprechenden Einstellungen. Wenn Sie das Lernprogramm abgeschlossen haben, ändern Sie die Sicherheitseinstellungen zurück zu ihrem ursprünglichen Zustand.

Sie können programmgesteuert Internet Explorer benachrichtigen, dass es nicht benötigt, um das Dialogfeld "Sicherheitswarnung" für dieses spezielle Steuerelement anzuzeigen. Sie können dafür mithilfe der `IObjectSafety` Schnittstelle. ATL stellt eine Implementierung dieser Schnittstelle in der Klasse [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Um die Schnittstelle zu Ihrem Steuerelement hinzuzufügen, fügen `IObjectSafetyImpl` zur Liste der geerbten Klassen, und fügen Sie einen Eintrag für die sie in der COM-Zuordnung.

### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>So fügen Sie IObjectSafetyImpl dem Steuerelement hinzu

1. Fügen Sie die folgende Zeile dem Ende der Liste geerbter Klassen in PolyCtl.h hinzu, und fügen Sie der vorherigen Zeile ein Komma hinzu:

    [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]

1. Fügen Sie die folgende Zeile der COM-Zuordnung in PolyCtl.h hinzu:

    [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]

## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements

Erstellen Sie das Steuerelement. Sobald der Buildvorgang abgeschlossen ist, öffnen Sie wieder PolyCtl.htm in der Browseransicht. Dieses Mal die Webseite angezeigt werden soll direkt ohne die **Sicherheitswarnungs** Dialogfeld. Wenn Sie innerhalb des Polygons klicken, wird die Anzahl der Seiten um eins erhöht. Klicken Sie außerhalb des Polygons, um die Anzahl der Seiten zu verringern.

[Zurück zu Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)

## <a name="next-steps"></a>Nächste Schritte

Dieser Schritt ist das ATL-Lernprogramm abgeschlossen. Links zu weiteren Informationen über ATL finden Sie die [ATL-Startseite](../atl/active-template-library-atl-concepts.md).

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
