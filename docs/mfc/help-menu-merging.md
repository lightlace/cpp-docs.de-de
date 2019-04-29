---
title: Verschachteln des Hilfemenüs
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], merging
- merging Help menus [MFC]
- Help [MFC], for active document containers
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
ms.openlocfilehash: e1e8f9af696b6ea4cd485f4215e1c8425098e987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396404"
---
# <a name="help-menu-merging"></a>Verschachteln des Hilfemenüs

Wenn ein Objekt in einem Container aktiv ist, bietet der Zusammenführungsfunktion Protokoll der OLE-Dokumente das Objekt vollständige Kontrolle über die **Hilfe** Menü. Hilfethemen für den Container sind daher nicht verfügbar, es sei denn, der Benutzer das Objekt deaktiviert wird. Die active Document Containment-Architektur baut auf den Regeln für ein direktes Zusammenführungsfunktion damit sowohl des Containers und eines aktiven Dokuments, das zum Freigeben von klicken Sie im Menü aktiv ist. Die neuen Regeln sind einfach zusätzliche Konventionen dafür, welche Komponente welchen Teil des Menüs besitzt, und wie das freigegebene Menü erstellt wird.

Die neue Konvention ist einfach. In aktive Dokumente die **Hilfe** Menü verfügt über zwei Menüelemente der obersten Ebene wie folgt aufgebaut:

`Help`

`Container Help >`

`Object Help    >`

Z. B. wenn ein Word-Abschnitt ist in der Office-Binder, aktiv der **Hilfe** Menü würde wie folgt aussehen:

`Help`

`Binder Help >`

`Word Help   >`

Beide Menüelemente sind hierarchische Menüs, die unter denen zusätzliche Menüelemente speziell für den Container und das Objekt an dem Benutzer bereitgestellt werden. Welche Elemente hier angezeigt werden hängt von den Container und Objekte beteiligt.

Zum Erstellen dieses zusammengeführt **Hilfe** Menü, das aktive Dokument Containment-Architektur ändert das normale Verfahren der OLE-Dokumente. Gemäß der OLE-Dokumente, die zusammengeführte Menüleiste haben sechs Gruppen von Menüs, nämlich **Datei**, **bearbeiten**, **Container**, **Objekt**,  **Fenster**, **Hilfe**in dieser Reihenfolge. In jeder Gruppe kann NULL oder mehr Menüs vorhanden sein. Die Gruppen **Datei**, **Container**, und **Fenster** auf den Container und die Gruppen gehören **bearbeiten**, **-Objekt,** und **Hilfe** auf das Objekt gehören. Wenn das Objekt ausführen das Zusammenführen von Menüs möchte, erstellt eine leere Menüleiste und übergibt sie an den Container. Fügt der Container die Menüs, klicken Sie dann durch Aufrufen von `IOleInPlaceFrame::InsertMenus`. Das Objekt auch übergibt eine Struktur, die ein Array von sechs LONG-Werte (**OLEMENUGROUPWIDTHS**). Nach dem Einfügen die Menüs, markiert der Container wie viele Menüs, die sie in den einzelnen Gruppen und dann gibt hinzugefügt. Klicken Sie dann fügt das Objekt über die Menüs, achten auf die Anzahl von Menüs in jeder Containergruppe. Schließlich übergibt das Objekt der zusammengeführten Menüleiste und das Array (enthält die Anzahl der Menüs in jeder Gruppe), OLE, gibt einen Opaque "Deskriptor im Menü" behandelt. Später das Objekt übergibt dieses Handle und die zusammengeführte Menüleiste an den Container über `IOleInPlaceFrame::SetMenu`. Zu diesem Zeitpunkt wird der Container wird in der zusammengeführten Menü und übergibt das Handle auch an OLE, aus, sodass OLE ordnungsgemäße Verteilung von Menü-Nachrichten durchführen kann.

