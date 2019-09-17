---
title: Ändern der Stile eines mit MFC erstellten Fensters
ms.date: 11/04/2016
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
ms.openlocfilehash: ef79fc88604d565a942fdb0ae07d5fc5a2e0ebeb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509002"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Ändern der Stile eines mit MFC erstellten Fensters

In seiner Version der `WinMain` Funktion registriert MFC mehrere Standardfenster Klassen für Sie. Da Sie MFC normalerweise nicht bearbeiten `WinMain`, bietet diese Funktion keine Möglichkeit, die MFC-Standardfenster Stile zu ändern. In diesem Artikel wird erläutert, wie Sie die Stile einer solchen vorab registrierten Fenster Klasse in einer vorhandenen Anwendung ändern können.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>Ändern von Stilen in einer neuen MFC-Anwendung

Wenn Sie Visual C++ 2,0 oder höher verwenden, können Sie die Standardfenster Stile im Anwendungs-Assistenten ändern, wenn Sie die Anwendung erstellen. Auf der Seite Benutzeroberflächen Features des Anwendungs-Assistenten können Sie Stile für das Hauptrahmen Fenster und die untergeordneten MDI-Fenster ändern. Für beide Fenstertypen können Sie die Rahmen Stärke (Thick oder Thin) und eine der folgenden Optionen angeben:

- Ob das Fenster Steuerelemente minimieren oder maximieren soll.

- Gibt an, ob das Fenster anfänglich minimiert, maximiert oder keines von beiden angezeigt wird.

Bei Hauptrahmen Fenstern können Sie auch angeben, ob das Fenster über ein System Menü verfügt. Für untergeordnete MDI-Fenster können Sie angeben, ob das Fenster Splitter Bereiche unterstützt.

##  <a name="_core_changing_styles_in_an_existing_application"></a>Ändern von Stilen in einer vorhandenen Anwendung

Wenn Sie in einer vorhandenen Anwendung Fenster Attribute ändern, befolgen Sie stattdessen die Anweisungen im Rest dieses Artikels.

Wenn Sie die standardmäßigen Fenster Attribute ändern möchten, die von einer Framework-Anwendung verwendet werden, die mit dem Anwendungs-Assistenten erstellt wurde, überschreiben Sie [die virtuelle Member-Funktion des Fensters](../mfc/reference/cwnd-class.md#precreatewindow) . `PreCreateWindow`ermöglicht einer Anwendung den Zugriff auf den Erstellungs Prozess, der normalerweise intern von der [CDocTemplate](../mfc/reference/cdoctemplate-class.md) -Klasse verwaltet wird. Das Framework ruft `PreCreateWindow` unmittelbar vor dem Erstellen des Fensters auf. Ihre Anwendung kann die Attribute ändern, die zum Erstellen des Fensters verwendet werden, indem die an `PreCreateWindow` übergebene [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)-Struktur bearbeitet wird. Um z. b. sicherzustellen, dass ein Fenster keine Beschriftung verwendet, verwenden Sie den folgenden bitweisen Vorgang:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

Die [CTRLBARS](../overview/visual-cpp-samples.md) -Beispielanwendung veranschaulicht diese Vorgehensweise zum Ändern von Fenster Attributen. Je nachdem, was sich in `PreCreateWindow`der Anwendung ändert, kann es erforderlich sein, die Basisklassen Implementierung der Funktion aufzurufen.

In der folgenden Erörterung werden die SDI-und [MDI](#_core_the_mdi_case)-Fälle behandelt.

##  <a name="_core_the_sdi_case"></a>Der SDI-Fall

In einer Anwendung mit einer einzelnen Dokument Schnittstelle (SDI) ist der Standardfenster Stil im Framework eine Kombination aus den Formaten **WS_OVERLAPPEDWINDOW** und **FWS_ADDTOTITLE** . **FWS_ADDTOTITLE** ist ein MFC-spezifischer Stil, der das Framework anweist, den Dokumenttitel der Beschriftung des Fensters hinzuzufügen. Um die Fenster Attribute in einer SDI-Anwendung zu ändern, `PreCreateWindow` überschreiben Sie die-Funktion `CFrameWnd` in der von abgeleiteten Klasse `CMainFrame`(die der Anwendungs-Assistent benennt). Beispiel:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Mit diesem Code wird ein Hauptrahmen Fenster erstellt, ohne Schaltflächen zu minimieren und zu maximieren. Das Fenster wird anfänglich auf dem Bildschirm zentriert.

##  <a name="_core_the_mdi_case"></a>Der MDI-Fall

Es ist etwas mehr Arbeit erforderlich, um den Fenster Stil eines untergeordneten Fensters in einer MDI-Anwendung (Multiple Document Interface) zu ändern. Standardmäßig verwendet eine MDI-Anwendung, die mit dem Anwendungs-Assistenten erstellt wurde, die in MFC definierte [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) -Standardklasse. Um den Fenster Stil eines untergeordneten MDI-Fensters zu ändern, müssen Sie eine neue Klasse `CMDIChildWnd` von ableiten und alle Verweise `CMDIChildWnd` auf in Ihrem Projekt durch Verweise auf die neue Klasse ersetzen. Höchstwahrscheinlich befindet sich der einzige Verweis `CMDIChildWnd` auf in der Anwendung in der Member- `InitInstance` Funktion Ihrer Anwendung.

Der Standardfenster Stil, der in einer MDI-Anwendung verwendet wird, ist eine Kombination aus den Stilen **WS_CHILD**, **WS_OVERLAPPEDWINDOW**und **FWS_ADDTOTITLE** . Um die Fenster Attribute der untergeordneten Fenster einer MDI-Anwendung zu ändern, überschreiben Sie die [prekreatewindow](../mfc/reference/cwnd-class.md#precreatewindow) -Funktion `CMDIChildWnd`in der von abgeleiteten Klasse. Beispiel:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Dieser Code erstellt untergeordnete MDI-Fenster ohne die Schaltfläche maximieren.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren?

- [Windows-Stile](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Rahmen Fenster Stile](../mfc/frame-window-styles-cpp.md)

- [Fenster Stile](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>Siehe auch

[Rahmen Fenster Stile](../mfc/frame-window-styles-cpp.md)
