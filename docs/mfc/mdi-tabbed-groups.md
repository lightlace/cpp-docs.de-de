---
title: MDI-Gruppen im Registerkartenformat | Microsoft Docs
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
ms.openlocfilehash: 6a7cf6420a331d46f2a158c16a30d439f334a46b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350353"
---
# <a name="mdi-tabbed-groups"></a>MDI-Gruppen im Registerkartenformat
Die Gruppen im Registerkartenformat Funktion für mehrere Document Interface (MDI) kann mehrere Interface (MDI) dokumentanwendungen eine oder mehrere Fenster im Registerkartenformat anzeigen (oder Gruppen von Fenstern im Registerkartenformat, bekannt als *Gruppen im Registerkartenformat*) in den Bereich des MDI-Client. Fenster im Registerkartenformat können vertikal oder horizontal ausgerichtet werden. Wenn eine Anwendung mehrere im Registerkartenformat MDI-Gruppen hostet, werden die Gruppen durch Splitterfenstern getrennt.  
  
## <a name="features"></a>Features  
 Im folgenden sind die Funktionen im Registerkartenformat MDI-Gruppen.  
  
-   Eine Anwendung kann im Registerformat dynamisch erstellen.  
  
-   Eine Anwendung kann im Registerformat horizontal oder vertikal ausrichten.  
  
-   Gruppen von Fenstern im Registerformat werden durch Splitterfenstern getrennt. Benutzer kann Gruppen im Registerkartenformat Größe ändern, indem Sie die Verwendung des Splitters.  
  
-   Benutzer können die einzelne Registerkarten zwischen Gruppen ziehen.  
  
-   Benutzer können die einzelnen Registerkarten, um neue Gruppen erstellen, ziehen.  
  
-   Der Benutzer kann Registerkarten zu verschieben oder neue Gruppen erstellen, mit der ein Kontextmenü aufrufen.  
  
-   Eine Anwendung kann speichern und laden das Layout von Fenstern im Registerkartenformat.  
  
-   Eine Anwendung kann speichern und laden die Liste der MDI-Dokumente.  
  
-   Eine Anwendung kann Zugriff auf einzelne Gruppen im Registerkartenformat und ändern ihre Parameter.  
  
### <a name="using-mdi-tabbed-groups"></a>Mit der MDI-Gruppen im Registerkartenformat  
 Die folgenden werden Aufgaben, die häufig im Registerkartenformat MDI-Gruppen ausgeführt:  
  
-   Rufen Sie zum Aktivieren im Registerkartenformat MDI-Gruppen für eine Hauptrahmenfenster [CMDIFrameWndEx:: Enablemditabbedgroups](../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups). Der zweite Parameter dieser Methode ist eine Instanz von der `CMDITabInfo` Klasse. Sie können die Standardparameter verwenden oder ändern Sie sie vor dem Aufruf `CMDIFrameWndEx::EnableMDITabbedGroups`.  
  
-   Klicken Sie zum Ändern der Eigenschaften einer im Registerkartenformat MDI-Gruppe zur Laufzeit erstellen oder Ändern einer `CMDITabInfo` Objekt, und rufen `CMDIFrameWndEx::EnableMDITabbedGroups` erneut  
  
-   Im Registerkartenformat Windows, um eine Liste der MDI abzurufen, rufen Sie `CMDIFrameWndEx::GetMDITabGroups`.  
  
-   Rufen Sie zum Erstellen neuer Registerkartengruppe MDI neben einer aktiven Registerkartengruppe `CMDIFrameWndEx::MDITabNewGroup`.  
  
-   Aufrufen, um den Eingabefokus auf das vorherige oder nächste Fenster der Registerkartengruppe zu verschieben, `CMDIFrameWndEx::MDITabMoveToNextGroup`.  
  
-   Um festzustellen, ob ein Fenster Mitglied der MDI-Formulars ist im Registerkartenformat Gruppe Aufruf `CMDIFrameWndEx::IsMemberOfMDITabGroup`.  
  
-   Um festzustellen, ob MDI-Registerkarten oder im Registerkartenformat MDI-Gruppen für eine Hauptrahmenfenster aktiviert sind, rufen Sie `CMDIFrameWndEx::AreMDITabs`. Um nur zu ermitteln, ob im Registerkartenformat MDI-Gruppen aktiviert sind, rufen `CMDIFrameWndEx::IsMDITabbedGroup`.  
  
-   Überschreiben, um ein Kontextmenü anzuzeigen, wenn der Benutzer klickt auf eine Registerkarte oder es in eine andere im Registerkartenformat MDI-Gruppe zieht, `CMDIFrameWndEx::OnShowMDITabContextMenu` in der `CMDIFrameWndEx`-Klasse. Wenn Sie diese Methode nicht implementieren, wird die Anwendung nicht im Kontextmenü angezeigt.  
  
-   Um das Layout im Registerkartenformat MDI-Gruppen in einer Anwendung zu speichern, rufen `CMDIFrameWndEx::SaveMDIState`. Laden Sie eine zuvor gespeicherte MDI im Registerkartenformat Gruppenprofil, rufen Sie `CMDIFrameWndEx::LoadMDIState`. Sie können auch diese Methoden zum Laden und speichern die Liste der geöffneten Dokumente in einer MDI-Anwendung aufrufen. Weitere Informationen zu speichern und Laden von MDI-Status finden Sie unter [CMDIFrameWndEx::LoadMDIState](../mfc/reference/cmdiframewndex-class.md#loadmdistate).  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [CMDIFrameWndEx-Klasse](../mfc/reference/cmdiframewndex-class.md)   
 [CMDIChildWndEx-Klasse](../mfc/reference/cmdichildwndex-class.md)   
 [CMDITabInfo-Klasse](../mfc/reference/cmditabinfo-class.md)
