---
title: 'Exemplarische Vorgehensweise: Erstellen einer herkömmlichen Windows-Desktop AnwendungC++()'
ms.custom: get-started-article
ms.date: 04/23/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 8bc2a42c5a9006065e2f0f4ecb70911e0055823e
ms.sourcegitcommit: bf724dfc639b16d5410fab72183f8e6b781338bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71062071"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Exemplarische Vorgehensweise: Erstellen einer herkömmlichen Windows-Desktop AnwendungC++()

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie eine herkömmliche Windows-Desktop Anwendung in Visual Studio erstellen. Die Beispielanwendung, die Sie erstellen, verwendet die Windows-API, um "Hello, Windows Desktop!" anzuzeigen. in einem Fenster anzeigt. Sie können den Code verwenden, den Sie in dieser exemplarischen Vorgehensweise als Muster entwickeln, um andere Windows-Desktopanwendungen zu erstellen.

Die Windows-API (auch als Win32-API, Windows-Desktop-API und Windows-Classic API bezeichnet) ist ein auf C-Sprache basierendes Framework zum Erstellen von Windows-Anwendungen. Es war seit den 80er Jahren vorhanden und wurde zum Erstellen von Windows-Anwendungen seit Jahrzehnten verwendet. Erweiterte und leichter zu Programmende Frameworks wurden auf der Windows-API erstellt, z. b. MFC, ATL und .NET-Frameworks. Auch der modernste Code für UWP-und Store-Apps C++, die in/WinRT geschrieben wurden, verwendet die Windows-API unterhalb von. Weitere Informationen zur Windows-API finden Sie unter [Windows-API-Index](/windows/win32/apiindex/windows-api-list). Es gibt viele Möglichkeiten, Windows-Anwendungen zu erstellen, aber der obige Prozess war der erste.

