---
title: 'Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt'
ms.date: 09/20/2018
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 0793511f09be9dcb37732c4c16bfd2b3038a6cf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567257"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt

In dieser exemplarischen Vorgehensweise erfahren, wie Sie einen einfachen Direct2D hinzufügen (D2D)-Objekt in ein Visual C++-Projekt für Microsoft Foundation Class-Bibliothek (MFC), und erstellen Sie das Projekt klicken Sie dann in eine Anwendung, die gibt "Hello, World" auf einem Farbverlaufshintergrund.

Die exemplarische Vorgehensweise zeigt, wie folgende Aufgaben ausgeführt wird:

- Erstellen Sie eine MFC-Anwendung.

- Erstellen Sie einen Pinsel mit Volltonfarbe und einen Pinsel mit linearem Farbverlauf.

- Ändern Sie den Farbverlaufspinsel, damit sie ordnungsgemäß beim Ändern des Fensters angepasst wird.

- Implementieren Sie einen zeichnen D2D-Handler.

- Überprüfen Sie die Ergebnisse aus.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Vorraussetzungen

Um diese exemplarische Vorgehensweise abzuschließen, benötigen Sie Visual Studio installiert, mit der **Desktopentwicklung mit C++** arbeitsauslastung und den optionalen **Visual C++ MFC für X86 und X64** Komponente.

## <a name="to-create-an-mfc-application"></a>Zum Erstellen einer MFC_Anwendung

1. Auf der **Datei** Startmenü **neu** und wählen Sie dann **Projekt**.

1. In der **neues Projekt** im Dialogfeld im linken Bereich unter **installierte Vorlagen**, erweitern Sie **Visual C++** und wählen Sie dann **MFC**. Wählen Sie im mittleren Bereich **MFC-Anwendung**. In der **Namen** geben *MFCD2DWalkthrough*. Klicken Sie auf **OK**.

1. In der **MFS-Anwendungsassistenten**, wählen Sie **Fertig stellen** ohne Änderung von Einstellungen.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Um einen Pinsel mit Volltonfarbe und einen Pinsel mit linearem Farbverlauf zu erstellen

1. In **Projektmappen-Explorer**in die **MFCD2DWalkthrough** in-Projekt die **Headerdateien** Ordner öffnen Element "MFCD2DWalkthroughView.h". Fügen Sie folgenden Code, der `CMFCD2DWalkthroughView` Klasse, um drei Data-Variablen zu erstellen:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Speichern Sie die Datei, und schließen Sie sie.

1. In der **Quelldateien** Ordner öffnen Element "MFCD2DWalkthroughView.cpp". Im Konstruktor für die `CMFCD2DWalkthroughView` Klasse, fügen Sie folgenden Code:

   ```cpp
   // Enable D2D support for this window:
   EnableD2DSupport();

   // Initialize D2D resources:
   m_pBlackBrush = new CD2DSolidColorBrush(
       GetRenderTarget(),
       D2D1::ColorF(D2D1::ColorF::Black));

   m_pTextFormat = new CD2DTextFormat(
       GetRenderTarget(),
       _T("Verdana"),
       50);

   m_pTextFormat->Get()->SetTextAlignment(
       DWRITE_TEXT_ALIGNMENT_CENTER);

   m_pTextFormat->Get()->SetParagraphAlignment(
       DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

   D2D1_GRADIENT_STOP gradientStops[2];

   gradientStops[0].color =
       D2D1::ColorF(D2D1::ColorF::White);

   gradientStops[0].position = 0.f;
   gradientStops[1].color =
       D2D1::ColorF(D2D1::ColorF::Indigo);

   gradientStops[1].position = 1.f;

   m_pLinearGradientBrush = new CD2DLinearGradientBrush(
       GetRenderTarget(),
       gradientStops,
       ARRAYSIZE(gradientStops),
       D2D1::LinearGradientBrushProperties(
           D2D1::Point2F(0,0),
           D2D1::Point2F(0,0)));
   ```

   Speichern Sie die Datei, und schließen Sie sie.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Der Pinsel mit Farbverlauf ändern, sodass es entsprechend beim Ändern des Fensters angepasst wird

1. Auf der **Projekt** Menü wählen **-Klassen-Assistent**.

1. In der **MFC-Klassenassistent**unter **Klassenname**Option `CMFCD2DWalkthroughView`.

1. Auf der **Nachrichten** Registerkarte die **Nachrichten** Kontrollkästchen `WM_SIZE` und wählen Sie dann **Handler hinzufügen**. Diese Aktion fügt der `OnSize` Nachrichtenhandler, an die `CMFCD2DWalkthroughView` Klasse.

1. In der **vorhandene Handler** Kontrollkästchen `OnSize`. Wählen Sie **Code bearbeiten** zum Anzeigen der `CMFCD2DWalkthroughView::OnSize` Methode. Fügen Sie am Ende der Methode den folgenden Code ein.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Speichern Sie die Datei, und schließen Sie sie.

## <a name="to-implement-a-d2d-drawing-handler"></a>Um eine Zeichnung D2D-Handler zu implementieren

1. Auf der **Projekt** Menü wählen **-Klassen-Assistent**.

1. In der **MFC-Klassenassistent**unter **Klassenname**Option `CMFCD2DWalkthroughView`.

1. Auf der **Nachrichten** Registerkarte **benutzerdefinierte Meldung hinzufügen**.

1. In der **benutzerdefinierte Meldung hinzufügen** Dialogfeld die **benutzerdefinierte Windows-Meldung** geben *AFX_WM_DRAW2D*. In der **Meldungshandlername** geben *OnDraw2D*. Wählen Sie die **registrierte Meldung** aus, und wählen Sie dann **OK**. Diese Aktion Fügt einen Meldungshandler für die AFX_WM_DRAW2D-Nachricht an die `CMFCD2DWalkthroughView` Klasse.

1. In der **vorhandene Handler** Kontrollkästchen `OnDraw2D`. Wählen Sie **Code bearbeiten** zum Anzeigen der `CMFCD2DWalkthroughView::OnDraw2D` Methode. Verwenden Sie diesen Code für die `CMFCD2DWalkthroughView::OnDrawD2D` Methode:

   ```cpp
   afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(
       WPARAM wParam,
       LPARAM lParam)
   {
       CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;
       ASSERT_VALID(pRenderTarget);

       CRect rect;
       GetClientRect(rect);

       pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);

       pRenderTarget->DrawText(
           _T("Hello, World!"),
           rect,
           m_pBlackBrush,
           m_pTextFormat);

       return TRUE;
   }
   ```

   Speichern Sie die Datei, und schließen Sie sie.

## <a name="to-verify-the-results"></a>Die Ergebnisse überprüfen

Erstellen Sie die Anwendung, und führen Sie sie aus. Sie müssen ein Farbverlauf, der sich ändert, wenn Sie die Größe des Fensters. "Hello World!" sollte in der Mitte des Rechtecks angezeigt werden.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
