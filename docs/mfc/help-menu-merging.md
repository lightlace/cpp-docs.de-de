---
title: Hilfemenüs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menus [MFC], merging
- merging Help menus [MFC]
- Help [MFC], for active document containers
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce8d5212f78546c08734aed6fd7e236fa4446007
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355534"
---
# <a name="help-menu-merging"></a>Verschachteln des Hilfemenüs
Wenn ein Objekt innerhalb eines Containers aktiv ist, bietet der Zusammenführungsfunktion Protokoll der OLE-Dokumente das Objekt vollständige Kontrolle über die **Hilfe** Menü. Hilfethemen für den Container sind daher nicht verfügbar, es sei denn, der Benutzer das Objekt deaktiviert wird. Die active Document Containment-Architektur wird erweitert, auf die Regeln für die direkte Zusammenführungsfunktion damit Containers und eines aktiven Dokuments, das im Menü freigeben aktiv ist. Die neue Regeln sind einfach zusätzliche Konventionen dafür, welche Komponente welchen Teil des Menüs besitzt und wie der gemeinsame Menü erstellt wird.  
  
 Die neue Konvention ist einfach. Aktive Dokumente der **Hilfe** Menü verfügt über zwei Menüelemente auf oberster Ebene wie folgt aufgebaut:  
  
 `Help`  
  
 `Container Help >`  
  
 `Object Help    >`  
  
 Z. B. wenn ein Word-Abschnitt ist in den Office Binder aktiv und dann die **Hilfe** Menü würde wie folgt aussehen:  
  
 `Help`  
  
 `Binder Help >`  
  
 `Word Help   >`  
  
 Beide Menüelemente sind hierarchische Menüs, die unter denen alle zusätzliche Menüelemente speziell für den Container und das Objekt für dem Benutzer bereitgestellt werden. Welche Elemente hier angezeigt werden hängt von den Container und Objekte an.  
  
 Zum Erstellen dieses zusammengeführt **Hilfe** Menü, das aktive Dokument Containment-Architektur ändert das normale Verfahren für OLE-Dokumente. Entsprechend OLE-Dokumente, die zusammengeführte Menüleiste können sechs Gruppen von Menüs, nämlich **Datei**, **bearbeiten**, **Container**, `Object`, **Fenster**, **Hilfe**in dieser Reihenfolge. In jeder Gruppe können NULL oder mehr Menüs vorhanden sein. Die Gruppen **Datei**, **Container**, und **Fenster** auf den Container und die Gruppen gehören **bearbeiten**, **-Objekt,** und **Hilfe** auf das Objekt gehören. Wenn das Objekt ausführen das Zusammenführen von Menüs möchte, eine leeren Menüleiste erstellt und übergibt sie an den Container. Klicken Sie dann fügt der Container seine Menüs durch Aufrufen von **IOleInPlaceFrame::InsertMenus**. Das Objekt auch übergibt eine Struktur, die ein Array von sechs LONG-Werte (**OLEMENUGROUPWIDTHS**). Nach dem Einfügen der Menüs, markiert der Container wie viele Menüs, die jeweils ihre Gruppen, und klicken Sie dann die gibt hinzugefügt. Danach fügt das Objekt seine Menüs unter Beachtung der Anzahl von Menüs in jeder Containergruppe. Schließlich übergibt das Objekt der zusammengeführten Menüleiste und das Array (enthält die Anzahl von Menüs, die in jeder Gruppe) an OLE, welche gibt ein nicht transparenter "Menü Deskriptor" zu behandeln. Später das Objekt übergibt dieses Handle und die zusammengeführte Menüleiste an den Container über **SetMenu**. Zu diesem Zeitpunkt wird der Container wird das zusammengeführte Menü angezeigt, und auch übergibt das Handle an OLE, sodass OLE ordnungsgemäße Verteilung von Nachrichten im Menü ausführen kann.  
  
 In der geänderten active Document-Prozedur, das Objekt muss zunächst initialisiert werden die **OLEMENUGROUPWIDTHS** Elemente auf 0 (null), vor der Übergabe an den Container. Führt der Container eine normale Menü Einfügen mit einer Ausnahme: die Container-einfügungen eine **Hilfe** Menüs als das letzte Element und speichert Sie im letzten Eintrag (sechste) des Wert 1 die **OLEMENUGROUPWIDTHS** Array (d. h. Breite [5], der Supportgruppe für das Objekt gehört). Dies **Hilfe** Menü ein Untermenü ist nur ein Element angezeigt wird der "**Container Help** >" Cascade Menü wie zuvor beschrieben.  
  
 Das Objekt führt dann seine normalen Menü Einfügen-Code, außer dass vor dem Einfügen der **Hilfe** Menü, überprüft er die sechste Eingabe der **OLEMENUGROUPWIDTHS** Array. Wenn der Wert 1 ist und der Name des letzten Menüs **Hilfe** (oder die entsprechende lokalisierte Zeichenfolge), und das Objekt fügt seine **Hilfe** Menü als Untermenü des Containers **Hilfe** Menü ".  
  
 Legt das Objekt dann das sechste Element des **OLEMENUGROUPWIDTHS** auf 0 (null) und das fünfte Element um eins erhöht. Auf diese Weise können OLE wissen, dass die **Hilfe** Menü gehört, auf den Container und das Menü (und die darin enthaltenen Untermenüs) entsprechende Menü-Nachrichten weitergeleitet werden soll, auf den Container. Es obliegt klicken Sie dann den Container zum Weiterleiten `WM_INITMENUPOPUP`, **WM_SELECT**, **WM_COMMAND**, und andere Fehlermeldungen im Zusammenhang mit dem Menü, die auf den Teil des Objekts gehören die **-Hilfe**  Menü. Dies erfolgt mithilfe von `WM_INITMENU` ein Flag entfernen, die dem Container mitteilt, ob der Benutzer in des Objekts navigiert **Hilfe** Menü. Klicken Sie dann der Container überwacht `WM_MENUSELECT` oder ein Element auf der **Hilfe** Menü, das der Container nicht selbst hinzugefügt hat. Auf Eintrag, es bedeutet, dass der Benutzer navigiert in einem Menü Objekt so, dass der Container legt das Flag "im Hilfemenü von Objekt" fest und den Status dieses Flags zum Weiterleiten verwendet `WM_MENUSELECT`, `WM_INITMENUPOPUP`, und **WM_COMMAND** Nachrichten verwenden, als ein Minimum zu das Objektfenster. (Bei Funktionsende wird der Container löscht das Flag und verarbeitet dann diese gleichen Nachrichten selbst.) Der Container die zu verwendende Fensters aus des Objekts zurückgegeben **IOleInPlaceActiveObejct::GetWindow** Funktion wie das Ziel für diese Nachrichten fest.  
  
 Wenn das Objekt eine 0 (null) in das sechste Element des erkennt **OLEMENUGROUPWIDTHS**, es geht gemäß den normalen Regeln für OLE-Dokumente. Dieses Verfahren umfasst die Container, die gehören **Hilfe** sowie anderen nicht Zusammenführen von Menüs.  
  
 Wenn das Objekt aufruft **SetMenu**, bevor das zusammengeführte Menü Balken-, die Container-überprüft, ob Anzeigen der **Hilfe** Menü enthält ein zusätzliches Untermenü, zusätzlich zu, was der Container hat eingefügt. Wenn also die Container verlässt die **Hilfe** in die zusammengeführte Menüleiste im Menü. Wenn die **Hilfe** Menü verfügt nicht über eine zusätzliche Untermenü, entfernen Sie den Container wird dessen **Hilfe** der zusammengeführten Menüleiste das Menü. Dieses Verfahren umfasst die Objekte, die Teilnahme an **Hilfe** sowie anderen nicht Zusammenführen von Menüs.  
  
 Schließlich das Menü disassemblieren wird, das Objekt entfernt bei der eingefügten **Hilfe** Menü neben anderen entfernen eingefügt Menüs. Wenn der Container seine Menüs entfernt, entfernt er seine **Hilfe** Menü zusätzlich zu den anderen Menüs, die sie eingefügt hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containers.md)

