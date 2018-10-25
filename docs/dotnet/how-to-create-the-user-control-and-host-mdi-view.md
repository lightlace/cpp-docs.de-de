---
title: 'Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten MDI-Ansicht | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms Controls
- Windows Forms [C++], MFC support
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2e61a69661034fb582039c744c3483f461405581
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056970"
---
# <a name="how-to-create-the-user-control-and-host-mdi-view"></a>Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI-Ansicht

In den folgenden Schritten wird das Erstellen eines .NET Framework-Benutzersteuerelements und das Erstellen des Steuerelements in einer Steuerelementklassenbibliothek (speziell in einem Projekt einer Windows-Steuerelementbibliothek) sowie das Kompilieren des Projekts in eine Assembly veranschaulicht. Das Steuerelement kann dann verwendet werden, aus einer MFC_Anwendung, die von abgeleitete Klassen verwendet [CView-Klasse](../mfc/reference/cview-class.md) und [CWinFormsView-Klasse](../mfc/reference/cwinformsview-class.md).

Informationen zum Erstellen eines Windows Forms-Benutzersteuerelements und eine Steuerelementklassenbibliothek erstellen, finden Sie unter [Vorgehensweise: Erstellen von Benutzersteuerelementen](/dotnet/framework/winforms/controls/how-to-author-composite-controls).

> [!NOTE]
>  In einigen Fällen verhalten sich Windows Forms-Steuerelemente, z. B. ein Datenblattsteuerelement eines Drittanbieters, nicht zuverlässig, wenn sie in einer MFC-Anwendung gehostet werden. Um dies zu umgehen, wird empfohlen, ein Windows Forms-Benutzersteuerelement in der MFC-Anwendung und das Datenblattsteuerelement des Drittanbieters innerhalb des Benutzersteuerelements zu platzieren.

Dieses Verfahren setzt voraus, dass Sie ein Windows Forms-Steuerelementbibliothek-Projekt mit dem Namen WindowsFormsControlLibrary1 wie in der Vorgehensweise in erstellt [Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

### <a name="to-create-the-mfc-host-application"></a>So erstellen Sie die MFC-Hostanwendung

1. Erstellen Sie ein MFC-Anwendungsprojekt.

   Auf der **Datei** , wählen Sie im Menü **neu**, und klicken Sie dann auf **Projekt**. In der **Visual C++** Ordner **MFC-Anwendung**.

   In der **Namen** Geben Sie `MFC02` , und ändern Sie die **Lösung** auf **zu Projektmappe hinzufügen**. Klicken Sie auf **OK**.

   In der **MFS-Anwendungsassistenten**, übernehmen Sie alle Standardeinstellungen, und klicken Sie dann auf **Fertig stellen**. Dies erstellt eine MFC-Anwendung mit einem MDI (Multiple Document Interface).

1. Konfigurieren Sie das Projekt für Common Language Runtime (CLR)-Unterstützung.

   In **Projektmappen-Explorer**, mit der rechten Maustaste die `MFC01` Projektknoten, und wählen Sie **Eigenschaften** aus dem Kontextmenü. Die **Eigenschaftenseiten** Dialogfeld wird angezeigt.

   Klicken Sie unter **Konfigurationseigenschaften**Option **allgemeine**. Unter den **Projektstandards** legen **Common Language Runtime-Unterstützung** zu **Common Language Runtime-Unterstützung (/ Clr)**.

   Klicken Sie unter **Konfigurationseigenschaften**, erweitern Sie **C/C++-** , und klicken Sie auf die **allgemeine** Knoten. Legen Sie **Debuginformationsformat** zu **Programmdatenbank (/ Zi)**.

   Klicken Sie auf die **Codegenerierung** Knoten. Legen Sie **minimale Neuerstellung aktivieren** zu **No (/ GM-)**. Legen Sie auch **vollständige Laufzeitüberprüfungen** zu **Standard**.

   Klicken Sie auf **OK** zum Übernehmen der Änderungen.

1. Fügen Sie in der Datei "stdafx.h" die folgende Zeile hinzu.

    ```
    #using <System.Windows.Forms.dll>
    ```

1. Fügen Sie dem .NET-Steuerelement einen Verweis hinzu.

   In **Projektmappen-Explorer**, mit der rechten Maustaste die `MFC02` Projektknoten, und wählen Sie **hinzufügen**, **Verweise**. In der **Eigenschaftenseite**, klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie WindowsFormsControlLibrary1 (unter der **Projekte** Registerkarte), und klicken Sie auf **OK** . Dies fügt einen Verweis in Form einer [/FU](../build/reference/fu-name-forced-hash-using-file.md) -Compileroption, damit das Programm kompiliert wird, kopiert es auch "WindowsFormsControlLibrary1.dll" in der `MFC02` Projektverzeichnis, damit das Programm ausgeführt wird.

1. Suchen Sie in stdafx.h folgende Zeile:

    ```
    #endif // _AFX_NO_AFXCMN_SUPPORT
    ```

   Fügen Sie davor folgende Zeilen ein:

    ```
    #include <afxwinforms.h>   // MFC Windows Forms support
    ```

1. Ändern Sie die View-Klasse, sodass es erbt [CWinFormsView](../mfc/reference/cwinformsview-class.md).

   Ersetzen Sie in MFC02View.h [CView](../mfc/reference/cview-class.md) mit [CWinFormsView](../mfc/reference/cwinformsview-class.md) , damit der Code wie folgt aussieht:

    ```
    class CMFC02View : public CWinFormsView
    {
    };
    ```

   Wenn Sie zusätzliche Ansichten der MDI-Anwendung hinzufügen möchten, müssen Sie zum Aufrufen [CWinApp:: AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) für jede Ansicht, die Sie erstellen.

1. Ändern Sie in der Datei MFC02View.cpp im IMPLEMENT_DYNCREATE-Makro und in der Meldungszuordnung CView in CWinFormsView um, und ersetzen Sie den vorhandenen leeren Konstruktor durch den folgenden:

    ```
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)

    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)
    {
    }
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)
    //leave existing body as is
    END_MESSAGE_MAP()
    ```

1. Erstellen Sie das Projekt, und führen Sie es aus.

   In **Projektmappen-Explorer**mit der rechten Maustaste auf MFC02, und wählen Sie **als Startprojekt festlegen**.

   Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

   Auf der **Debuggen** Menü klicken Sie auf **Starten ohne debugging**.

## <a name="see-also"></a>Siehe auch

[Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)