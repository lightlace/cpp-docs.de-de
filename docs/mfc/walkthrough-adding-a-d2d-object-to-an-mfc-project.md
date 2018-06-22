---
title: 'Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt | Microsoft Docs'
ms.custom: ''
ms.date: 06/19/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68a6d5a0cda8c4d7fd06cf7bb6b9c1b60e50374b
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306007"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>Exemplarische Vorgehensweise: Hinzufügen eines D2D-Objekts zu einem MFC-Projekt

In dieser exemplarischen Vorgehensweise erfahren Sie, wie eine grundlegende Direct2D hinzugefügt (D2D)-Objekt an einer Visual C++-Projekt für Microsoft Foundation Class-Bibliothek (MFC), und erstellen Sie das Projekt in eine Anwendung, die druckt "Hello, World" auf einem Farbverlaufshintergrund.

Erläutert, wie Sie diese Aufgaben ausführen:

- Erstellen Sie eine MFC-Anwendung.

- Erstellen Sie einen Pinsel mit Volltonfarbe und einem linearen Farbverlaufspinsel.

- Ändern Sie die Farbverlaufspinsel, sodass es entsprechend geändert wird, wenn die Fenstergröße geändert wird.

- Implementieren Sie einen zeichnen D2D-Handler.

- Überprüfen Sie die Ergebnisse aus.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie Visual Studio installiert, mit der **Desktopentwicklung mit C++** arbeitsauslastung und den optionalen **Visual C++ MFC für X86- und X64** Komponente.

## <a name="to-create-an-mfc-application"></a>Zum Erstellen einer MFC_Anwendung

1. Auf der **Datei** Sie im Menü **neu** und wählen Sie dann **Projekt**.

2. In der **neues Projekt** im Dialogfeld im linken Bereich unter **installierte Vorlagen**, erweitern Sie **Visual C++** und wählen Sie dann **MFC**. Wählen Sie im mittleren Bereich **MFC-Anwendung**. Geben Sie im Feld **Name** `MFCD2DWalkthrough`ein. Klicken Sie auf **OK**.

3. In der **MFC-Anwendung-Assistent**, wählen Sie **Fertig stellen** ohne Änderung von Einstellungen.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>So erstellen einen Pinsel mit Volltonfarbe und einem linearen Farbverlaufspinsel

1. In **Projektmappen-Explorer**in der **MFCD2DWalkthrough** in-Projekt die **Headerdateien** Ordner öffnen Element "MFCD2DWalkthroughView.h". Fügen Sie diesen Code, um die `CMFCD2DWalkthroughView` Klasse, um drei Datenvariablen zu erstellen:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Speichern Sie die Datei, und schließen Sie es.

2. In der **Quelldateien** Ordner öffnen Element "MFCD2DWalkthroughView.cpp". Im Konstruktor für die `CMFCD2DWalkthroughView` Klasse, fügen Sie Code hinzu:

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

   Speichern Sie die Datei, und schließen Sie es.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Der Pinsel mit Farbverlauf ändern, sodass es entsprechend beim Ändern des Fensters angepasst wird

1. Auf der **Projekt** Menü wählen **Klassen-Assistent**.

2. In der **MFC-Klassen-Assistent**unter **Klassenname**Option `CMFCD2DWalkthroughView`.

3. Auf der **Nachrichten** Registerkarte die **Nachrichten** wählen Sie im `WM_SIZE` und wählen Sie dann **Handler hinzufügen**. Mit dieser Aktion wird die `OnSize` Nachrichtenhandler, an die `CMFCD2DWalkthroughView` Klasse.

4. In der **vorhandene Handler** wählen Sie im `OnSize`. Wählen Sie **-Code bearbeiten** zum Anzeigen der `CMFCD2DWalkthroughView::OnSize` Methode. Fügen Sie am Ende der Methode den folgenden Code ein.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Speichern Sie die Datei, und schließen Sie es.

## <a name="to-implement-a-d2d-drawing-handler"></a>Zum Implementieren eines Zeichnung D2D-Handlers

1. Auf der **Projekt** Menü wählen **Klassen-Assistent**.

2. In der **MFC-Klassen-Assistent**unter **Klassenname**Option `CMFCD2DWalkthroughView`.

3. Auf der **Nachrichten** Registerkarte **benutzerdefinierte Meldung hinzufügen**.

4. In der **benutzerdefinierte Meldung hinzufügen** Dialogfeld die **benutzerdefinierte Windows-Meldung** geben `AFX_WM_DRAW2D`. In der **Handler Nachrichtenname** geben `OnDraw2D`. Wählen Sie die **registrierte Meldung** aus, und wählen Sie dann **OK**. Dieser Vorgang fügt einen Meldungshandler für die `AFX_WM_DRAW2D` -Meldung an das `CMFCD2DWalkthroughView` Klasse.

5. In der **vorhandene Handler** wählen Sie im `OnDraw2D`. Wählen Sie **-Code bearbeiten** zum Anzeigen der `CMFCD2DWalkthroughView::OnDraw2D` Methode. Verwenden Sie diesen Code für die `CMFCD2DWalkthroughView::OnDrawD2D` Methode:

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

   Speichern Sie die Datei, und schließen Sie es.

## <a name="to-verify-the-results"></a>Die Ergebnisse überprüfen

- Erstellen Sie die Anwendung, und führen Sie sie aus. Es muss ein Farbverlauf Rechteck verfügen, die beim Ändern der Größe des Fensters ändert. "Hello World!" sollte in der Mitte des Rechtecks angezeigt werden.

## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweisen](../mfc/walkthroughs-mfc.md)
