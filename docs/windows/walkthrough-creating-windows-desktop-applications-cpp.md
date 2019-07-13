---
title: 'Exemplarische Vorgehensweise: Erstellen Sie eine herkömmliche Windows-Desktop-Anwendung (C++)'
ms.custom: get-started-article
ms.date: 04/23/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 2cf9928d56c564edc0e3bda1935eb11004000985
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861123"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Exemplarische Vorgehensweise: Erstellen Sie eine herkömmliche Windows-Desktop-Anwendung (C++)

In dieser exemplarischen Vorgehensweise veranschaulicht erstellen Sie eine herkömmliche Windows-desktop-Anwendung in Visual Studio. Die beispielanwendung, die Sie erstellen mithilfe der Windows-API "Hello, Windows Desktop!" anzuzeigen. in einem Fenster anzeigt. Sie können den Code verwenden, den Sie in dieser exemplarischen Vorgehensweise als Muster entwickeln, um andere Windows-Desktopanwendungen zu erstellen.

Die Windows-API (auch bekannt als die Win32-API, Windows-Desktop-API und klassischen Windows-API) ist ein C#-Sprache basierenden Framework zum Erstellen von Windows-Anwendungen. Es wurde seit den 1980er und zum Erstellen von Windows-Anwendungen bereits seit Jahrzehnten verwendet wurde. Weitere erweiterte und einfacher-to-Program-Frameworks wurden erstellt, auf der Windows-API, wie MFC, ATL und der .NET Framework-Versionen. Sogar die meisten modernen Code für UWP und Store-apps, die in C++ geschriebene c++ / WinRT verwendet die Windows-API unter. Weitere Informationen über die Windows-API finden Sie unter [Windows-API-Index](/windows/desktop/apiindex/windows-api-list). Es gibt viele Möglichkeiten zum Erstellen von Windows-Anwendungen, aber die oben beschriebenen Prozess war der erste.

