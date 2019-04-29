---
title: 'TN040: MFC-OLE direkte Größenanpassung und Zoomen'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: c2cb25388184ac969bec7c01d8077a458c03a03a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305462"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE direkte Größenanpassung und Zoomen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird erläutert, die Probleme im Zusammenhang mit Bearbeitung direktes und wie ein Server sollten richtig Zoomen zu erreichen und direktes Ändern der Größe. Bei der direkten Aktivierung über das WYSIWYG-Konzept einen Schritt weiter in diesem Container ausgeführt, und Server miteinander zusammenarbeiten und insbesondere die OLE-Spezifikation im Wesentlichen die gleiche Weise interpretieren.

Es gibt eine Anzahl von Erwartungen der Endbenutzer, der beibehalten werden soll, aufgrund der schließen-Interaktion zwischen einem Container und Server, der direkten Aktivierung unterstützt:

- Die Präsentation Anzeige (der Metadatei gezeichnet, die der `COleServerItem::OnDraw` außer Kraft setzen) sollte genau gleich aussehen als wenn es gezeichnet wird, für die Bearbeitung (außer, dass Bearbeitungstools nicht angezeigt werden).

- Wenn der Container wird vergrößert, sollten Fenster mit den zu!

- Die Container und Server sollte Objekten zu bearbeiten, verwenden die gleichen Metriken angezeigt werden. Dies bedeutet, dass Sie mithilfe einer basierend auf der Anzahl der Zuordnungsmodus *logische* Pixel pro Zoll – nicht physische Pixel pro Zoll auf dem Anzeigegerät rendern.

> [!NOTE]
>  Da direkte Aktivierung gilt nur für Elemente, die eingebettet sind (nicht verknüpft), gilt die Zoomen nur für eingebettete Objekte. Sehen Sie in beiden APIs `COleServerDoc` und `COleServerItem` , die für das Zoomen verwendet werden. Der Grund für diese Zwiespalt ist, dass nur Funktionen, die für verknüpfte und eingebettete Elemente gültig sind in `COleServerItem` (Dadurch können Sie eine gängige Implementierung haben) und Funktionen, die nur für eingebettete Objekte gültig sind befinden sich in der `COleServerDoc` Klasse (aus der Sicht des Servers, ist es die **Dokument** eingebettet wird).

Die meisten von der Last wird auf dem Server Implementierer selbst, platziert, in an, dass der Server muss kennen Zoomfaktor des Containers und die Bearbeitung Schnittstelle nach Bedarf ändern. Aber wie der Server bestimmt den Zoomfaktor an, dem der Container verwendet wird

## <a name="mfc-support-for-zooming"></a>MFC-Unterstützung für Zoomen

Der aktuelle Zoomfaktor kann bestimmt werden, indem `COleServerDoc::GetZoomFactor`. Dies aufrufen, wenn das Dokument nicht direkt aktiv ist führt immer zu einem Faktor Zoom von 100 % (oder das Verhältnis 1:1). Aufruf von es direkt aktiv möglicherweise einen anderen Wert als 100 % zurückgeben.

Ein Beispiel für Zoomen ordnungsgemäß finden Sie im MFC-OLE-Beispiel [HIERSVR](../overview/visual-cpp-samples.md). HIERSVR vergrößern, wird dadurch erschwert die Tatsache, dass Text angezeigt, und der Text, in der Regel keine Skalierung eine lineare Interpolation (Hinweise, typografische Konventionen, Entwurf Breiten und Höhen alle erschweren die Angelegenheit). Dennoch HIERSVR ist ein angemessener Verweis für die Implementierung korrekt Zoomen und daher ist das MFC-Tutorial [SCRIBBLE](../overview/visual-cpp-samples.md) (Schritt 7).

`COleServerDoc::GetZoomFactor` den Zoomfaktor basierend auf einer Reihe von verschiedenen Metriken verfügbar sind oder aus dem Container als auch von der Implementierung von bestimmt Ihre `COleServerItem` und `COleServerDoc` Klassen. Kurz gesagt, wird der aktuelle Zoomfaktor der folgenden Formel bestimmt:

