---
title: "Exemplarische Vorgehensweise: Erstellen einer herkömmliche Windows-Desktop-Anwendung (C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/09/2017
ms.reviewer: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.assetid: a247a9af-aff1-4899-9577-5f8104a0afbb
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25919c70d1a2ffffb350a0ec3c97b429d6d5ac66
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Exemplarische Vorgehensweise: Erstellen einer herkömmlichen Windows-Desktop-Anwendung (C++)

In dieser exemplarischen Vorgehensweise wird gezeigt, wie eine herkömmliche Windows-desktop-Anwendung in Visual Studio zu erstellen. Erstellen Sie nun bei der beispielanwendung verwendet die Windows-API "Hello, Windows-Desktop!" angezeigt in einem Fenster anzeigt. Sie können den Code verwenden, den Sie in dieser exemplarischen Vorgehensweise als Muster entwickeln, um andere Windows-Desktopanwendungen zu erstellen.

Der Windows-API (auch bekannt als die Win32-API, Windows-Desktop-API und klassische Windows-API) ist ein C#-Sprache ausgehend-Framework zum Erstellen von Windows-Anwendungen. Es wurde seit den 1980er Jahren und zum Erstellen von Windows-Anwendungen für Jahrzehnten verwendet wurde. Zusätzlich zu dieser API können z. B. MFC, ATL und der .NET Framework-Versionen haben mehr erweiterte und einfacher-to-Program Frameworks erstellt wurde. Auch die meisten modernen Code für universelle Windows-Plattform und Store-apps, die in C++ geschrieben wurde c++ / WinRT diese API unterhalb verwendet. Weitere Informationen über die Windows-API finden Sie unter [Windows-API Index](https://msdn.microsoft.com/library/windows/desktop/ff818516.aspx). Es gibt viele Methoden zum Erstellen von Windows-Anwendungen, aber dies war die erste.

