---
title: "TN040: MFC/OLE direkte Gr&#246;&#223;enanpassung und Zoomen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Direkte Aktivierung, Zoomen und Größenänderung"
  - "direkte Größenänderung"
  - "TN040"
  - "Zoomen und direkte Aktivierung"
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# TN040: MFC/OLE direkte Gr&#246;&#223;enanpassung und Zoomen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis erläutert die Probleme in Bezug auf direkte Bearbeiten und wie ein Server das richtige und Zoomen direkte Größenanpassung erreichen soll.  Mit direkter Aktivierung wird das WYSIWYG\-Konzept einen weiteren Schritt darin unternommen, dass Container und Server miteinander zusammenarbeiten, und insbesondere die OLE\-Spezifikation auf ganz ähnliche Art und Weise interpretiert.  
  
 Aufgrund der normalen Interaktion zwischen einem Container und einem Server, die direkte Aktivierung dort unterstützen, sollten Sie einige Erwartungen vom Endbenutzer, der erhalten bleiben soll:  
  
-   Die Präsentationsanzeige \(die Metadatei gezeichnet in der `COleServerItem::OnDraw` \- Überschreibung\) sollte gleich wie genau betrachten, wenn sie für Bearbeiten gezeichnet wird \(außer dass Bearbeitungstools, sind nicht sichtbar\).  
  
-   Wenn der Container vergrößert, sollte das Serverfenster auch\!  
  
-   der Container und Server, Sie Objekte zum Bearbeiten mit derselben Metriken wenn.  Dies bedeutet mithilfe eines Zuordnungsmodus auf Grundlage der Anzahl von *logischen* Pixeln physische pro Pixel Zoll\-nots pro Zoll, beim Rendern auf dem Anzeigegerät.  
  
> [!NOTE]
>  Da direkte Aktivierung nur auf Elemente angewendet wird, die eingebettet \(nicht verknüpft\) werden, Ereignisse gilt nur auf eingebettete Objekte.  Sie finden APIs in sowohl `COleServerDoc` und `COleServerItem`, die zum Zoomen verwendet werden.  Der Grund für diese Dichotomie ist, dass nur Funktionen, die für die verknüpfte und eingebettete Elemente gültig sind, in `COleServerItem` \(diese ermöglicht es Ihnen, eine weiter gehende allgemeine Implementierung zu haben\) und Funktionen, die nur für eingebettete Objekte gültig sind, sind in der `COleServerDoc`\-Klasse sind \(aus Sicht des Servers, ist die `document`, die eingebettet wird\).  
  
 Die meisten der Belastung wird auf die Serverimplementierung, und platziert, dass der Server den Zoomfaktor des Containers und berücksichtigen die Bearbeitungsschnittstelle entsprechend ändern muss.  Aber wie bestimmt der Server den Zoomfaktor, dass der Container verwendet?  
  