```
Position Rectangle (PR) / Container Extent (CE)
```

Das POSITIONSRECHTECK richtet sich nach den Container. Es wird an den Server zurückgegeben, während der direkten Aktivierung bei `COleClientItem::OnGetItemPosition` wird aufgerufen, und wird aktualisiert, wenn der Container des Servers aufgerufen `COleServerDoc::OnSetItemRects` (mit einem Aufruf von `COleClientItem::SetItemRects`).

Der CONTAINER-Block ist etwas komplexer zu berechnen. Wenn der Container aufgerufen hat `COleServerItem::OnSetExtent` (mit einem Aufruf von `COleClientItem::SetExtent`), und klicken Sie dann den Umfang der CONTAINER diesen Wert in Pixel, die basierend auf der Anzahl der Pixel pro logischem Zoll () konvertiert wird. Wenn der Container nicht SetExtent (die normalerweise der Fall ist) aufgerufen, der CONTAINER-Block ist die Größe von zurückgegebenen `COleServerItem::OnGetExtent`. Also, wenn der Container nicht SetExtent aufgerufen hat, das Framework setzt voraus, dass wenn dies der Fall der Container es mit 100 % des natürlichen Wertebereichs aufgerufen haben würde (der von zurückgegebene Wert `COleServerItem::GetExtent`). Anders ausgedrückt, das Framework wird davon ausgegangen, dass der Container auf 100 % (nicht mehr und nicht kleiner) des Elements angezeigt wird.

Es ist wichtig, Sie jedoch beachten, dass `COleServerItem::OnSetExtent` und `COleServerItem::OnGetExtent` Namen ähnlich sind, werden sie nicht das gleiche Attribut des Elements ändern. `OnSetExtent` wird aufgerufen, um dem Server wissen, welcher Anteil des Objekts in den Container (unabhängig von der Zoomfaktor) angezeigt wird und `OnGetExtent` wird von der Container kann feststellen der idealen Größe des Objekts aufgerufen.

Durch jede der beteiligten APIs ansehen, können Sie ein klareres Bild abrufen:

## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent

Diese Funktion sollte die "natürliche Size" in HIMETRIC-Einheiten des Elements zurück. Die beste Möglichkeit, "Größe" vorstellen, ist die Definition der Größe, die es den Anschein hat beim Drucken. Die hier zurückgegebene Größe ist konstant für ein bestimmtes Element-Inhalt (ähnlich wie der Metadatei die Konstante für ein bestimmtes Element ist). Diese Größe wird nicht geändert werden, wenn Vergrößern auf das Element angewendet wird. In der Regel ändert sich nicht, wenn der Container dem Element durch Aufrufen von mehr oder weniger Speicherplatz gibt `OnSetExtent`. Ein Beispiel für eine Änderung möglicherweise mit einem einfachen Text-Editor mit keine "Margin"-Funktion, die basierend auf den letzten Block, der den Container per Text umbrochen. Wenn ein Server geändert wird, sollte der Server wahrscheinlich die OLEMISC_RECOMPOSEONRESIZE bit in der systemregistrierung festgelegt (siehe die OLE-SDK-Dokumentation für Weitere Informationen zu dieser Option).

## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent

Diese Funktion wird aufgerufen, wenn der Container "mehr oder weniger" des Objekts anzeigt. Die meisten Container werden nicht dies überhaupt aufrufen. Die Standardimplementierung speichert den letzten Wert empfangen aus dem Container in "M_sizeExtent", die im verwendet wird `COleServerDoc::GetZoomFactor` bei der Berechnung des CONTAINER-Block-Wertes, der oben beschriebenen.

## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects

Diese Funktion wird aufgerufen, nur, wenn das Dokument direkt aktiv ist. Wird aufgerufen, wenn der Container entweder der Position des Elements oder des Clipping angewendet wird, auf das Element aktualisiert. Das POSITIONSRECHTECK bietet wie oben beschrieben den Zähler für die Berechnung der Zoom-Faktor. Ein Server kann anfordern, dass die Position eines Elements geändert werden, durch den Aufruf `COleServerDoc::RequestPositionChange`. Der Container kann, oder kann nicht auf diese Anforderung Antworten, durch den Aufruf `OnSetItemRects` (mit einem Aufruf von `COleServerItem::SetItemRects`).

## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw

Es ist wichtig zu wissen, dass die Metadatei erstellt, durch Überschreiben der `COleServerItem::OnDraw` erzeugt genau die gleiche Metadatei, unabhängig von der aktuellen Zoomfaktor. Der Container wird die Metadatei nach Bedarf skaliert werden. Dies ist ein wichtiger Unterschied zwischen der Ansicht `OnDraw` und dem Serverelement `OnDraw`. Die Ansicht-Handles, Zoomen, das Element erstellt, die nur eine *zoombare* Metadatei und überlässt dem der Container, führen Sie das entsprechende zoomen.

Stellen Sie sicher, dass Ihre Server korrekt verhält sich am einfachsten ist die Verwendung von die Implementierung der `COleServerDoc::GetZoomFactor` Wenn das Dokument direkt aktiv ist.

## <a name="mfc-support-for-in-place-resizing"></a>MFC-Unterstützung für das direkte Ändern der Größe

MFC wird vollständig die direkte Größenänderung-Schnittstelle implementiert, wie in der Spezifikation von OLE 2 beschrieben. Die Benutzeroberfläche wird von unterstützt die `COleResizeBar` -Klasse, eine benutzerdefinierte Meldung WM_SIZECHILD und spezielle Behandlung dieser Nachricht in `COleIPFrameWnd`.

Sie möchten andere Behandlung dieser Nachricht als die vom Framework bereitgestellten implementieren. Wie oben beschrieben, bleibt das Framework die Ergebnisse des direktes Ändern der Größe von bis zu dem Container, der Server antwortet auf die Änderung in der Zoomfaktor. Wenn der Container durch Festlegen der beiden reagiert CONTAINER Umfang und POSITIONSRECHTECK während der Verarbeitung der seine `COleClientItem::OnChangeItemPosition` (aufgerufen aufgrund eines Aufrufs von `COleServerDoc::RequestPositionChange`) und Ändern der Größe des direktes dazu führt, "mehr oder weniger" des Elements in der Bearbeitung angezeigt Fenster. Wenn der Container reagiert, indem Sie die während der Verarbeitung der POSITIONSRECHTECK festlegen `COleClientItem::OnChangeItemPosition`der Zoomfaktor wird geändert, und das Element "vergrößert herunter- oder hochskalieren." angezeigt

Ein Server kann (zu einem gewissen Grad) steuern, was geschieht, während der Verhandlung. Eine Tabelle z. B., möchten möglicherweise mehr oder weniger Zellen angezeigt, wenn der Benutzer die Fenstergröße wird während der Bearbeitung des Elements für ein direktes. Ein Word, möchten möglicherweise ändern Sie die "Seitenränder" sind identisch mit dem Fenster und Umbrechen von Text bis zum neuen Rand. Server, implementieren Sie dies durch Ändern der natürlichen Block (zurückgegebene Größe von `COleServerItem::OnGetExtent`) bei der Größenänderung erfolgt. Dadurch werden sowohl das POSITIONSRECHTECK als auch den Umfang der CONTAINER im selben Umfang, was in der gleichen Zoomfaktor, aber eine größere oder kleinere Anzeigebereich ändern. Darüber hinaus, mehr oder weniger des Dokuments werden angezeigt, in der Metadatei vom `OnDraw`. In diesem Fall wird das Dokument selbst ändern, wenn der Benutzer das Element, anstatt nur den Anzeigebereich Größe ändert.

Können Sie benutzerdefinierte Größe zu implementieren und die Benutzeroberfläche weiterhin nutzen `COleResizeBar` durch Überschreiben der WM_SIZECHILD-Nachricht in Ihrem `COleIPFrameWnd` Klasse. Weitere Informationen zu den Besonderheiten der WM_SIZECHILD, finden Sie unter [technischen Hinweis 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
