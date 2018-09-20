---
title: Ändern der Stile eines Fensters mit MFC erstellten | Microsoft-Dokumentation
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
ms.openlocfilehash: 98bcf57cc3a4697fc035fad73d8faf4e577a84b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420119"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Ändern der Stile eines mit MFC erstellten Fensters

In der Version von der `WinMain` MFC-Funktion registriert mehrere standardmäßige Fenstermanager-Klassen für Sie. Da Sie normalerweise die MFC bearbeiten nicht `WinMain`, dass die Funktion Sie keine Möglichkeit gibt, die MFC-Standard-Window-Stile zu ändern. In diesem Artikel wird erläutert, wie Sie die Stile einer solchen vorab registrierten Fensterklasse in einer vorhandenen Anwendung ändern können.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Ändern der Stile in einem neuen MFC-Anwendung

Wenn Sie Visual C++ 2.0 oder höher verwenden, können Sie die Standardstile für die Fenster im Anwendungs-Assistenten bei der Erstellung Ihrer Anwendung ändern. Klicken Sie auf Features der Benutzeroberfläche der Anwendung des Assistenten können Sie Stile für Ihre Hauptrahmenfenster und die untergeordneten MDI-Fenster ändern. Für beide Fenster können Sie angeben, die Rahmenstärke ("thick" oder "thin") und eine der folgenden:

- Gibt an, ob das Fenster minimieren oder maximieren-Steuerelemente verfügt.

- Gibt an, ob das Fenster anfänglich minimiert, maximiert angezeigt oder keines von beiden.

Für Windows der Hauptframe können Sie auch angeben, ob das Fenster ein Systemmenü verfügt. Für untergeordnete MDI-Fenster können Sie angeben, ob das Fenster Splitter Bereiche unterstützt.

##  <a name="_core_changing_styles_in_an_existing_application"></a> Ändern der Stile, die in einer vorhandenen Anwendung

Wenn Sie im Fenster Attribute in einer vorhandenen Anwendung ändern möchten, befolgen Sie die Anweisungen im weiteren Verlauf dieses Artikels stattdessen.

Um die Standardattribute-Fenster ein, die mit der Anwendungs-Assistent erstellt eine Framework-Anwendung zu ändern, außer Kraft setzen des Fensters [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) virtuelle Memberfunktion. `PreCreateWindow` ermöglicht es einer Anwendung des Erstellungsprozesses normalerweise intern verwaltet werden, indem Sie den Zugriff auf die [CDocTemplate](../mfc/reference/cdoctemplate-class.md) Klasse. Das Framework ruft `PreCreateWindow` unmittelbar vor dem Erstellen des Fensters. Durch Ändern der [CREATESTRUCT](../mfc/reference/createstruct-structure.md) Zeitstruktur `PreCreateWindow`, die Anwendung kann die Attribute, die zum Erstellen des Fensters ändern. Um sicherzustellen, dass ein Fenster eine Beschriftung nicht verwendet wird, verwenden Sie beispielsweise den folgenden bitweisen Vorgang:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

Die [CTRLBARS](../visual-cpp-samples.md) beispielanwendung veranschaulicht dieses Verfahren zum Ändern von Fensterattributen. Je nachdem, was in Ihrer Anwendung ändert `PreCreateWindow`, es kann erforderlich sein, die Implementierung der Basisklasse der Funktion aufrufen.

Die folgende Erläuterung umfasst den SDI-Fall und die [MDI-Fall](#_core_the_mdi_case).

##  <a name="_core_the_sdi_case"></a> Der SDI-Fall

In einer einzelnen (SDI) Anwendung die, der Standardstil für Fenster in das Framework ist eine Kombination der **WS_OVERLAPPEDWINDOW** und **FWS_ADDTOTITLE** Stile. **FWS_ADDTOTITLE** eine MFC-spezifischen Format, das das hinzuzufügende den Titel des Dokuments, um die Beschriftung des Fensters Framework weist. Überschreiben, um das Fenster-Attribute in einer SDI-Anwendung zu ändern, die `PreCreateWindow` -Funktion in Ihrer Klasse abgeleitet `CFrameWnd` (die Namen der Anwendungs-Assistent `CMainFrame`). Zum Beispiel:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Dieser Code erstellt ein Hauptrahmenfenster ohne Schaltflächen "Minimieren" und "Maximieren" und ohne beträchtliche Rahmen. Das Fenster wird anfänglich auf dem Bildschirm zentriert.

##  <a name="_core_the_mdi_case"></a> Im Fall von MDI

Ein wenig mehr Aufwand ist erforderlich, um den Fensterstil eines untergeordneten Fensters, in eine Anwendung der multiple Document Interface (MDI) zu ändern. Standardmäßig verwendet eine MDI-Anwendung mit der Anwendungs-Assistent erstellt standardmäßig [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) Klasse, die in MFC definiert. Um den Fensterstil eines untergeordneten MDI-Fensters zu ändern, müssen Sie eine neue Klasse von ableiten `CMDIChildWnd` , und Ersetzen Sie alle Verweise auf `CMDIChildWnd` in Ihrem Projekt Verweise auf die neue Klasse. In den meisten Fällen den einzigen Verweis auf `CMDIChildWnd` in der Anwendung befindet sich in Ihrer Anwendungsverzeichnis `InitInstance` Member-Funktion.

Der Stil für den Standard-Fenster in einer MDI-Anwendung verwendet, ist eine Kombination der **WS_CHILD**, **WS_OVERLAPPEDWINDOW**, und **FWS_ADDTOTITLE** Stile. Um die Attribute im Fenster des MDI-Anwendung untergeordneter Fenster ändern möchten, überschreiben die [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) -Funktion in Ihrer Klasse abgeleitet `CMDIChildWnd`. Zum Beispiel:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Dieser Code erstellt die untergeordneten MDI-Formulars Windows ohne eine Schaltfläche "Maximieren".

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Windows-Stile](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)

- [Window-Stile](https://msdn.microsoft.com/library/windows/desktop/ms632600)

## <a name="see-also"></a>Siehe auch

[Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)