In der geänderten active Document-Prozedur, das Objekt muss zunächst initialisiert die **OLEMENUGROUPWIDTHS** Elemente auf 0 (null), vor der Übergabe an den Container. Der Container führt dann eine Einfügung normales Menü mit einer Ausnahme: Der Container-Fügt ein **helfen** wie das letzte Element im Menü und speichert Sie in den letzten Eintrag des (sechsten) den Wert 1 die **OLEMENUGROUPWIDTHS** Array (d. h. Breite [5], die Hilfe-Gruppe des Objekts gehört). Dies **Hilfe** Menü müssen nur ein Element wird ein Untermenü der "**Container Hilfe** >" Cascade-Menü, die wie oben beschrieben.

Das Objekt führt dann seine normales Menü Einfügen-Code, außer dass vor dem Einfügen der **Hilfe** Menü, überprüft er die sechste Eingabe der **OLEMENUGROUPWIDTHS** Array. Wenn der Wert 1 ist und der Name der das letzte Menü ist **helfen** (oder die entsprechende, lokalisierte Zeichenfolge), und das Objekt fügt seine **Hilfe** Menü als Untermenü des Containers **helfen** ein Menü.

Das Objekt legt dann das sechste Element des **OLEMENUGROUPWIDTHS** 0 (null) und das fünfte Element um eins erhöht. OLE wissen, dass dadurch die **Hilfe** Menü gehört, auf den Container und die Menü-Nachrichten, die in diesem Menü (und die darin enthaltenen Untermenüs) entspricht, die in den Container weitergeleitet werden soll. Es obliegt klicken Sie dann den Container weiterleiten **WM_INITMENUPOPUP**, **WM_SELECT**, **WM_COMMAND**, und in anderen Fehlermeldungen im Zusammenhang mit dem Menü, die des Objekts gehören Teil der **Hilfe** Menü. Dies erfolgt mithilfe von **WM_INITMENU** ein Flag zu löschen, der den Container angibt, in der des Objekts gibt an, ob der Benutzer navigiert **Hilfe** Menü. Klicken Sie dann der Container zu überwacht **WM_MENUSELECT** geöffnet oder ein Element auf der **Hilfe** Menü, das der Container selbst nicht hinzugefügt haben. Auf den Eintrag, es bedeutet, dass der Benutzer in einem Menü Objekt navigiert ist, damit der Container legt das Flag "im"Menü Hilfe"Objekt" fest und verwendet den Zustand des Flags, um alle weiterzuleiten **WM_MENUSELECT**, **WM_INITMENUPOPUP**, und  **WM_COMMAND** Nachrichten mindestens auf das Objektfenster. (Bei Funktionsende wird der Container löscht das Flag und verarbeitet dann die gleichen Nachrichten selbst.) Der Container sollte verwenden Sie das Fenster, die von des Objekts zurückgegeben `IOleInPlaceActiveObejct::GetWindow` fungieren als Ziel für diese Nachrichten.

Wenn das Objekt eine NULL in der sechsten Elements des erkennt **OLEMENUGROUPWIDTHS**, wird der üblichen Regeln der OLE-Dokumente. Dieses Verfahren umfasst die Container, die Teil sind **Hilfe** Zusammenführungsfunktion sowie diejenigen, die nicht der Fall ist.

Wenn das Objekt aufruft `IOleInPlaceFrame::SetMenu`, bevor das zusammengeführte Menü Balken-, die Überprüfungen Container anzeigen, ob von der **Hilfe** Menü enthält ein zusätzliches Untermenü, zusätzlich zu, was der Container eingefügt hat. Wenn also der Container lässt die **Hilfe** in der zusammengeführten Menüleiste im Menü. Wenn die **helfen** Menü verfügt nicht über eine zusätzliche Untermenü, entfernen Sie den Container wird die **helfen** Menü in der zusammengeführten Menüleiste. Diese Prozedur umfasst Objekte, die Teilnahme an **Hilfe** Zusammenführungsfunktion sowie diejenigen, die nicht der Fall ist.

Zum Schluss Zeitpunkt zum disassemblieren des im Menüs ist, das Objekt entfernt bei der eingefügten **helfen** Menü neben anderen entfernen eingefügt Menüs. Wenn der Container seine Menüs entfernt, entfernt er seine **Hilfe** Menü neben den anderen Menüs, die sie eingefügt hat.

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containers.md)