> [!IMPORTANT]
> Aus Gründen der Übersichtlichkeit werden einige Code Anweisungen im Text ausgelassen. Der Abschnitt [Build the Code](#build-the-code) am Ende dieses Dokuments zeigt den gesamten Code.

## <a name="prerequisites"></a>Vorraussetzungen

- Ein Computer, auf dem Microsoft Windows 7 oder eine höhere Version ausgeführt wird. Für ein optimales Entwicklungserlebnis empfehlen wir Windows 10.

- Eine Kopie von Visual Studio. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen Sie sicher, dass die Workload **Desktopentwicklung mit C++** aktiviert ist. Machen Sie sich keine Sorgen, wenn Sie diese Workload beim Installieren von Visual Studio nicht installiert haben. Sie können das Installationsprogramm erneut ausführen und die Workload jetzt installieren.

   ![Desktopentwicklung mit C++](../build/media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Grundkenntnisse der Verwendung der Visual Studio-IDE. Wenn Sie bereits früher Windows-Desktop-Apps verwendet haben, dürften keine Verständnisprobleme auftreten. Eine Einführung finden Sie unter [Willkommen in der Visual Studio-IDE](/visualstudio/ide/visual-studio-ide).

- Grundlegende Kenntnisse der Programmiersprache C++. Keine Sorge: Wir verwenden keine allzu komplizierten Verfahren.

## <a name="create-a-windows-desktop-project"></a>Erstellen eines Windows-Desktop Projekts

Führen Sie die folgenden Schritte aus, um Ihr erstes Windows-Desktop Projekt zu erstellen und den Code für eine funktionierende Windows-Desktop Anwendung einzugeben. Stellen Sie sicher, dass die Versions Auswahl in der linken oberen Ecke dieser Seite auf die richtige Version von Visual Studio festgelegt ist, die Sie verwenden.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>So erstellen Sie ein Windows-Desktop Projekt in Visual Studio 2019

1. Klicken Sie im Hauptmenü auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

1. Legen Sie am oberen Rand des Dialog Felds **Sprache** auf **C++** fest, legen Sie **Platform** auf **Windows**fest, und legen Sie **Projekttyp** auf **Desktop**fest. 

1. Wählen Sie in der gefilterten Liste der Projekttypen die Option **Windows-Desktop-Assistent** und dann **weiter**aus. Geben Sie auf der nächsten Seite einen Namen für das Projekt ein, und geben Sie den Speicherort des Projekts an, wenn dies gewünscht ist.

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Projekt zu erstellen.

1. Das Dialogfeld **Windows-Desktop Projekt** wird jetzt angezeigt. Wählen Sie unter **Anwendungstyp**die Option **Windows-Anwendung (. exe)** aus. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** aus, um das Projekt zu erstellen.

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **desktopapp** , wählen Sie **Hinzufügen**aus, und wählen Sie dann **Neues Element**aus.

   ![Neues Element zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-project-add-new-item-153.gif "Neues Element zum desktopapp-Projekt hinzufügen")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . Geben Sie im Feld **Name** einen Namen für die Datei ein, z. b. *hellowindowsdesktop. cpp*. Wählen Sie **Hinzufügen** aus.

   ![Cpp-Datei zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-add-cpp-file-153.png "Cpp-Datei zum desktopapp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt, und die Quelldatei wird im Editor geöffnet. Fahren Sie fort, indem Sie [den Code erstellen](#create-the-code).

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>So erstellen Sie ein Windows-Desktop Projekt in Visual Studio 2017

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich die Option **installiertes** > **visuelles C++** Element, und wählen Sie dann **Windows-Desktop**aus. Wählen Sie im mittleren Bereich die Option **Windows-Desktop-Assistent**aus.

   Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. b. *desktopapp*. Klicken Sie auf **OK**.

   ![Benennen des desktopapp-Projekts](../build/media/desktop-app-new-project-name-153.png "Benennen des desktopapp-Projekts")

1. Wählen Sie im Dialogfeld **Windows-Desktop Projekt** unter **Anwendungstyp**die Option **Windows-Anwendung (. exe)** aus. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** aus, um das Projekt zu erstellen.

   ![Assistent zum Erstellen von desktopapp-Projekten in Windows-Desktop Projekten](../build/media/desktop-app-new-project-wizard-153.png "Assistent zum Erstellen von desktopapp-Projekten in Windows-Desktop Projekten")

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **desktopapp** , wählen Sie **Hinzufügen**aus, und wählen Sie dann **Neues Element**aus.

   ![Neues Element zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-project-add-new-item-153.gif "Neues Element zum desktopapp-Projekt hinzufügen")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . Geben Sie im Feld **Name** einen Namen für die Datei ein, z. b. *hellowindowsdesktop. cpp*. Wählen Sie **Hinzufügen** aus.

   ![Cpp-Datei zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-add-cpp-file-153.png "Cpp-Datei zum desktopapp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt, und die Quelldatei wird im Editor geöffnet. Fahren Sie fort, indem Sie [den Code erstellen](#create-the-code).

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>So erstellen Sie ein Windows-Desktop Projekt in Visual Studio 2015

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neues Projekt** im linken Bereich **installierte** > **Vorlagen** > **Visualisierung C++** , und wählen Sie dann **Win32**aus. Wählen Sie im mittleren Bereich **Win32-Projekt**aus.

   Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. b. *desktopapp*. Klicken Sie auf **OK**.

   ![Benennen des desktopapp-Projekts](../build/media/desktop-app-new-project-name-150.png "Benennen des desktopapp-Projekts")

1. Wählen Sie auf der Seite **Übersicht** des **Win32-Anwendungs-Assistenten**die Option **weiter**aus.

   ![Übersicht über das Erstellen von Desktop-Apps im Win32-Anwendungs-Assistenten](../build/media/desktop-app-win32-wizard-overview-150.png "Übersicht über das Erstellen von Desktop-Apps im Win32-Anwendungs-Assistenten")

1. Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp**die Option **Windows-Anwendung**aus. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **Fertig** stellen aus, um das Projekt zu erstellen.

   ![Erstellen von desktopapp-Einstellungen im Win32-Anwendungs-Assistenten](../build/media/desktop-app-win32-wizard-settings-150.png "Erstellen von desktopapp-Einstellungen im Win32-Anwendungs-Assistenten")

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt desktopapp, wählen Sie **Hinzufügen**aus, und wählen Sie dann **Neues Element**aus.

   ![Neues Element zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-project-add-new-item-150.gif "Neues Element zum desktopapp-Projekt hinzufügen")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . Geben Sie im Feld **Name** einen Namen für die Datei ein, z. b. *hellowindowsdesktop. cpp*. Wählen Sie **Hinzufügen** aus.

   ![Cpp-Datei zum desktopapp-Projekt hinzufügen](../build/media/desktop-app-add-cpp-file-150.png "Cpp-Datei zum desktopapp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt, und die Quelldatei wird im Editor geöffnet.

::: moniker-end

## <a name="create-the-code"></a>Erstellen des Codes

Als Nächstes erfahren Sie, wie Sie den Code für eine Windows-Desktop Anwendung in Visual Studio erstellen.

### <a name="to-start-a-windows-desktop-application"></a>So beginnen Sie eine Windows-Desktopanwendung

1. Ebenso wie jede C-Anwendung C++ und jede Anwendung eine `main` Funktion als Ausgangspunkt aufweisen muss, muss jede Windows-Desktop Anwendung `WinMain` über eine-Funktion verfügen. `WinMain` besitzt die folgende Syntax.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Informationen zu den Parametern und Rückgabe Werten dieser Funktion finden Sie unter [WinMain Entry Point](/windows/win32/api/winbase/nf-winbase-winmain).

   > [!NOTE]
   > Was sind diese zusätzlichen Wörter, wie z `CALLBACK`. b., oder? `HINSTANCE` `_In_` Die herkömmliche Windows-API verwendet häufig Typedefs-und Präprozessormakros, um einige Details von Typen und Platt Form spezifischem Code, wie z. b. Aufruf Konventionen, **__declspec** -Deklarationen und compilerpragmas, zu abstrahieren. In Visual Studio können Sie die Funktion "IntelliSense [Quick Info](/visualstudio/ide/using-intellisense#quick-info) " verwenden, um zu sehen, was diese Typedefs und Makros definieren. Zeigen Sie mit der Maus auf das gewünschte Wort, oder wählen Sie es aus, und drücken Sie **STRG**+**K**, **STRG**+**I** für ein kleines Popup Fenster, das die Definition enthält. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense). Parameter und Rückgabe Typen verwenden oftmals *SAL* -Anmerkungen, um Programmierfehler zu erfassen. Weitere Informationen finden Sie unter [Verwenden von Sal-Anmerkungen zum Reduzieren vonC++ C/Code-Fehlern](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Für Windows-Desktop &lt;Programme ist Windows. h > erforderlich. &lt;Tchar. h > definiert das `TCHAR` Makro, das letztendlich in **wchar_t** aufgelöst wird, wenn das Unicode-Symbol im Projekt definiert ist. andernfalls wird es in **char**aufgelöst.  Wenn Sie immer mit aktiviertem Unicode erstellen, benötigen Sie keinen TCHAR und können **wchar_t** einfach direkt verwenden.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Neben der `WinMain` -Funktion muss jede Windows-Desktopanwendung auch über eine Fensterprozedurfunktion verfügen. Diese Funktion wird normalerweise `WndProc` benannt, Sie können Sie aber beliebig benennen. `WndProc` besitzt die folgende Syntax.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   In dieser Funktion schreiben Sie Code zum Verarbeiten von *Nachrichten* , die von Windows bei Auftreten von *Ereignissen* von Windows empfangen werden. Wenn ein Benutzer beispielsweise eine OK-Schaltfläche in der Anwendung auswählt, sendet Windows eine Meldung an Sie, und Sie können Code in `WndProc` ihrer Funktion schreiben, der die entsprechenden Aufgaben erledigt. Sie wird als *Behandlung* eines Ereignisses bezeichnet. Die Ereignisse, die für Ihre Anwendung relevant sind, werden nur behandelt.

   Weitere Informationen finden Sie unter [Window Procedures](/windows/win32/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>So fügen Sie der WinMain-Funktion Funktionen hinzu

1. In der `WinMain` -Funktion füllen Sie eine Struktur des Typs [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw). Die Struktur enthält Informationen zum Fenster, z. b. das Anwendungssymbol, die Hintergrundfarbe des Fensters, den Namen, der in der Titelleiste angezeigt werden soll, und wichtig, einen Funktionszeiger auf die Fenster Prozedur. Das folgende Beispiel zeigt eine typische `WNDCLASSEX` -Struktur.

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   Weitere Informationen zu den Feldern der obigen Struktur finden Sie unter [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw).

1. Registrieren Sie `WNDCLASSEX` die bei Windows, damit Sie über Ihr Fenster informiert ist und wie Sie Nachrichten an das Fenster senden können. Verwenden Sie die [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) -Funktion, und übergeben Sie die Fensterklassenstruktur als Argument. Das `_T` -Makro wird verwendet, da der `TCHAR` -Typ verwendet wird.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. Sie können nun ein Fenster erstellen. Verwenden Sie die [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) -Funktion.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   Diese Funktion gibt einen `HWND`zurück, der ein Handle für ein Fenster ist. Ein Handle ähnelt einem Zeiger, den Windows verwendet, um geöffnete Fenster nachzuverfolgen. Weitere Informationen finden Sie unter [Windows-Datentypen](/windows/win32/WinProg/windows-data-types).

1. An diesem Punkt wurde das Fenster erstellt, aber wir müssen Windows darauf hinweisen, das Fenster sichtbar zu machen. Dies ist der folgende Code:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Das angezeigte Fenster hat nicht viel Inhalt, weil Sie die `WndProc` Funktion noch nicht implementiert haben. Anders ausgedrückt: die Anwendung verarbeitet die Nachrichten, die von Windows jetzt gesendet werden, noch nicht.

1. Zum Verarbeiten der Nachrichten fügen wir zuerst eine Nachrichten Schleife hinzu, um auf die von Windows gesendeten Nachrichten zu lauschen. Wenn die Anwendung eine Nachricht empfängt, sendet diese Schleife Sie an die `WndProc` Funktion, die behandelt werden soll. Die Nachrichtenschleife ähnelt dem folgenden Code.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Weitere Informationen über die in der Nachrichtenschleife verwendeten Strukturen und Funktionen finden Sie unter [MSG](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).

   An diesem Punkt sollte die `WinMain` -Funktion in etwa dem folgenden Code entsprechen.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>So fügen Sie der WndProc-Funktion Funktionen hinzu

1. Damit die `WndProc` -Funktion die Nachrichten behandeln kann, die von der Anwendung empfangen werden, implementieren Sie eine switch-Anweisung.

   Eine wichtige zu behandelnde Nachricht ist die [WM_PAINT](/windows/win32/gdi/wm-paint) -Nachricht. Die Anwendung empfängt die `WM_PAINT` Meldung, wenn ein Teil des angezeigten Fensters aktualisiert werden muss. Das Ereignis kann auftreten, wenn ein Benutzer ein Fenster vor dem Fenster bewegt, es dann wieder entfernt und die Anwendung nicht weiß, wann diese Ereignisse auftreten. Nur Windows weiß, damit Sie `WM_PAINT`benachrichtigt werden. Wenn das Fenster zum ersten Mal angezeigt wird, müssen alle Updates aktualisiert werden.

   Rufen Sie zur Behandlung einer `WM_PAINT` -Nachricht zuerst [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint)auf, behandeln Sie anschließend die gesamte Logik, um das Layout von Text, Schaltflächen und anderen Steuerelementen im Fenster zu behandeln, und rufen Sie anschließend [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint)auf. Bei der Anwendung besteht die Logik zwischen dem Anfangs-und dem Endbefehl in der Anzeige der Zeichenfolge "Hello, Windows Desktop!". im Fenster. Im folgenden Code wird die [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) -Funktion zur Anzeige der Zeichenfolge verwendet.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC`im Code ist ein Handle für einen Gerätekontext, bei dem es sich um eine Datenstruktur handelt, die Windows verwendet, um Ihre Anwendung für die Kommunikation mit dem Grafik Subsystem zu aktivieren. Die `BeginPaint` - `EndPaint` Funktion und die-Funktion sorgen dafür, dass sich Ihre Anwendung wie ein guter Bürger verhält, und verwendet den Gerätekontext nicht länger als erforderlich. Die Funktionen helfen, das Grafik Subsystem zur Verwendung durch andere Anwendungen verfügbar zu machen.

1. Eine Anwendung verarbeitet in der Regel viele andere Nachrichten, z. b. [WM_CREATE](/windows/win32/winmsg/wm-create) , wenn ein Fenster erstmalig erstellt wird, und [WM_DESTROY](/windows/win32/winmsg/wm-destroy) , wenn das Fenster geschlossen wird. Der folgende Code zeigt eine grundlegende, jedoch vollständige `WndProc` -Funktion.

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>Erstellen des Codes

Wie bereits versprochen, ist hier der gesamte Code für die funktionierende Anwendung aufgeführt.

### <a name="to-build-this-example"></a>So erstellen Sie dieses Beispiel

1. Löschen Sie den Code, den Sie in " *hellowindowsdesktop. cpp* " im Editor eingegeben haben. Kopieren Sie den folgenden Beispielcode, und fügen Sie ihn in " *hellowindowsdesktop. cpp*" ein:

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen**. Die Ergebnisse der Kompilierung sollten im Fenster **Ausgabe** in Visual Studio angezeigt werden.

   ![Erstellen des desktopapp-Projekts](../build/media/desktop-app-project-build-150.gif "Erstellen des desktopapp-Projekts")

1. Drücken Sie **F5**, um die Anwendung auszuführen. Ein Fenster, das den Text "Hello, Windows Desktop!" enthält. sollte in der oberen linken Ecke der Anzeige angezeigt werden.

   ![Ausführen des desktopapp-Projekts](../build/media/desktop-app-project-run-157.PNG "Ausführen des desktopapp-Projekts")

Herzlichen Glückwunsch! Sie haben diese exemplarische Vorgehensweise abgeschlossen und eine herkömmliche Windows-Desktop Anwendung erstellt.

## <a name="see-also"></a>Siehe auch

[Windows-Desktop Anwendungen](../windows/windows-desktop-applications-cpp.md)
