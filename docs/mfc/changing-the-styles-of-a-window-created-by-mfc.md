---
title: Ändern der Stile eines Fensters mit MFC erstellten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34ea35bd43e2bf4e96cbc1552ff169789c1068a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345728"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Ändern der Stile eines mit MFC erstellten Fensters
In der Version von den `WinMain` MFC-Funktion mehrere Standardfenster-Klassen für Sie registriert. Da Sie normalerweise die MFC bearbeiten nicht `WinMain`, dass die Funktion keine Möglichkeit bestand, ändern Sie die MFC-Fenster Standardstile werden ermittelt. In diesem Artikel wird erläutert, wie Sie einen der Stile eines solchen einen vorab registrierten Fensterklasse in einer vorhandenen Anwendung ändern können.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Ändern von Formaten in eine neue MFC-Anwendung  
 Wenn Sie Visual C++ 2.0 oder höher verwenden, können Sie Fenster Standardstile im Anwendungs-Assistenten ändern, wenn Ihre Anwendung zu erstellen. Dem Anwendungsassistenten Benutzeroberflächen-Features auf der Seite können Sie für Ihre Hauptrahmenfenster und die untergeordneten MDI-Fenster Stile ändern. Für beide Fenster können Sie angeben, dessen Rahmenstärke ("thick" oder "thin") und keines der folgenden:  
  
-   Gibt an, ob das Fenster minimieren bzw. maximieren-Steuerelemente aufweist.  
  
-   Gibt an, ob das Fenster anfänglich minimiert, maximiert angezeigt oder keines von beiden.  
  
 Für das Hauptrahmenfenster können Sie auch angeben, ob das Fenster ein Systemmenü verfügt. Für untergeordnete MDI-Fenster können Sie angeben, ob das Fenster Splitter Bereiche unterstützt.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a> Ändern von Formaten in einer vorhandenen Anwendung  
 Wenn Sie im Fenster Attribute in einer vorhandenen Anwendung ändern möchten, folgen Sie den Anweisungen im weiteren Verlauf dieses Artikels stattdessen.  
  
 Um das Fenster-Standardattribute, die von einer frameworkanwendung erstellt mit Anwendungs-Assistenten verwendet zu ändern, überschreiben Sie des Fensters [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) virtuelle Memberfunktion. `PreCreateWindow` ermöglicht es einer Anwendung der Erstellungsprozess normalerweise intern verwaltet werden, indem Sie den Zugriff auf die [CDocTemplate](../mfc/reference/cdoctemplate-class.md) Klasse. Das Framework ruft `PreCreateWindow` unmittelbar vor dem Erstellen des Fensters. Durch Ändern der [CREATESTRUCT](../mfc/reference/createstruct-structure.md) Struktur übergeben, um `PreCreateWindow`, die Anwendung kann die Attribute, die zum Erstellen des Fensters ändern. Um sicherzustellen, dass ein Fenster eine Beschriftung nicht verwendet wird, verwenden Sie z. B. die folgende bitweise Operation:  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 Die [jeder](../visual-cpp-samples.md) beispielanwendung für veranschaulicht diese Vorgehensweise zum Ändern von Fensterattributen. Je nachdem, was in Ihrer Anwendung ändert `PreCreateWindow`, es kann erforderlich sein, die Implementierung der Basisklasse der Funktion aufrufen.  
  
 Die folgende Erläuterung umfasst die SDI Groß-/Kleinschreibung und den [MDI Groß-/Kleinschreibung](#_core_the_mdi_case).  
  
##  <a name="_core_the_sdi_case"></a> Die SDI Groß-/Kleinschreibung  
 In einer einzelnen Dokument Interface (SDI)-Anwendung ist das Standardformat für Fenster im Framework eine Kombination der **WS_OVERLAPPEDWINDOW** und **FWS_ADDTOTITLE** Stile. **FWS_ADDTOTITLE** ist eine MFC-spezifischen-Formatvorlage, die das Framework den Titel des Dokuments auf die Beschriftung des Fensters hinzufügen weist. Überschreiben, um das Fenster Attribute in einer SDI-Anwendung zu ändern, die `PreCreateWindow` Funktion in Ihrer Klasse abgeleitet `CFrameWnd` (die die Namen der Anwendungs-Assistent `CMainFrame`). Zum Beispiel:  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 Dieser Code erstellt ein Hauptrahmenfenster ohne Schaltflächen "Minimieren und Maximieren" und ohne eine beträchtliche Anzahl an Rahmen. Das Fenster wird anfangs auf dem Bildschirm zentriert.  
  
##  <a name="_core_the_mdi_case"></a> Die MDI-Groß-/Kleinschreibung  
 So ändern Sie den Fensterstil, der ein untergeordnetes Fenster in einer Anwendung der multiple Document Interface (MDI), ist etwas mehr Arbeit erforderlich. Standardmäßig verwendet eine MDI-Anwendung, die mit der Anwendungs-Assistent erstellt standardmäßig [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) Klasse, die in MFC definiert. Um den Fensterstil, der ein untergeordnetes MDI-Fenster zu ändern, leiten Sie eine neue Klasse von `CMDIChildWnd` , und Ersetzen Sie alle Verweise auf `CMDIChildWnd` in Ihrem Projekt Verweise auf die neue Klasse. Sehr wahrscheinlich lediglich einen Verweis auf `CMDIChildWnd` in der Anwendung befindet sich in der Anwendungsverzeichnis `InitInstance` Memberfunktion.  
  
 Das Fenster-Standardformat, die in einer MDI-Anwendung verwendet, ist eine Kombination der **WS_CHILD**, **WS_OVERLAPPEDWINDOW**, und **FWS_ADDTOTITLE** Stile. Um die Attribute Fenster eine MDI-Anwendung untergeordnetes Fenster zu ändern, überschreiben die [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) Funktion in Ihrer Klasse abgeleitet `CMDIChildWnd`. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 Dieser Code erstellt untergeordnete MDI-Fenster ohne eine Schaltfläche "Maximieren".  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Fensterstile](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
-   [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)  
  
-   [Fensterstile](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## <a name="see-also"></a>Siehe auch  
 [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)

