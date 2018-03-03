---
title: Grundlagen zu Symbolleisten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RT_TOOLBAR
dev_langs:
- C++
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 136b9f5dd36c9e4092b8e5c15ac1738541cf71f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-fundamentals"></a>Grundlegendes über Symbolleisten
Dieser Artikel beschreibt die grundlegende MFC-Implementierung, in dem Sie eine Standardsymbolleiste Ihrer Anwendung hinzufügen, indem Sie eine Option im Anwendungs-Assistenten auswählen kann. Zu den behandelten Themen gehören:  
  
-   [Die Symbolleistenoption Anwendungs-Assistent](#_core_the_appwizard_toolbar_option)  
  
-   [Die Symbolleiste im code](#_core_the_toolbar_in_code)  
  
-   [Bearbeiten die Symbolleistenressource](#_core_editing_the_toolbar_resource)  
  
-   [Mehrere Symbolleisten](#_core_multiple_toolbars)  
  
##  <a name="_core_the_appwizard_toolbar_option"></a>Die Anwendung Assistenten Symbolleistenoption  
 Um eine einzige Symbolleiste mit Schaltflächen zu erhalten, wählen Sie die Symbolleistenoption standardmäßiges Andocken auf der Seite mit der Bezeichnung Benutzeroberflächen-Features. Dadurch wird die Anwendung Code hinzugefügt, die:  
  
-   Ein Symbolleistenobjekt erstellt wird.  
  
-   Verwaltet die Symbolleiste, einschließlich der Fähigkeit, andocken oder verschieben.  
  
##  <a name="_core_the_toolbar_in_code"></a>Die Symbolleiste im Code  
 Die Symbolleiste ist eine [CToolBar](../mfc/reference/ctoolbar-class.md) Objekt deklariert als Datenmember Ihrer Anwendung **CMainFrame** Klasse. Das heißt, ist die Symbolleistenobjekt in die Hauptframe-Fensterobjekt eingebettet. Dies bedeutet, dass MFC die Symbolleiste erstellt, wenn das Rahmenfenster erstellt und zerstört wird, wenn es das Rahmenfenster zerstört. Die folgende Deklaration der partiellen Klasse, für eine Anwendung multiple Document Interface (MDI), zeigt der Datenmember für eine eingebettete Symbolleiste und eine eingebettete Statusleiste. Darüber hinaus wird gezeigt, die Außerkraftsetzung von der `OnCreate` Memberfunktion.  
  
 [!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]  
  
 Symbolleiste Erstellung erfolgt in **CMainFrame::OnCreate**. MFC-Aufrufe [OnCreate](../mfc/reference/cwnd-class.md#oncreate) nach dem Erstellen des Fensters für den Rahmen, aber bevor er angezeigt wird. Die Standardeinstellung `OnCreate` , der Assistent für die Anwendung generiert führt die folgenden Tasks aus Symbolleiste:  
  
1.  Ruft die `CToolBar` des Objekts [erstellen](../mfc/reference/ctoolbar-class.md#create) Memberfunktion zum Erstellen des zugrunde liegenden [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt.  
  
2.  Aufrufe [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) Laden Sie die Symbolleiste Ressourceninformationen.  
  
3.  Ruft die Funktionen zum Andocken, Gleitkommatyp und QuickInfos aktivieren. Weitere Informationen zu diesen aufrufen, finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md).  
  
> [!NOTE]
>  Im allgemeinen MFC-Beispiel [DOCKTOOL](../visual-cpp-samples.md) enthält Abbildungen des alten und neuen MFC-Symbolleisten. Die Symbolleisten, mit denen **COldToolbar** erfordern Aufrufe in Schritt 2 `LoadBitmap` (statt `LoadToolBar`) und `SetButtons`. Die neue Symbolleisten erfordern Aufrufe von `LoadToolBar`.  
  
 Das Andocken, Gleitkommatyp und Tool Tipps Aufrufe sind optional. Sie können diese Zeilen entfernen `OnCreate` Falls gewünscht. Das Ergebnis ist eine Symbolleiste, die festen, "float" oder Redock nicht und kann nicht zum Anzeigen von QuickInfos bleibt.  
  
##  <a name="_core_editing_the_toolbar_resource"></a>Bearbeiten die Symbolleistenressource  
 Die Standardsymbolleiste Sie mit dem Assistenten für die Anwendung erhalten basiert auf einer **RT_TOOLBAR** die benutzerdefinierte Ressource in MFC, Version 4.0 eingeführt. Sie können diese Ressource mit dem Bearbeiten der [Symbolleisten-Editor](../windows/toolbar-editor.md). Der Editor können Sie problemlos hinzufügen, löschen und erneute Anordnen von Schaltflächen. Sie enthält einen grafischen Editor für die Schaltflächen, die die allgemeine Grafik-Editor in Visual C++ sehr ähnlich sind. Wenn Sie Symbolleisten in früheren Versionen von Visual C++ bearbeitet, finden die Aufgabe wesentlich einfacher jetzt Sie.  
  
 Um eine Symbolleisten-Schaltfläche mit einem Befehl zu verbinden, Sie geben Sie der Schaltfläche eine Befehls-ID, z. B. `ID_MYCOMMAND`. Geben Sie die Befehls-ID der Schaltfläche auf der Seite in der Symbolleisten-Editor. Erstellen Sie eine Handlerfunktion für den Befehl (siehe [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md) für Weitere Informationen).  
  
 Neue [CToolBar](../mfc/reference/ctoolbar-class.md) Memberfunktionen arbeiten mit der **RT_TOOLBAR** Ressource. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) jetzt findet der [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) beim Laden der Bitmap für die Symbolleisten-Schaltflächen und [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) legen Sie die Schaltflächenformate und Schaltflächen mit Bitmapbildern verbinden.  
  
 Einzelheiten zur Verwendung des Symbolleisten-Editors finden Sie unter [Symbolleisten-Editor](../windows/toolbar-editor.md).  
  
##  <a name="_core_multiple_toolbars"></a>Mehrere Symbolleisten  
 Der Anwendungs-Assistent bietet Ihnen über ein Standard-Symbolleiste. Wenn Sie mehr als eine Symbolleiste in Ihrer Anwendung benötigen, können Sie den Code auf die zusätzlichen Symbolleisten, die basierend auf den vom Assistenten generierten Code für die Standardsymbolleiste modellieren.  
  
 Wenn Sie eine Symbolleiste als Ergebnis eines Befehls anzeigen möchten, müssen Sie:  
  
-   Erstellen Sie eine neue Symbolleistenressource über die Symbolleiste des Editors und Laden Sie es in `OnCreate` mit der [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) Memberfunktion.  
  
-   Betten Sie ein neues [CToolBar](../mfc/reference/ctoolbar-class.md) Objekt in die Hauptframe-Fensterklasse.  
  
-   Stellen Sie die entsprechenden in-Funktionsaufrufe `OnCreate` , andocken oder verschieben die Symbolleiste, legen Sie die Stile und so weiter.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Implementieren der MFC-Symbolleiste (Übersicht die Übersichtsinformationen auf der Symbolleiste)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen  
  
-   [Arbeiten mit dem Toolbar-Steuerelement](../mfc/working-with-the-toolbar-control.md)  
  
-   [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)