> [!IMPORTANT]
> Aus Gründen der Übersichtlichkeit werden einige codeanweisungen im Text weggelassen. Die [erstellen Sie den Code](#build-the-code) Abschnitt am Ende dieses Dokuments wird der vollständige Code gezeigt.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Ein Computer, auf dem Microsoft Windows 7 oder eine höhere Version ausgeführt wird. Für ein optimales Entwicklungserlebnis empfehlen wir Windows 10.

- Eine Kopie von Visual Studio. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen Sie sicher, dass die Workload **Desktopentwicklung mit C++** aktiviert ist. Machen Sie sich keine Sorgen, wenn Sie diese Workload beim Installieren von Visual Studio nicht installiert haben. Sie können das Installationsprogramm erneut ausführen und die Workload jetzt installieren.

   ![Desktopentwicklung mit C++](../build/media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Grundkenntnisse der Verwendung der Visual Studio-IDE. Wenn Sie bereits früher Windows-Desktop-Apps verwendet haben, dürften keine Verständnisprobleme auftreten. Eine Einführung finden Sie unter [Willkommen in der Visual Studio-IDE](/visualstudio/ide/visual-studio-ide).

- Grundlegende Kenntnisse der Programmiersprache C++. Keine Sorge: Wir verwenden keine allzu komplizierten Verfahren.

## <a name="create-a-windows-desktop-project"></a>Erstellen Sie ein Windows-desktop-Projekt

Um Ihre erste Windows-Desktopprojekt erstellen, und geben den Code für eine funktionierende Windows-Desktopanwendung, gehen Sie wie folgt vor. Stellen Sie sicher, dass die Auswahl für die Version in der oberen linken Ecke dieser Seite auf die richtige Version von Visual Studio festgelegt ist, die Sie verwenden.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Erstellen Sie ein Windows-desktop-Projekt in Visual Studio-2019

1. Klicken Sie im Hauptmenü auf **Datei** > **Neu** > **Projekt**, um das Dialogfeld **Neues Projekt erstellen** zu öffnen.

1. Legen Sie am oberen Rand des Dialogfelds, **Sprache** zu **C++** legen **Plattform** zu **Windows**, und legen Sie **Projekttyp** zu **Desktop**. 

1. Wählen Sie die gefilterte Liste der Projekttypen, **-Assistenten für Windows Desktop** wählen Sie dann **Weiter**. Klicken Sie in der nächsten Seite Geben Sie einen Namen für das Projekt, und geben Sie den Speicherort des Projekts ein, bei Bedarf.

1. Klicken Sie auf die Schaltfläche **Erstellen**, um das Projekt zu erstellen.

1. Die **-Projekt für Windows Desktop** Dialogfeld wird jetzt angezeigt. Klicken Sie unter **Anwendungstyp**Option **Windows-Anwendung (.exe)** . Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** zum Erstellen des Projekts.

1. In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesktopApp** Projekts **hinzufügen**, und wählen Sie dann **neues Element**.

   ![Neues Element hinzufügen, DesktopApp Projekt](../build/media/desktop-app-project-add-new-item-153.gif "neues Element hinzufügen, DesktopApp-Projekt")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . In der **Namen** geben einen Namen für die Datei, z. B. *HelloWindowsDesktop.cpp*. Wählen Sie **Hinzufügen** aus.

   ![Hinzufügen von cpp-Datei zu DesktopApp Projekt](../build/media/desktop-app-add-cpp-file-153.png "cpp-Datei zu DesktopApp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt und die Quelldatei wird im Editor geöffnet. Um den Vorgang fortzusetzen, fahren Sie mit [Erstellen des Codes](#create-the-code).

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Erstellen Sie ein Windows-desktop-Projekt in Visual Studio 2017

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. In der **neues Projekt** erweitern Sie im Dialogfeld im linken Bereich **installiert** > **Visual C++** , und wählen Sie dann **Windows Desktop**. Wählen Sie im mittleren Bereich **-Assistenten für Windows Desktop**.

   In der **Namen** geben einen Namen für das Projekt, z. B. *DesktopApp*. Klicken Sie auf **OK**.

   ![Nennen Sie das Projekt DesktopApp](../build/media/desktop-app-new-project-name-153.png "DesktopApp Projektnamen")

1. In der **-Projekt für Windows Desktop** Dialogfeld unter **Anwendungstyp**Option **Windows-Anwendung (.exe)** . Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** zum Erstellen des Projekts.

   ![Erstellen Sie im Assistenten für Windows-Desktopprojekt DesktopApp](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp im Assistenten für Windows-Desktopprojekt erstellen")

1. In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesktopApp** Projekts **hinzufügen**, und wählen Sie dann **neues Element**.

   ![Neues Element hinzufügen, DesktopApp Projekt](../build/media/desktop-app-project-add-new-item-153.gif "neues Element hinzufügen, DesktopApp-Projekt")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . In der **Namen** geben einen Namen für die Datei, z. B. *HelloWindowsDesktop.cpp*. Wählen Sie **Hinzufügen** aus.

   ![Hinzufügen von cpp-Datei zu DesktopApp Projekt](../build/media/desktop-app-add-cpp-file-153.png "cpp-Datei zu DesktopApp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt und die Quelldatei wird im Editor geöffnet. Um den Vorgang fortzusetzen, fahren Sie mit [Erstellen des Codes](#create-the-code).

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Erstellen Sie ein Windows-desktop-Projekt in Visual Studio 2015

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. In der **neues Projekt** erweitern Sie im Dialogfeld im linken Bereich **installiert** > **Vorlagen** > **Visual C++** , und wählen Sie dann **Win32**. Wählen Sie im mittleren Bereich **Win32-Projekt**aus.

   In der **Namen** geben einen Namen für das Projekt, z. B. *DesktopApp*. Klicken Sie auf **OK**.

   ![Nennen Sie das Projekt DesktopApp](../build/media/desktop-app-new-project-name-150.png "DesktopApp Projektnamen")

1. Auf der **Übersicht** auf der Seite die **Win32-Anwendungsassistenten**, wählen Sie **Weiter**.

   ![DesktopApp in Übersicht über die Win32-Anwendung-Assistenten erstellen](../build/media/desktop-app-win32-wizard-overview-150.png "erstellen DesktopApp in Win32-Anwendung-Assistenten (Übersicht)")

1. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **Windows-Anwendung**. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **Fertig stellen** zum Erstellen des Projekts.

   ![DesktopApp in Win32-Assistenten Anwendungseinstellungen erstellen](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp in Win32-Anwendungseinstellungen-Assistenten erstellen")

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt DesktopApp, wählen Sie **hinzufügen**, und wählen Sie dann **neues Element**.

   ![Neues Element hinzufügen, DesktopApp Projekt](../build/media/desktop-app-project-add-new-item-150.gif "neues Element hinzufügen, DesktopApp-Projekt")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)** . In der **Namen** geben einen Namen für die Datei, z. B. *HelloWindowsDesktop.cpp*. Wählen Sie **Hinzufügen** aus.

   ![Hinzufügen von cpp-Datei zu DesktopApp Projekt](../build/media/desktop-app-add-cpp-file-150.png "cpp-Datei zu DesktopApp-Projekt hinzufügen")

Das Projekt wird jetzt erstellt und die Quelldatei wird im Editor geöffnet.

::: moniker-end

## <a name="create-the-code"></a>Erstellen des Codes

Als Nächstes erfahren Sie, wie Sie den Code für eine Windows-desktop-Anwendung in Visual Studio zu erstellen.

### <a name="to-start-a-windows-desktop-application"></a>So beginnen Sie eine Windows-Desktopanwendung

1. Ebenso wie jede C- und C++-Anwendung müssen ein `main` fungieren als Ausgangspunkt erforderlich, jede Windows-Desktopanwendung benötigen eine `WinMain` Funktion. `WinMain` besitzt die folgende Syntax.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Weitere Informationen zu den Parametern und Rückgabewerten dieser Funktion finden Sie unter [WinMain-Einstiegspunkt](/windows/desktop/api/winbase/nf-winbase-winmain).

   > [!NOTE]
   > Was alle diese zusätzlichen Wörter sind, z. B. `CALLBACK`, oder `HINSTANCE`, oder `_In_`? Die herkömmliche Windows-API verwendet die Typdefinitionen und Präprozessormakros umfassend zu abstrahieren Details der Typen und plattformspezifischen code zu, z. B. Aufrufkonventionen, **__declspec** Deklarationen und compilerpragmen. In Visual Studio können Sie IntelliSense [Quick Info](/visualstudio/ide/using-intellisense#quick-info) Funktion, um festzustellen, welche dieser Typdefinitionen und Makros definiert. Zeigen Sie die Maus auf das Wort von Interesse sind, oder wählen Sie ihn aus, und drücken Sie **STRG**+**K**, **STRG**+**ich** für eine kleines Popupfenster, das die Definition enthält. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense). Parameter und Rückgabetypen verwenden häufig *SAL-Anmerkungen* können Sie Catch Programmierfehler. Weitere Informationen finden Sie unter [Verwenden von SAL-Anmerkungen zum Reduzieren von C/C++-Codefehlern](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Windows-desktop-Programme erfordern &lt;windows.h >. &lt;TCHAR.h > definiert die `TCHAR` Makro, das letzten Endes löst, **"wchar_t"** Wenn das UNICODE-Symbol in Ihrem Projekt definiert ist, andernfalls löst **Char**.  Wenn Sie immer mit Unicode-aktiviert erstellen, ist Sie nicht, benötigen Sie TCHAR und können nur **"wchar_t"** direkt.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Neben der `WinMain` -Funktion muss jede Windows-Desktopanwendung auch über eine Fensterprozedurfunktion verfügen. Diese Funktion ist in der Regel mit dem Namen `WndProc` , aber Sie können sie einen beliebigen Namen. `WndProc` besitzt die folgende Syntax.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   In dieser Funktion, die Sie schreiben Code zum Behandeln von *Nachrichten* , die die Anwendung empfängt von Windows beim *Ereignisse* auftreten. Beispielsweise wenn ein Benutzer die Schaltfläche "OK" in Ihrer Anwendung auswählt, sendet Windows eine Nachricht an Sie und können Sie Code in schreiben Ihre `WndProc` Funktion, die ausführt, beliebige Aufgaben geeignet ist. Es heißt *behandeln* ein Ereignis. Sie behandeln, nur die Ereignisse, die für Ihre Anwendung relevant sind.

   Weitere Informationen finden Sie unter [Window Procedures](/windows/desktop/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>So fügen Sie der WinMain-Funktion Funktionen hinzu

1. In der `WinMain` -Funktion, füllen Sie eine Struktur des Typs [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa). Die Struktur enthält Informationen über das Fenster, z. B. das Anwendungssymbol, die Hintergrundfarbe des Fensters, den Namen in der Titelleiste und vor allem einen Funktionszeiger, der Fensterprozedur anzeigen. Das folgende Beispiel zeigt eine typische `WNDCLASSEX` -Struktur.

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

   Weitere Informationen zu den Feldern der oben genannten-Struktur, finden Sie unter [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa).

1. Registrieren der `WNDCLASSEX` mit Windows, damit das Fenster "und" Gewusst wie: Senden von Nachrichten an sie, dass die It kennt. Verwenden Sie die [RegisterClassEx](/windows/desktop/api/winuser/nf-winuser-registerclassexa) -Funktion, und übergeben Sie die Fensterklassenstruktur als Argument. Die `_T` Makro wird verwendet, da wir verwenden die `TCHAR` Typ.

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

1. Sie können nun ein Fenster erstellen. Verwenden Sie die [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) -Funktion.

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

   Diese Funktion gibt ein `HWND`, dies ist ein Handle für ein Fenster. Ein Handle ist etwas wie ein Zeiger, die Windows verwendet, um zu verfolgen geöffneten Fenster. Weitere Informationen finden Sie unter [Windows-Datentypen](/windows/desktop/WinProg/windows-data-types).

1. An diesem Punkt wird das Fenster erstellt wurde, aber wir müssen noch mitteilen von Windows, um es sichtbar zu machen. Das ist die Funktionsweise dieses Codes:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Das angezeigte Fenster nicht viel Inhalt aufweisen, da Sie noch nicht implementiert haben die `WndProc` Funktion. Das heißt, ist nicht die Anwendung noch die verarbeiten Nachrichten, die Windows jetzt an ihn sendet.

1. Um die Nachrichten zu verarbeiten, fügen wir zunächst eine Meldungsschleife zum Lauschen auf Nachrichten, die Windows sendet hinzu. Wenn die Anwendung eine Nachricht empfängt, diese Schleife verteilt, damit Ihre `WndProc` Funktion behandelt werden. Die Nachrichtenschleife ähnelt dem folgenden Code.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Weitere Informationen über die in der Nachrichtenschleife verwendeten Strukturen und Funktionen finden Sie unter [MSG](/windows/desktop/api/winuser/ns-winuser-msg), [GetMessage](/windows/desktop/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).

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

   Eine wichtige Meldung verarbeiten wird die [WM_PAINT](/windows/desktop/gdi/wm-paint) Nachricht. Die Anwendung empfängt die `WM_PAINT` Nachricht als Teil der angezeigten Fenster aktualisiert werden muss. Das Ereignis kann auftreten, wenn ein Benutzer ein Fenster vor das Fenster verschiebt, dann verschiebt Sie es noch mal weg, und Ihre Anwendung weiß nicht, wenn diese Ereignisse auftreten. Nur Windows bekannt ist, damit Sie mit benachrichtigt `WM_PAINT`. Wenn das Fenster erstmals angezeigt wird, müssen alle Daten aktualisiert werden.

   Rufen Sie zur Behandlung einer `WM_PAINT` -Nachricht zuerst [BeginPaint](/windows/desktop/api/winuser/nf-winuser-beginpaint)auf, behandeln Sie anschließend die gesamte Logik, um das Layout von Text, Schaltflächen und anderen Steuerelementen im Fenster zu behandeln, und rufen Sie anschließend [EndPaint](/windows/desktop/api/winuser/nf-winuser-endpaint)auf. Ist für die Anwendung die Logik zwischen dem Anfangs- und dem Beendigungsanruf zur Anzeige der Zeichenfolge "Hello, Windows Desktop!" im Fenster. Im folgenden Code wird die [TextOut](/windows/desktop/api/wingdi/nf-wingdi-textouta) -Funktion zur Anzeige der Zeichenfolge verwendet.

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

   `HDC` im Code ist ein Handle für einen Gerätekontext, eine Datenstruktur, die Windows verwendet, um Ihre Anwendung für die Kommunikation mit dem grafiksubsystem zu ermöglichen. Die `BeginPaint` und `EndPaint` Funktionen die Anwendung verhalten sich wie ein "guter Bürger", und verwenden Sie den Gerätekontext nicht länger als notwendig zu. Die Funktionen Hilfe stellen die grafiksubsystem ist für die Verwendung durch andere Anwendungen verfügbar.

1. Eine Anwendung behandelt normalerweise viele andere Meldungen, z. B. [WM_CREATE](/windows/desktop/winmsg/wm-create) , wenn ein Fenster erstellt wird, und [WM_DESTROY](/windows/desktop/winmsg/wm-destroy) Wenn das Fenster geschlossen wird. Der folgende Code zeigt eine grundlegende, jedoch vollständige `WndProc` -Funktion.

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

## <a name="build-the-code"></a>Erstellen Sie den code

Wie versprochen, ist hier der vollständige Code für die Anwendung aus.

### <a name="to-build-this-example"></a>So erstellen Sie dieses Beispiel

1. Löschen Sie Sie, im eingegeben haben Code *HelloWindowsDesktop.cpp* im Editor. Dieser Beispielcode kopieren und fügen Sie ihn in *HelloWindowsDesktop.cpp*:

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

1. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen**. Die Ergebnisse der Kompilierung sollte angezeigt werden, der **Ausgabe** Fenster in Visual Studio.

   ![Erstellen Sie das Projekt DesktopApp](../build/media/desktop-app-project-build-150.gif "erstellen Sie das Projekt DesktopApp")

1. Um die Anwendung auszuführen, drücken Sie die **F5**. Ein Fenster mit dem Text "Hello, Windows Desktop!" sollte in der oberen linken Ecke der Anzeige angezeigt werden.

   ![Führen Sie das Projekt DesktopApp](../build/media/desktop-app-project-run-157.PNG "führen Sie das Projekt DesktopApp")

Herzlichen Glückwunsch! Sie haben diese exemplarische Vorgehensweise abgeschlossen und erstellt eine herkömmliche Windows-Desktopanwendung.

## <a name="see-also"></a>Siehe auch

[Windows-Desktop-Anwendungen](../windows/windows-desktop-applications-cpp.md)
