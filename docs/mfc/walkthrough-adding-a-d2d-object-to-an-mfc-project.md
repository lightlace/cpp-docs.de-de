---
title: 'Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt'
ms.date: 04/25/2019
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 5e1c75e32899ef9697025d662eeec4a6a2482f2b
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304307"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt

In dieser exemplarischen Vorgehensweise wird erläutert, wie ein einfaches Direct2D-Objekt (D2D C++) zu einem Visual, Microsoft Foundation Class-Bibliothek (MFC)-Projekt hinzugefügt und dann das Projekt in einer Anwendung erstellt wird, die "Hello, World!" ausgibt. auf einem Farbverlaufs Hintergrund.

In der exemplarischen Vorgehensweise wird gezeigt, wie Sie diese Aufgaben ausführen:

- Erstellen Sie eine MFC-Anwendung.

- Erstellen Sie einen Pinsel mit voll Tonfarbe und einen Pinsel mit linearem Farbverlauf.

- Ändern Sie den Farbverlaufs Pinsel so, dass er sich entsprechend ändert, wenn die Größe des Fensters geändert wird.

- Implementieren Sie einen D2D-Zeichnungs Handler.

- Überprüfen Sie die Ergebnisse.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Erforderliche Komponenten

Um diese exemplarische Vorgehensweise durchführen zu können, müssen Sie Visual Studio mit der Arbeitsauslastung und der **optionalen C++ Visual MFC für x86-und x64** **- C++**  Komponente installiert haben.

## <a name="to-create-an-mfc-application"></a>So erstellen Sie eine MFC-Anwendung

1. Verwenden Sie den **MFC-Anwendungs-Assistenten** , um eine MFC-Anwendung zu erstellen. Unter Exemplarische Vorgehensweise [: Verwenden der neuen MFC-shellsteuerelemente](walkthrough-using-the-new-mfc-shell-controls.md) finden Sie Anweisungen zum Öffnen des Assistenten für Ihre Version von Visual Studio.

1. Geben Sie im Feld **Name den Namen** *MFCD2DWalkthrough*ein. Klicken Sie auf **OK**.

1. Klicken Sie im **MFC-Anwendungs-Assistenten**auf **Fertig** stellen, ohne die Einstellungen zu ändern.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>So erstellen Sie einen Pinsel mit voll Tonfarbe und einen Pinsel mit linearem Farbverlauf

1. Öffnen Sie in **Projektmappen-Explorer**im Projekt **MFCD2DWalkthrough** im Ordner **Header Dateien die Datei** MFCD2DWalkthroughView. h. Fügen Sie der `CMFCD2DWalkthroughView`-Klasse den folgenden Code hinzu, um drei Daten Variablen zu erstellen:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Speichern Sie die Datei, und schließen Sie Sie.

1. Öffnen Sie im Ordner **Quelldateien die Datei** MFCD2DWalkthroughView. cpp. Fügen Sie im Konstruktor für die `CMFCD2DWalkthroughView`-Klasse den folgenden Code hinzu:

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

   Speichern Sie die Datei, und schließen Sie Sie.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Um den Farbverlaufs Pinsel so zu ändern, dass er sich entsprechend ändert, wenn die Größe des Fensters geändert wird.

1. Wählen Sie im Menü **Projekt** die Option **Klassen-Assistent**aus.

1. Wählen Sie im **MFC-Klassen-Assistenten**unter **Klassenname**die Option `CMFCD2DWalkthroughView`aus.

1. Wählen Sie auf der Registerkarte **Nachrichten** im Feld **Meldungen** `WM_SIZE` aus, und wählen Sie dann **Handler hinzufügen**aus. Durch diese Aktion wird der `CMFCD2DWalkthroughView` Klasse der `OnSize` Meldungs Handler hinzugefügt.

1. Wählen Sie im Feld **vorhandene Handler** die Option `OnSize`aus. Wählen Sie **Code bearbeiten** aus, um die `CMFCD2DWalkthroughView::OnSize`-Methode anzuzeigen. Fügen Sie am Ende der-Methode den folgenden Code hinzu.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Speichern Sie die Datei, und schließen Sie Sie.

## <a name="to-implement-a-d2d-drawing-handler"></a>So implementieren Sie einen D2D-Zeichnungs Handler

1. Wählen Sie im Menü **Projekt** die Option **Klassen-Assistent**aus.

1. Wählen Sie im **MFC-Klassen-Assistenten**unter **Klassenname**die Option `CMFCD2DWalkthroughView`aus.

1. Wählen Sie auf der Registerkarte **Nachrichten** **benutzerdefinierte Meldung hinzufügen**aus.

1. Geben Sie im Dialogfeld **benutzerdefinierte Meldung hinzufügen** im Feld **benutzerdefinierte Windows-Meldung** *AFX_WM_DRAW2D*ein. Geben Sie im Feld **nachrichtenhandlername den Namen** *OnDraw2D*ein. Wählen Sie die Option **registrierte Nachricht** aus, und klicken Sie dann auf **OK**. Durch diese Aktion wird der `CMFCD2DWalkthroughView` Klasse ein Meldungs Handler für die AFX_WM_DRAW2D Nachricht hinzugefügt.

1. Wählen Sie im Feld **vorhandene Handler** die Option `OnDraw2D`aus. Wählen Sie **Code bearbeiten** aus, um die `CMFCD2DWalkthroughView::OnDraw2D`-Methode anzuzeigen. Verwenden Sie diesen Code für die `CMFCD2DWalkthroughView::OnDrawD2D`-Methode:

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

   Speichern Sie die Datei, und schließen Sie Sie.

## <a name="to-verify-the-results"></a>So überprüfen Sie die Ergebnisse

Erstellen Sie die Anwendung, und führen Sie sie aus. Es sollte ein Farbverlaufs Rechteck vorhanden sein, das sich ändert, wenn Sie die Größe des Fensters ändern. "Hello World!" sollte in der Mitte des Rechtecks angezeigt werden.

## <a name="see-also"></a>Siehe auch

[Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
