---
title: MDI-Gruppen im Registerkartenformat | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mdi [MFC], tabbed groups
- tabbed grous [MFC]
ms.assetid: 0a464f36-39b7-4e68-8b67-ec175de28377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35113181a21a5ff265b12269f57ee853f6011abc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442161"
---
# <a name="mdi-tabbed-groups"></a>MDI-Gruppen im Registerkartenformat

Die Gruppen im Registerkartenformat Funktion für mehrere Document Interface (MDI) ermöglicht Anwendungen für mehrere Dokumente Interface (MDI) eine oder mehrere Fenster im Registerformat angezeigt (oder Gruppen von Fenstern im Registerkartenformat, bekannt als *-Gruppen im Registerkartenformat*) in den Bereich des MDI-Client. Fenster im Registerkartenformat können vertikal oder horizontal ausgerichtet werden. Wenn eine Anwendung mehr als ein MDI-Gruppe im Registerkartenformat hostet, werden die Gruppen durch Splitterfenstern getrennt.

## <a name="features"></a>Features

Im folgenden finden die Funktionen der im Registerkartenformat MDI-Gruppen:

- Eine Anwendung kann im Registerformat dynamisch erstellen.

- Eine Anwendung kann im Registerformat Horizontales oder vertikales Ausrichten.

- Gruppen von Fenstern im Registerkartenformat werden durch Splitterfenstern getrennt. Der Benutzer kann Gruppen im Registerkartenformat mithilfe des Splitters ändern.

- Benutzer können die einzelne Registerkarten zwischen den Gruppen ziehen.

- Der Benutzer kann auf einzelne Registerkarten, um neue Gruppen erstellen ziehen.

- Der Benutzer kann Registerkarten zu verschieben oder neue Gruppen erstellen, über ein Kontextmenü.

- Eine Anwendung kann zu speichern und laden das Layout von Fenstern im Registerkartenformat.

- Eine Anwendung kann zu speichern und laden die Liste der MDI-Dokumente.

- Eine Anwendung kann Zugriff auf einzelnen Registerkarten Gruppen und ihre Parameter zu ändern.

### <a name="using-mdi-tabbed-groups"></a>Mit der MDI-Gruppen im Registerkartenformat

Im folgenden finden häufig mit im Registerkartenformat MDI-Gruppen ausgeführten Aufgaben:

- Rufen Sie zum Aktivieren im Registerkartenformat MDI-Gruppen für ein Hauptrahmenfenster [CMDIFrameWndEx:: Enablemditabbedgroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups). Der zweite Parameter dieser Methode ist eine Instanz von der `CMDITabInfo` Klasse. Sie können die Standardparameter verwenden oder ändern Sie sie vor dem Aufruf `CMDIFrameWndEx::EnableMDITabbedGroups`.

- Klicken Sie zum Ändern der Eigenschaften einer MDI-Registerkarten-Gruppe zur Laufzeit erstellen oder Ändern einer `CMDITabInfo` Objekt, und rufen `CMDIFrameWndEx::EnableMDITabbedGroups` erneut

- Zum Abrufen einer Liste der MDI-Fenster, rufen Sie `CMDIFrameWndEx::GetMDITabGroups`.

- Um eine neue MDI-Registerkarten Gruppe neben einer Gruppe mit aktiven im Registerkartenformat zu erstellen, rufen `CMDIFrameWndEx::MDITabNewGroup`.

- Um den Eingabefokus auf das vorherige oder nächste Fenster der Registerkartengruppe verschieben möchten, rufen Sie `CMDIFrameWndEx::MDITabMoveToNextGroup`.

- Um festzustellen, ob ein Fenster Mitglied der MDI-Formulars ist im Registerkartenformat in Gruppe-Aufruf `CMDIFrameWndEx::IsMemberOfMDITabGroup`.

- Um zu bestimmen, ob ein Hauptrahmenfenster MDI-Registerkarten oder im Registerkartenformat MDI-Gruppen aktiviert sind, rufen Sie `CMDIFrameWndEx::AreMDITabs`. Um nur zu bestimmen, ob im Registerkartenformat MDI-Gruppen aktiviert sind, rufen `CMDIFrameWndEx::IsMDITabbedGroup`.

- Um ein Kontextmenü angezeigt wird, wenn der Benutzer klickt auf einer Registerkarte oder es in ein anderes in MDI-Registerkarten zieht, außer Kraft setzen `CMDIFrameWndEx::OnShowMDITabContextMenu` in die `CMDIFrameWndEx`-abgeleitete Klasse. Wenn Sie diese Methode nicht implementieren, wird die Anwendung nicht im Kontextmenü angezeigt.

- Um das Layout der MDI-Registerkarten, Gruppen in einer Anwendung zu speichern, rufen `CMDIFrameWndEx::SaveMDIState`. Laden Sie eine zuvor gespeicherte MDI im Registerkartenformat auf Gruppenprofil, rufen Sie `CMDIFrameWndEx::LoadMDIState`. Sie können auch diese Methoden zum Laden oder speichern Sie die Liste der geöffneten Dokumente in einer MDI-Anwendung aufrufen. Weitere Informationen zum Speichern und Laden des MDI-Zustands finden Sie unter [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate).

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[CMDIFrameWndEx-Klasse](../mfc/reference/cmdiframewndex-class.md)<br/>
[CMDIChildWndEx-Klasse](../mfc/reference/cmdichildwndex-class.md)<br/>
[CMDITabInfo-Klasse](../mfc/reference/cmditabinfo-class.md)
