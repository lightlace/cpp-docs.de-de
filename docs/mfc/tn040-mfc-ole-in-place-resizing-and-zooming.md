---
title: 'TN040: MFC-OLE direkte Größenanpassung und Zoomen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dbd817e6bcb9c7ff526bef98bd5c2c8c1f1bb3e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955169"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE direkte Größenanpassung und Zoomen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird erläutert, die Probleme im Zusammenhang mit bearbeiten direkte und wie ein Server sollte richtig vergrößern/verkleinern erreichen und direktes Ändern der Größe. Bei der direkten Aktivierung über das WYSIWYG-Konzept geschaltet einen Schritt weiter in diesem Container und Server miteinander kooperieren und insbesondere die OLE-Spezifikation im Wesentlichen die gleiche Weise interpretieren.  
  
 Es gibt eine Anzahl von Anforderungen an die von der Endbenutzer, der beibehalten werden soll, aufgrund der schließen-Interaktion zwischen einem Container und Server, die direkte Aktivierung unterstützt:  
  
-   Die Anzeige der Präsentation (der Metadatei gezeichnet, der `COleServerItem::OnDraw` außer Kraft setzen) sollte genau gleich aussehen als wenn es für die Bearbeitung (außer, dass Bearbeitungstools nicht sichtbar sind) gezeichnet wird.  
  
-   Wenn der Container vergrößert, sollten das Fenster des Servers zu!  
  
-   Container und Server sollten Objekte für die Bearbeitung mit dieselben Metriken anzeigen. Dies bedeutet, dass Sie mit einem Zuordnungsmodus basierend auf der Anzahl der *logische* Pixel pro Zoll – nicht physischen Pixel pro Zoll beim Rendern auf dem Anzeigegerät.  
  
> [!NOTE]
>  Da die direkte Aktivierung gilt nur für Elemente, die eingebettet sind, (nicht verknüpft), gilt die Zoomen nur für eingebettete Objekte. Sehen Sie in beiden APIs `COleServerDoc` und `COleServerItem` für Zoomen verwendet werden. Der Grund für diese Zwiespalt ist, dass nur Funktionen, die für die verknüpfte oder eingebettete Elemente gelten in `COleServerItem` (Dies können Sie eine verbreitete Implementierung haben) und Funktionen, die nur für eingebettete Objekte gültig sind befinden sich der `COleServerDoc` Klasse (aus der Perspektive des Verwaltungsservers, ist die **Dokument** eingebettet wird).  
  
 Die meisten ständig befindet auf Ausführender der Server, dass der Server muss beachten Zoomfaktor für den Container und dessen Bearbeitung Oberfläche nach Bedarf ändern. Aber wie der Server bestimmt den Zoomfaktor, den der Container verwendet wird  
  
