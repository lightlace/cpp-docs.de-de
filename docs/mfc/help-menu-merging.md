---
title: "Verschachteln des Hilfemen&#252;s | Microsoft Docs"
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
  - "Menüs, Zusammenführen"
  - "Zusammenführen von Hilfemenüs"
  - "Hilfe, für Active Document-Container"
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verschachteln des Hilfemen&#252;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Objekt innerhalb eines Containers aktiv ist, gibt das Menüzusammenführungsprotokoll von OLE\-Dokumenten die Objektvollständige kontrolle des Menüs **Hilfe**.  Folglich sind die Hilfethemen des Containers nicht verfügbar, es sei denn, dass der Benutzer das Objekt deaktiviert.  Die Active Document\-Kapselungsarchitektur erweitert die Regeln, sodass direkte Menüzusammenführung den Container und ein aktives Dokument können, das ausgewählt ist, im Menü freizugeben.  Die neuen Regeln sind einfach zusätzliche Konventionen darüber, welche Komponente besitzt, welcher Teil des Menüs und die freigegebene Menü erstellt wird.  
  
 Die neue Konvention ist einfach.  In den aktiven Dokumenten hat das Menü **Hilfe** zwei Menüelemente der obersten Ebene, die organisiert werden, wie folgt:  
  
 `Help`  
  
 `Container Help >`  
  
 `Object Help    >`  
  
 Wenn ein Word\-Abschnitt im sollte aktiv ist, wird das Menü **Hilfe** wird angezeigt, wie folgt:  
  
 `Help`  
  
 `Binder Help >`  
  
 `Word Help   >`  
  
 Beide Menüelemente sind Untermenüs, unter denen zusätzliche Menüelemente, die dem Container und auf das Objekt bestimmt sind, den Benutzer bereitstellt.  Welche Elemente hier angezeigt werden, hängt mit dem Container und die Objekte, die behandeln.  
  
 Um zusammengeführte dieses **Hilfe** Menü zu erstellen, ändert die Active Document\-Kapselungsarchitektur die normale OLE\-Dokumentprozedur.  Gemäß OLE\-Dokumenten kann die zusammengeführte Menüleiste sechs Gruppen Menüs, nämlich **Datei**, **Bearbeiten**, **Container**, `Object`, **Hilfe**, **Fenster** haben, in dieser Reihenfolge.  In jeder Gruppe, kann er keinen oder mehr geben Menüs.  Die Gruppen **Datei**, **Container** und **Fenster** gehören dem Container und Gruppen **Bearbeiten**, **Object,** und **Hilfe** gehören das Objekt.  Wenn das Objekt Menüzusammenführung tun möchte, erstellt es eine leere Menüleiste und an den Container.  Der Container fügt dann die Menüs ein, indem **IOleInPlaceFrame::InsertMenus** aufruft.  Das Objekt führt auch eine Struktur, die ein Array von sechs LANGEN Werte \(**OLEMENUGROUPWIDTHS**\) ist.  Nach Abruf der Menüs eingefügt hat, markiert der Container, wie Menüs er in eine der Gruppen hinzugefügt und gibt.  Dann fügt das Objekt seiner Menüs ein und erwähnt die Anzahl von Menüs in jeder Containergruppe.  Schließlich besteht das Objekt die zusammengeführte Menüleiste und das Array \(das die Anzahl von Menüs in jeder Gruppe enthält\), in OLE, das einem nicht transparenten "Menüdeskriptor" Handle zurückgibt.  Später, die die Objektübergaben und die zusammengeführte Menüleiste bin behandeln, zu **IOleInPlaceFrame::SetMenu**.  Derzeit zeigt der Container die zusammengeführte Menüleiste an und führt auch das Handle für OLE, dass OLE das richtige Weiterleiten von Menümeldungen ausführen kann.  
  
 In der geänderten aktiven Dokumentprozedur muss das Objekt die **OLEMENUGROUPWIDTHS**\-Elemente Null zuerst initialisieren, bevor es zum bin übergibt.  Anschließend führt der Container eine normale Menüeinfügung mit einer Ausnahme: Der Container wird ein Menü **Hilfe** als letztes Element ein und speichert einen Wert 1 im letzten \(6.\) Eintrag **OLEMENUGROUPWIDTHS** des Arrays \(das heißt, Breite \[5\], das der Hilfegruppe des Objekts gehört\).  In **Hilfe** Menü verfügt nur ein Element, das ein Untermenü ist, "**Containerhilfe** \>" überlappen Menü, wie zuvor beschrieben.  
  
 Das Objekt führt dann den normalen Menüeinfügungscode aus, außer dass, bevor das **Hilfe** Menü eingefügt, sucht es den 6. Eintrag **OLEMENUGROUPWIDTHS** des Arrays.  Wenn der Wert 1 und der Name des letzten Menüs **Hilfe** \(oder die entsprechende lokalisierte Zeichenfolge\) ist, wird das Objekt **Hilfe** sein als Menü Untermenü des Menüs **Hilfe** des Containers ein.  
  
 Das Objekt stellt die 6. Element von **OLEMENUGROUPWIDTHS** auf Null und inkrementiert die fünfte Element durch eines.  Dieses informiert OLE, dass das Menü **Hilfe** dem Container gehört und die Menümeldungen entsprechend diesem Menü \(und seinen Untermenüs\) bin weitergeleitet werden sollen.  Es wird die Verantwortung des Containers, `WM_INITMENUPOPUP` weiterzuleiten, **WM\_SELECT**, **WM\_COMMAND** usw. Menü\-verknüpfte Meldungen, die den Teil des Objekts des Menüs **Hilfe** gehören.  Dies wird erreicht, indem `WM_INITMENU` verwendet, um ein Flag wieder löschen, das den Container an, ob der Benutzer im Menü **Hilfe** des Objekts navigiert.  Der Container beobachtet dann `WM_MENUSELECT` für Eintrag in oder Beenden von jedem Element im Menü **Hilfe**, das die Container selbst nicht hinzugefügt.  Bei einem Eintrag Dies bedeutet, dass der Benutzer in ein Objektmenü navigiert, sodass der Container das Objekt "in Menüs Hilfe" Flag festgelegt und den Zustand dieses Flags, um jeden `WM_MENUSELECT`, `WM_INITMENUPOPUP` und **WM\_COMMAND** Meldungen, z minimalen, am Objektfenster weiterzuleiten. \(Bei Beendigung, löscht der Container das Flag und verarbeitet diese gleichen Meldungen auch.\) Der Container sollte das Fenster verwenden, das von der **IOleInPlaceActiveObejct::GetWindow**\-Funktion des Objekts als Ziel für diese Meldungen zurückgegeben wird.  
  
 Wenn das Objekt nicht im 6. Element von **OLEMENUGROUPWIDTHS** erkennt, wird sie entsprechend den normalen OLE\-Dokumentregeln fort.  Diese Prozedur zeigt Container, die an **Hilfe** Menüzusammenführung teilnehmen sowie die ab, die keine Typen darstellen.  
  
 Wenn das Objekt **IOleInPlaceFrame::SetMenu** aufruft, bevor sie angezeigt wird, überprüft die zusammengeführte Menüleiste, der Container, ob das Menü **Hilfe** ein zusätzliches Untermenü, verfügt zusätzlich zu, was der Container eingefügt hat.  Wenn dies fehlschlägt der Container handeln **Hilfe** Menü in der Menüleiste zusammengeführten.  Wenn das Menü **Hilfe** kein zusätzliches Untermenü verfügt, entfernt der Container handeln **Hilfe** Menü für die zusammengeführte Menüleiste.  Diese Verfahren werden Objekte, die an **Hilfe** Menüzusammenführung teilnehmen sowie die ab, die keine Typen darstellen.  
  
 Wenn schließlich ist es Zeit, das Menü zu disassemblieren, entfernt das Objekt das eingefügte Menü **Hilfe** zusätzlich zum Entfernen der eingefügten anderen Menüs.  Wenn der Container die Menüs entfernt, entfernt er sein Menü **Hilfe** zusätzlich zu den anderen Menüs, die es eingefügt hat.  
  
## Siehe auch  
 [Active Document\-Container](../mfc/active-document-containers.md)