> [!IMPORTANT]
> Aus Gründen der Übersichtlichkeit werden einige codeanweisungen im Text weggelassen. Die [erstellen Sie den Code](#build-the-code) Abschnitt am Ende dieses Dokuments wird den vollständigen Code gezeigt.

## <a name="prerequisites"></a>Erforderliche Komponenten

- Ein Computer, der Microsoft Windows 7 oder höher ausgeführt wird. Wir empfehlen Windows 10 Entwicklung optimale Ergebnisse zu erzielen.

- Eine Kopie des Visual Studio-2017. Informationen zum Herunterladen und Installieren von Visual Studio finden Sie unter [installieren Sie Visual Studio 2017](/visualstudio/install/install-visual-studio). Wenn Sie das Installationsprogramm ausführen, stellen sicher, dass die **Desktopentwicklung mit C++** arbeitsauslastung aktiviert ist. Machen Sie sich keine Gedanken Sie, wenn Sie diese arbeitsauslastung nicht installiert haben, wenn Sie Visual Studio installiert. Sie können das Installationsprogramm erneut ausführen und installieren Sie es jetzt.

   ![Desktop-Entwicklung mit C++](../build/media/desktop-development-with-cpp.png "Desktopentwicklung mit C++")

- Einen Überblick über die Grundlagen der Verwendung von Visual Studio-IDE. Wenn Sie Windows-desktop-apps vor verwendet haben, können Sie wahrscheinlich Schritt zu halten. Eine Einführung finden Sie unter [Visual Studio-IDE Featuretour](/visualstudio/ide/visual-studio-ide).

- Einen Überblick über genügend die Grundlagen der Programmiersprache C++ nachvollziehen. Keine Sorge, wir keine zu kompliziert gestalten.

## <a name="create-a-windows-desktop-project"></a>Erstellen eines Windows-desktop-Anwendungsprojekts

Führen Sie diese Schritte zum Erstellen Ihrer ersten Windows-Desktopprojekt, und geben den Code für eine funktionierende Windows desktop-Anwendung. Wenn Sie eine Version von Visual Studio, die älter sind als Visual Studio 2017 Version 15.3 verwenden, fahren Sie mit [So erstellen ein Windows-desktop-Projekt in Visual Studio 2017 RTM](#create-in-vs2017-rtm).

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>So erstellen eine Windows-Desktopprojekt in Visual Studio 2017 Update 15.3 und höher

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. In der **neues Projekt** erweitern Sie im Dialogfeld im linken Bereich **installiert**, **Visual C++**, und wählen Sie dann **Windows Desktop**. Wählen Sie im mittleren Bereich **im Assistenten für Windows Desktop**.

   In der **Namen** geben einen Namen für das Projekt ein, z. B. *DesktopApp*. Klicken Sie auf **OK**.

   ![Nennen Sie das Projekt DesktopApp](../build/media/desktop-app-new-project-name-153.png "DesktopApp Projektnamen")

1. In der **Windows-Desktop-Projekt** Dialogfeld unter **Anwendungstyp**Option **Windows-Anwendung (.exe)**. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **OK** zum Erstellen des Projekts.

   ![Erstellen Sie im Assistenten für Windows-Desktopprojekt DesktopApp](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp im Assistenten für Windows-Desktopprojekt erstellen")

1. In **Projektmappen-Explorer**, mit der rechten Maustaste die **DesktopApp** Projekts **hinzufügen**, und wählen Sie dann **neues Element**.

   ![Neues Element hinzufügen DesktopApp Projekt](../build/media/desktop-app-project-add-new-item-153.gif "neues Element hinzufügen, DesktopApp-Projekt")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)**. In der **Namen** geben einen Namen für die Datei, z. B. *HelloWindowsDesktop.cpp*. Wählen Sie **Hinzufügen** aus.

   ![Hinzufügen von cpp-Datei zu DesktopApp Projekt](../build/media/desktop-app-add-cpp-file-153.png "cpp-Datei zu DesktopApp Projekt hinzufügen")

Das Projekt ist jetzt erstellt und die Quelldatei wird im Editor geöffnet. Um den Vorgang fortzusetzen, fahren Sie fort mit [erstellen Sie den Code](#create-the-code).

### <a id="create-in-vs2017-rtm"></a>So erstellen ein Windows-desktop-Projekt in Visual Studio 2017 RTM

1. Wählen Sie im Menü **Datei** die Option **Neu** und anschließend **Projekt** aus.

1. In der **neues Projekt** erweitern Sie im Dialogfeld im linken Bereich **installiert**, **Vorlagen**, **Visual C++**, und wählen Sie dann auf **Win32**. Wählen Sie im mittleren Bereich **Win32-Projekt**aus.

   In der **Namen** geben einen Namen für das Projekt ein, z. B. *DesktopApp*. Klicken Sie auf **OK**.

   ![Nennen Sie das Projekt DesktopApp](../build/media/desktop-app-new-project-name-150.png "DesktopApp Projektnamen")

1. Auf der **Übersicht** auf der Seite der **Win32-Anwendungsassistenten**, wählen Sie **Weiter**.

   ![Erstellen von DesktopApp in Win32-Anwendung-Assistenten (Übersicht)](../build/media/desktop-app-win32-wizard-overview-150.png "erstellen DesktopApp in Win32-Anwendung-Assistenten (Übersicht)")

1. Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **Windows-Anwendung**. Wählen Sie unter **Zusätzliche Optionen**die Option **Leeres Projekt**aus. Wählen Sie **Fertig stellen** zum Erstellen des Projekts.

   ![Erstellen DesktopApp in Win32-Anwendung Assistenteneinstellungen](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp in Win32-Anwendungseinstellungen-Assistenten erstellen")

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt DesktopApp, wählen Sie **hinzufügen**, und wählen Sie dann **neues Element**.

   ![Neues Element hinzufügen DesktopApp Projekt](../build/media/desktop-app-project-add-new-item-150.gif "neues Element hinzufügen, DesktopApp-Projekt")

1. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C++-Datei (.cpp)**. In der **Namen** geben einen Namen für die Datei, z. B. *HelloWindowsDesktop.cpp*. Wählen Sie **Hinzufügen** aus.

   ![Hinzufügen von cpp-Datei zu DesktopApp Projekt](../build/media/desktop-app-add-cpp-file-150.png "cpp-Datei zu DesktopApp Projekt hinzufügen")

Das Projekt ist jetzt erstellt und die Quelldatei wird im Editor geöffnet.

## <a name="create-the-code"></a>Erstellen Sie den code

Als Nächstes erfahren Sie, wie Sie den Code für eine Windows-desktop-Anwendung in Visual Studio zu erstellen.

### <a name="to-start-a-windows-desktop-application"></a>So beginnen Sie eine Windows-Desktopanwendung

1. Ebenso wie jede C- und C++-Anwendung benötigen eine `main` fungieren als Ausgangspunkt erforderlich, jede Windows-Desktopanwendung benötigen eine `WinMain` Funktion. `WinMain` besitzt die folgende Syntax.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Informationen zu den Parametern und Rückgabewerten dieser Funktion finden Sie unter [WinMain Einstiegspunkt](https://msdn.microsoft.com/library/windows/desktop/ms633559).

   > [!NOTE]
   > Was diese zusätzliche Wörter sind, z. B. **RÜCKRUF**, oder **HINSTANCE**, oder  **\_In\_**? Die herkömmliche Windows-API verwendet Typdefinitionen und Präprozessormakros umfassend zu abstrahieren einige Details von Typen und plattformspezifischen code, z. B. Aufrufkonventionen, **__declspec** Deklarationen und Compiler-Pragmas. In Visual Studio können Sie IntelliSense [Quick Info](/visualstudio/ide/using-intellisense#quick-info) Funktion, um festzustellen, was diese Typdefinitionen und Makros definieren. Bewegen Sie Ihre Maus auf das Wort von Interesse sind, oder wählen Sie ihn aus, und drücken Sie STRG-K, STRG-I für ein kleines Popupfenster, das die Definition enthält. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense). Parameter und Rückgabetypen verwenden häufig *SAL-Anmerkungen* helfen Ihnen beim Catch Programmierfehler. Weitere Informationen finden Sie unter [mithilfe von SAL-Anmerkungen zum Reduzieren von C/C++-Codefehlern](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Windows-desktop-Programme erfordern &lt;windows.h >. &lt;TCHAR.h > definiert die `TCHAR` -Makro, das letztlich aufgelöst wird, `wchar_t` Wenn das Unicode-Symbol in Ihrem Projekt definiert ist, andernfalls löst zum `char`.  Wenn Sie immer mit Unicode-aktiviert erstellen, können Sie brauchen nicht TCHAR und nur Wchar_t direkt.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Neben der `WinMain` -Funktion muss jede Windows-Desktopanwendung auch über eine Fensterprozedurfunktion verfügen. Diese Funktion ist in der Regel mit dem Namen `WndProc` , aber der name kann sich auf einen beliebigen Namen. `WndProc` besitzt die folgende Syntax.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   In dieser Funktion, die Sie schreiben Code für die Behandlung *Nachrichten* , die die Anwendung empfängt von Windows beim *Ereignisse* auftreten. Z. B. wenn ein Benutzer eine Schaltfläche "OK" in der Anwendung auswählt, Windows wird eine Nachricht an Sie senden und Sie können Code Schreiben Ihrer `WndProc` Funktion, die die Arbeit geeignet ist. Hierbei spricht *Behandlung von* ein Ereignis. Sie behandeln nur die Ereignisse, die für Ihre Anwendung relevant sind.

   Weitere Informationen finden Sie unter [Window Procedures](https://msdn.microsoft.com/library/windows/desktop/ms632593).

### <a name="to-add-functionality-to-the-winmain-function"></a>So fügen Sie der WinMain-Funktion Funktionen hinzu

1. In der `WinMain` -Funktion, füllen Sie eine Struktur des Typs [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577). Diese Struktur enthält Informationen über das Fenster, z. B. das Anwendungssymbol, die Hintergrundfarbe des Fensters, den Namen in der Titelleiste und sehr wichtig, einen Funktionszeiger auf die Fensterprozedur anzeigen. Das folgende Beispiel zeigt eine typische `WNDCLASSEX` -Struktur.

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

   Informationen über die Felder dieser Struktur finden Sie unter [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577).

1. Registrieren Sie die `WNDCLASSEX` mit Windows damit über das Fenster und zum Senden von Nachrichten darauf, dass die It weiß. Verwenden der [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587) Funktion, und übergeben Sie die Fensterklassenstruktur als Argument. Die `_T` Makro wird verwendet, da wir verwenden die `TCHAR` Typ.

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

1. Sie können nun ein Fenster erstellen. Verwenden der [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) Funktion.

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

   Diese Funktion gibt eine `HWND`, dies ist ein Handle für ein Fenster. Ein Handle ist etwas wie ein Zeiger, die Windows zum Nachverfolgen geöffneten Fenstern verwendet. Weitere Informationen finden Sie unter [Windows Data Types](https://msdn.microsoft.com/library/windows/desktop/aa383751).

1. Zu diesem Zeitpunkt das Fenster erstellt wurde, aber wir benötigen Sie weitere anzuweisen, Windows, um sichtbar zu machen. Das heißt, was bewirkt, dass dieser Code:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Das angezeigte Fenster nicht viel Inhalt haben, da Sie noch nicht implementiert wurde die `WndProc` Funktion. Das heißt, wird die Anwendung nicht noch die Nachrichten behandeln, die Windows jetzt an sie sendet.

1. Um die Nachrichten zu behandeln, fügen wir zuerst eine Nachrichtenschleife zum Abhören von Nachrichten, die Windows sendet hinzu. Wenn die Anwendung eine Nachricht empfängt, diese Schleife leitet er die `WndProc` Funktion behandelt werden. Die Nachrichtenschleife ähnelt dem folgenden Code.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Weitere Informationen zu den Strukturen und Funktionen in der Nachrichtenschleife, finden Sie unter [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955), und [DispatchMessage ](https://msdn.microsoft.com/library/windows/desktop/ms644934).

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

   Eine wichtige Meldung wird die [WM_PAINT](https://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht. Die Anwendung empfängt diese Nachricht, wenn ein Teil des angezeigten Fenster aktualisiert werden muss. Dieses Ereignis kann auftreten, wenn ein Benutzer ein Fenster vor Ihrem Fenster verschoben und dann bewegt Weg erneut aus. Die Anwendung weiß nicht, wann Ereignisse wie folgt auftreten; nur Windows bekannt ist, damit Sie mit benachrichtigt `WM_PAINT`. Wenn das Fenster erstmals angezeigt wird, müssen alle Daten aktualisiert werden.

   Behandelt eine `WM_PAINT` Nachricht werden beim ersten Aufruf [BeginPaint](https://msdn.microsoft.com/library/windows/desktop/dd183362), behandeln Sie anschließend die gesamte Logik, um das Layout von Text, Schaltflächen und anderen Steuerelementen im Fenster, und rufen dann [EndPaint](https://msdn.microsoft.com/library/windows/desktop/dd162598). Für diese Anwendung besteht die Logik zwischen dem Anfangs- und dem Beendigungsanruf zur Anzeige der Zeichenfolge "Hello, Windows-Desktop!" im Fenster. Im folgenden Code, beachten Sie, dass die [TextOut](https://msdn.microsoft.com/library/windows/desktop/dd145133) Funktion dient zur Anzeige der Zeichenfolge.

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

   `HDC`In diesem Code wird ein Handle für einen Gerätekontext, also eine Datenstruktur, die von Windows verwendet, um die Anwendung für die Kommunikation mit dem Graphics-Subsystem zu aktivieren. Die `BeginPaint` und `EndPaint` Funktionen stellen Sie sicher, dass Ihre Anwendung verhält sich wie eine gute Bürger und nicht den Gerätekontext für mehr als notwendig zu verwenden. Dadurch wird sichergestellt, dass das Graphics-Subsystem für die Verwendung durch andere Anwendungen verfügbar ist.

1. Eine Anwendung behandelt normalerweise viele andere Meldungen, z. B. [WM_CREATE](https://msdn.microsoft.com/library/windows/desktop/ms632619) , wenn ein Fenster erstellt wird, und [WM_DESTROY](https://msdn.microsoft.com/library/windows/desktop/ms632620) , wenn das Fenster geschlossen. Der folgende Code zeigt eine grundlegende, jedoch vollständige `WndProc` -Funktion.

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

Wie angekündigt, ist hier der vollständige Code für die Anwendung arbeiten.

### <a name="to-build-this-example"></a>So erstellen Sie dieses Beispiel

1. Löschen Sie sämtlicher Code, den Sie im Editor in HelloWindowsDesktop.cpp eingegeben haben. Kopieren Sie diesen Beispielcode, und fügen Sie ihn in HelloWindowsDesktop.cpp:

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

1. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen**. Die Kompilierungsergebnisse sollte angezeigt werden, der **Ausgabe** Fenster in Visual Studio.

   ![Erstellen Sie das Projekt DesktopApp](../build/media/desktop-app-project-build-150.gif "erstellen Sie das Projekt DesktopApp")

1. Um die Anwendung auszuführen, drücken Sie die **F5**. Ein Fenster mit dem Text "Hello, Windows-Desktop!" sollte in der oberen linken Ecke der Anzeige angezeigt werden.

   ![Führen Sie das Projekt DesktopApp](../build/media/desktop-app-project-run-150.gif "führen Sie das Projekt DesktopApp")

Herzlichen Glückwunsch! Sie haben in dieser exemplarischen Vorgehensweise abgeschlossen und erstellt eine herkömmliche Windows-desktop-Anwendung.

## <a name="see-also"></a>Siehe auch

[Windows-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md)