## <a name="mfc-support-for-zooming"></a>MFC-Unterstützung für Zoomen  
 Der aktuelle Zoomfaktor kann bestimmt werden, durch den Aufruf `COleServerDoc::GetZoomFactor`. Diese aufrufen, wenn das Dokument nicht in-Place aktiv wird führt immer zu 100 % Zoom Faktor (oder Verhältnis 1:1). Aufrufen dieser zwar etwas anderes als 100 % von in-Place aktiv zurückgegeben werden kann.  
  
 Ein Beispiel für vergrößern/verkleinern ordnungsgemäß finden Sie im MFC-OLE-Beispiel [HIERSVR](../visual-cpp-samples.md). Vergrößern HIERSVR wird verkompliziert von der Tatsache, dass er zeigt Text an, und Text, in der Regel keine Skalierung eine lineare Interpolation (Hinweise, typografische Konventionen Entwurf Breiten und Höhen alle erschweren die Angelegenheit). Dennoch HIERSVR ist eine angemessene Referenz zum Vergrößern/Verkleinern ordnungsgemäß implementieren, und ist daher die MFC-Lernprogramm [SCRIBBLE](../visual-cpp-samples.md) (Schritt 7).  
  
 `COleServerDoc::GetZoomFactor` Bestimmt den Zoomfaktor basierend auf einer Reihe von anderen verfügbaren Metriken aus dem Container oder aus der Implementierung Ihrer `COleServerItem` und `COleServerDoc` Klassen. Kurz gesagt, wird der aktuelle Zoomfaktor der folgenden Formel bestimmt:  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 Das Rechteck POSITION richtet sich nach den Container. Es wird an den Server zurückgegeben, während der direkten Aktivierung beim `COleClientItem::OnGetItemPosition` wird aufgerufen und wird aktualisiert, wenn der Container des Servers ruft `COleServerDoc::OnSetItemRects` (mit einem Aufruf von `COleClientItem::SetItemRects`).  
  
 Das AUSMAß der CONTAINER ist etwas komplexer zu berechnen. Wenn der Container aufgerufen hat `COleServerItem::OnSetExtent` (mit einem Aufruf von `COleClientItem::SetExtent`), wird das AUSMAß der CONTAINER diesen Wert in Pixel, die basierend auf der Anzahl der Pixel pro logischem Zoll () konvertiert. Wenn der Container nicht SetExtent (Dies ist normalerweise die Groß-/Kleinschreibung) aufgerufen, die CONTAINER-Block ist die Größe von zurückgegeben `COleServerItem::OnGetExtent`. Deshalb, wenn der Container nicht SetExtent aufgerufen hat, das Framework geht davon aus, wenn dem so wäre die Container er mit 100 % des natürlichen Wertebereichs aufgerufen haben würde (Rückgabewert `COleServerItem::GetExtent`). Anders ausgedrückt, das Framework wird davon ausgegangen, dass der Container 100 % (nicht mehr und nicht kleiner) des Elements anzeigt.  
  
 Es ist wichtig, obwohl beachten, dass `COleServerItem::OnSetExtent` und `COleServerItem::OnGetExtent` Namen ähnlich sind, sie das gleiche Attribut des Elements nicht bearbeiten. `OnSetExtent` wird aufgerufen, um lassen Sie den Server, die wissen, wie viel des Objekts im Container (unabhängig von den Zoomfaktor) angezeigt wird und `OnGetExtent` wird von der Container kann feststellen der idealen Größe des Objekts aufgerufen.  
  
 Durch jede der APIs beteiligten ansehen, erhalten Sie ein klareres Bild:  
  
## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent  
 Diese Funktion sollte die "natürliche Size" in HIMETRIC-Einheiten des Elements zurück. Die beste Möglichkeit, die "natürliche Größe" vorstellen wird es als die Größe definiert Sie kann beim Drucken kann. Die hier zurückgegebene Größe ist Zeichenfolgenkonstante für ein bestimmtes Element-Inhalt (ähnlich wie die Metadatei, die Zeichenfolgenkonstante für ein bestimmtes Element ist). Diese Größe ändert sich nicht, wenn Zoomen auf das Element angewendet wird. In der Regel nicht geändert werden, wenn der Container dem Element mehr oder weniger Speicherplatz durch den Aufruf gibt `OnSetExtent`. Ein Beispiel für eine Änderung möglicherweise von einem einfachen Text-Editor mit der Empfängerprozess keine "Margin", die basierend auf den letzten Block gesendet, die vom Container Text umbrochen. Wenn ein Server ändern, sollte der Server wahrscheinlich die OLEMISC_RECOMPOSEONRESIZE bit in der Registrierung festgelegt (siehe die OLE-SDK-Dokumentation für Weitere Informationen zu dieser Option).  
  
## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent  
 Diese Funktion wird aufgerufen, wenn der Container "mehr oder weniger" des Objekts zeigt. Die meisten Container werden nicht auf allen aufzurufen. Die standardmäßige Implementierung speichert den letzten Wert empfangen aus dem Container im "M_sizeExtent", die im verwendet wird `COleServerDoc::GetZoomFactor` bei der Berechnung des oben beschriebenen CONTAINER Block-Wertes.  
  
## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects  
 Diese Funktion wird aufgerufen, nur, wenn das Dokument in-Place aktiv ist. Sie wird aufgerufen, wenn der Container der Position des Elements oder des Clipping auf das Element angewendete aktualisiert. Das Rechteck POSITION bietet wie oben beschrieben den Zähler bei der Berechnung des Zoom-Faktor. Ein Server anfordern, dass die Position eines Elements geändert werden, durch den Aufruf `COleServerDoc::RequestPositionChange`. Der Container kann oder reagiert nicht auf diese Anforderung durch den Aufruf `OnSetItemRects` (mit einem Aufruf von `COleServerItem::SetItemRects`).  
  
## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw  
 Es ist wichtig, beachten Sie, dass die Metadatei erstellt, durch Überschreiben der `COleServerItem::OnDraw` erzeugt genau die gleiche Metadatei, unabhängig von den aktuellen Zoomfaktor. Der Container kann die Metadatei nach Bedarf skaliert werden. Dies ist ein wichtiger Unterschied zwischen der Ansicht `OnDraw` und dem Server das `OnDraw`. Das Anzeigen von Handles vergrößern/verkleinern, erstellt das Element nur einen *zoombarem* Metadatei an und lässt sie bis zu der Container die entsprechenden vergrößern/verkleinern möchten.  
  
 Die beste Möglichkeit, sicherzustellen, dass der Server ordnungsgemäß verhält, ist die Verwendung die Implementierung der `COleServerDoc::GetZoomFactor` , wenn das Dokument in-Place aktiv ist.  
  
## <a name="mfc-support-for-in-place-resizing"></a>MFC-Unterstützung für die direkte Größenänderung  
 MFC implementiert vollständig die Größenänderung im direkten-Schnittstelle, wie in der Spezifikation OLE 2 beschrieben. Die Benutzeroberfläche wird unterstützt, indem die `COleResizeBar` -Klasse, eine benutzerdefinierte Meldung WM_SIZECHILD und besondere Behandlung dieser Nachricht in `COleIPFrameWnd`.  
  
 Sie möchten möglicherweise implementieren andere Behandlung dieser Nachricht als was durch das Framework bereitgestellt wird. Wie oben beschrieben wird, bleibt das Framework die Ergebnisse der direkten Ändern der Größe von bis zu dem Container, der Server antwortet, um die Änderung in den Zoomfaktor. Wenn der Container durch Festlegen der beiden reagiert CONTAINER BLÖCKEN und POSITIONSRECHTECK während der Verarbeitung seiner `COleClientItem::OnChangeItemPosition` (infolge eines Aufrufs für aufgerufen `COleServerDoc::RequestPositionChange`) und dann die direkte Größenänderung führt "mehr oder weniger" des Elements in die Bearbeitung anzeigen Fenster ". Wenn der Container reagiert, indem Sie nur das POSITIONSRECHTECK festlegen, bei der Verarbeitung von `COleClientItem::OnChangeItemPosition`der Zoomfaktor wird geändert, und das Element angezeigt, die "vergrößert bzw. verkleinert."  
  
 Ein Server kann (in gewissem Umfang) steuern, was geschieht, während diese Verhandlungen. Ein Arbeitsblatt, z. B. möglicherweise festlegen, ob mehr oder weniger Zellen anzeigen, wenn der Benutzer die Fenstergröße ändert, während der Bearbeitung des Elements direktes. Ändern Sie die "Seitenränder" sind identisch mit dem Fenster und Umbrechen von Text an den neuen Rand möglicherweise ein Word einstellen. Server, implementieren Sie dies durch Ändern der natürlichen Block (die Größe von zurückgegebenen `COleServerItem::OnGetExtent`) die Größenänderung wird nach Abschluss. Dadurch wird das Rechteck POSITION und die CONTAINER-Blocks zu ändern, indem Sie die gleiche Menge, Datensammlungen, die in der gleichen Zoomfaktor, aber eine größere oder kleinere Anzeigebereich. Darüber hinaus, mehr oder weniger des Dokuments werden sichtbar, in der Metadatei von generierten `OnDraw`. In diesem Fall wird das Dokument selbst ändern, wenn der Benutzer das Element, anstatt nur des Ansichtsbereichs ändert.  
  
 Können Sie benutzerdefinierte Größe zu implementieren und weiterhin nutzen von bereitgestellte Benutzeroberfläche `COleResizeBar` durch Überschreiben der WM_SIZECHILD-Nachricht in Ihrem `COleIPFrameWnd` Klasse. Weitere Informationen zu den Besonderheiten der WM_SIZECHILD, finden Sie unter [technischen Hinweis 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