## MFC\-Unterstützung zum Zoomen  
 Der aktuelle Zoomfaktor kann bestimmt werden, indem `COleServerDoc::GetZoomFactor` aufgerufen wird.  Das Aufrufen dieses, wenn das Dokument direkt nicht aktiviert ist, führt immer einen Zoomfaktor 100% \(oder 1:1\-Verhältnis\).  Das Aufrufen, wenn sie direkt aktiv, gibt möglicherweise etwas anders 100% zurück.  
  
 Ein Beispiel aus richtig vergrößern finden Sie das Beispiel [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE.  Das Zoomen in HIERSVR wird dadurch kompliziert, dem sie Text anzeigt, und im Allgemeinen nicht skaliert in einer linearen Weise \(Hinweise, typografische Konventionen, Entwurfsbreiten alle und Höhen erschweren die Angelegenheit\).  Noch HIERSVR ist ein geeigneter Verweis für das Implementieren ordnungsgemäß Vergrößern und deshalb ist MFC Referenten\- [SCRIBBLE](../top/visual-cpp-samples.md) \(Schritt 7\).  
  
 `COleServerDoc::GetZoomFactor` bestimmt den Zoomfaktor auf Grundlage verschiedene verfügbare Metriken vom Container oder von der Implementierung der `COleServerItem` und `COleServerDoc`\-Klassen.  Kurz gesagt wird der Stromzoomfaktor von der folgenden Formel bestimmt:  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 Das POSITIONS\-RECHTECK wird vom Container bestimmt.  Er wird an den Server während der direkten Aktivierung zurückgegeben, wenn `COleClientItem::OnGetItemPosition` aufgerufen und wird aktualisiert, wenn der Container `COleServerDoc::OnSetItemRects` des Servers aufruft \(durch Aufruf von `COleClientItem::SetItemRects`\).  
  
 Der CONTAINER\-WERTEBEREICH ist etwas komplizierter zu berechnen.  Wenn der Container `COleServerItem::OnSetExtent` \(mit einem Aufruf von `COleClientItem::SetExtent`\) aufgerufen hat, ist der CONTAINER\-WERTEBEREICH dieser Wert, der an Pixel auf Grundlage der Anzahl der Pixel pro Zoll logischen konvertiert wird.  Wenn der Container nicht SetExtent aufgerufen hat \(die normalerweise der Fall ist\), ist der CONTAINER\-WERTEBEREICH die Größe, die von `COleServerItem::OnGetExtent` zurückgegeben wird.  Wenn der Container nicht SetExtent aufgerufen hat, verwendet das Framework an, dass, wenn er ausgeführt, der Container ihn mit 100% des natürlichen Wertebereichs aufgerufen hat \(der Wert zurückgegeben von **COleServerItem::GetExtent**\).  Gab eine andere Methode, dem Framework einsetzen an, dass der Container 100% \(nicht mehr, kein\) weniger von Element angezeigt wird.  
  
 Beachten Sie, dass, obwohl, `COleServerItem::OnSetExtent` und `COleServerItem::OnGetExtent` ähnliche Namen haben, nicht das gleiche Attribut des Elements ändern.  `OnSetExtent` wird aufgerufen, um den Server zu informieren, wie viel des Objekts im Container \(unabhängig davon den Zoomfaktor\) angezeigt wird und `OnGetExtent` wird vom Container bezeichnet, um optimale Größe des Objekts zu bestimmen.  
  
 Durch jede der betroffenen APIs berücksichtigen, können Sie ein klareres Bild abrufen:  
  
## COleServerItem::OnGetExtent  
 Diese Funktion sollte der vollständige Größe "in" HIMETRIC\-Einheiten des Elements zurückgeben.  Die beste Methode, mit der natürliche "Größe" für die Anwendungsprogrammierung, zu definieren, da die Größe möglicherweise kann, als gedruckt.  Die Größe, die hier zurückgegeben wird, ist für Inhalt eines bestimmten Zeitraums unverändert \(ähnlich wie die Metadatei, die für ein bestimmtes Element konstant ist\).  Diese Größe ändert sich nicht, während zum Zoomen Element angewendet wird.  Sie normalerweise nicht geändert, wenn der Container das Element mehr oder weniger Platz vorhanden ist, indem Sie `OnSetExtent` aufrufen.  Ein Beispiel einer Änderung ist das eines einfachen Text\-Editors ohne "Rand" Funktion, die den Text auf dem letzten einband Wertebereich, der über den Container gesendet wurde.  Wenn ein Server ändert, muss der Server das OLEMISC\_RECOMPOSEONRESIZE\-Bit in der Systemregistrierung wahrscheinlich festlegen \(siehe die OLE\-SDK\-Dokumentation weitere Informationen zu dieser Option\).  
  
## COleServerItem::OnSetExtent  
 Diese Funktion wird aufgerufen, wenn der Container "mehr oder weniger" des Objekts anzeigt.  Die meisten Containern rufen nicht übernehmen überhaupt auf.  Die Standardimplementierung speichert den letzten Wert, der vom Container in "m\_sizeExtent" empfangen, das in `COleServerDoc::GetZoomFactor` verwendet wird, wenn es den CONTAINER\-WERTEBEREICHSwert berechnet, der oben beschriebenen.  
  
## COleServerDoc::OnSetItemRects  
 Diese Funktion wird nur aufgerufen, wenn das Dokument direkt aktiv ist.  Sie wird aufgerufen, wenn der Container jede der die Position oder das Clipping Elements aktualisiert, die auf das Element angewendet werden.  Das POSITIONS\-RECHTECK, wie oben erläutert, wird der Zähler für die Zoomfaktorberechnung bereit.  Ein Server können anfordern, dass die Elementposition geändert wird, indem `COleServerDoc::RequestPositionChange` aufgerufen wird.  Der Container reagiert möglicherweise auf diese Anforderung, indem Sie `OnSetItemRects` aufrufen \(durch Aufruf von **COleServerItem::SetItemRects**\).  
  
## COleServerDoc::OnDraw  
 So erkennen ist wichtig, dass, wie die Metadatei, die erstellt wird, indem von `COleServerItem::OnDraw` überschrieben wird, genau dieselbe Metadatei erzeugt, unabhängig vom aktuellen Zoomfaktor.  Der Container skaliert die Metadatei entsprechend.  Dies ist ein wichtiger Unterschied zwischen `OnDraw` und `OnDraw` der Ansicht des Serverelements.  Die Ansicht verarbeitet Zoomen, wird das Element nur eine Metadatei *zoombare* und Arbeitsblätter es in Container, um das entsprechende Zoomen auszuführen.  
  
 Die beste Möglichkeit, zu sichergestellt, dass der Server nicht ordnungsgemäß verhält, ist, die Implementierung von `COleServerDoc::GetZoomFactor`, wenn das Dokument direkt aktiv ist.  
  
## MFC\-Unterstützung für direkte Größenanpassung  
 MFC implementiert vollständig die direkte Größenanpassungsschnittstelle, wie in der Spezifikation OLE 2 beschrieben.  Die Benutzeroberfläche wird von der `COleResizeBar`\-Klasse, eine Gewohnheitsmeldung **WM\_SIZECHILD** und besondere Behandlung sie in `COleIPFrameWnd` unterstützt.  
  
 Sie sollten unterschiedliche Behandlung diese Meldung als implementieren, was vom Framework bereitgestellt wird.  Wie oben beschrieben, können das Framework die Ergebnisse des direkten Größe nach Container \- der Server reagiert auf die Änderung im Zoomfaktor.  Wenn der Container reagiert, indem festgelegt wird, treten CONTAINER\-WERTEBEREICH und POSITIONS\-RECHTECK während der Verarbeitung vom `COleClientItem::OnChangeItemPosition` \(als Ergebnis eines Aufrufs von `COleServerDoc::RequestPositionChange`\) dann das direktes Größe ändern, dem Ein\- "mehr oder weniger" des \<Elementname\>\-Elements im Bearbeitungsfenster.  Wenn der Container reagiert, indem nur das POSITIONS\-RECHTECK während der Verarbeitung von `COleClientItem::OnChangeItemPosition` festlegen, ändert der Zoomfaktor und das Element wird angezeigt "Einchecken oder verkleinert."  
  
 Ein Server kann steuern \(zu einem gewissen\) was während dieser Verhandlungs\- geschieht.  Ein Arbeitsblatt, beispielsweise vielleicht, um mehr oder weniger Zellen angezeigt, wenn der Benutzer das Fenster beim Bearbeiten von direkten Elements angepasst wird.  Ein Wortprozessor ausgewählt ist, um die "Seitenränder" zu ändern, können sie gleich wie das Fenster und das rewrap der Text dem neuen Rand.  Server implementieren dieses, indem den natürlichen Wertebereich ändern \(die Größe von `COleServerItem::OnGetExtent` zurückgegeben\) Wenn die Größenanpassung durchgeführt wird.  Dadurch wird das POSITIONS\-RECHTECK und den CONTAINER\-WERTEBEREICH, über die gleiche Zeitdauer, Ergebnis desselben Zoomfaktors zu ändern, ein kleineres oder größeres Anzeigebereich.  Darüber hinaus sind mehr oder weniger des Dokuments Metadatei\- sichtbar, die durch `OnDraw` generiert wird.  In diesem Fall ändert das Dokument selbst, wenn der Benutzer die Größe des Elements ändert, nicht nur das Sendegebiets.  
  
 Sie können benutzerdefinierte Größenanpassung implementieren und die Benutzeroberfläche weiterhin nutzen, die von `COleResizeBar` bereitgestellt wird, indem Sie die **WM\_SIZECHILD** Nachricht in der `COleIPFrameWnd`\-Klasse überschreiben.  Weitere Informationen zu den Besonderheiten von **WM\_SIZECHILD**, finden Sie unter [Technischer Hinweis 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)