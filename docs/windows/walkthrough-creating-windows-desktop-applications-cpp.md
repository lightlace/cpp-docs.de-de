---
title: "Exemplarische Vorgehensweise: Erstellen von Windows-Desktopanwendungen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows-Anwendungen [C++], Win32"
  - "WinMain"
  - "Win32-Anwendungen [C++]"
  - "Windows-API [C++]"
ms.assetid: a247a9af-aff1-4899-9577-5f8104a0afbb
caps.latest.revision: 27
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen von Windows-Desktopanwendungen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird erläutert, wie Sie eine einfache Windows\-Desktopanwendung erstellen, die „Hello, World\!“ in einem Fenster anzeigt. Sie können den Code verwenden, den Sie in dieser exemplarischen Vorgehensweise als Muster entwickeln, um andere Windows\-Desktopanwendungen zu erstellen.  
  
 Die Win32\-API \(auch als Windows\-API bezeichnet\) ist ein auf C basierendes Framework zum Erstellen von Windows\-Anwendungen. Weitere Informationen zur Win32\-API finden Sie unter [Windows\-API](https://msdn.microsoft.com/en-us/library/cc433218.aspx).  
  
> [!IMPORTANT]
>  Damit bestimmte Codesegmente in den Schritten in diesem Dokument genauer erklärt werden können, können einige Codeanweisungen ausgelassen werden, die ansonsten für eine funktionierende Anwendung erforderlich wären; zum Beispiel Include\-Direktiven und globale Variablendeklarationen. Im Abschnitt **Beispiel** am Ende dieses Dokuments wird der vollständige Code gezeigt.  
  
## Vorbereitungsmaßnahmen  
 Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C\+\+.  
  
 Eine Videodarstellung finden Sie unter [Gewusst wie: Erstellen von Win32\-Anwendungen \(C\+\+\)](http://go.microsoft.com/fwlink/?LinkId=102471) in der Visual Studio 2008\-Dokumentation.  
  
### So erstellen Sie ein Win32\-basiertes Projekt  
  
1.  Klicken Sie im Menü **Datei** auf **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Dialogfeld **Neues Projekt** im linken Bereich auf **Installierte Vorlagen** und auf **Visual C\+\+**, und wählen Sie dann **Win32** aus. Wählen Sie im mittleren Bereich **Win32\-Projekt** aus.  
  
     Geben Sie im Feld **Name** einen Namen für das Projekt ein, z. B. `win32app`. Klicken Sie auf **OK**.  
  
3.  Klicken Sie auf der Willkommensseite des **Win32\-Anwendungs\-Assistenten** auf **Weiter**.  
  
4.  Wählen Sie auf der Seite "Anwendungseinstellungen" unter **Anwendungstyp** die Option **Windows\-Anwendung** aus. Wählen Sie unter **Zusätzliche Optionen** die Option **Leeres Projekt** aus. Klicken Sie auf **Fertig stellen**, um das Projekt zu erstellen.  
  
5.  Klicken Sie in **Projektmappen\-Explorer** mit der rechten Maustaste auf das Win32app\-Projekt, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **C\+\+\-Datei \(.cpp\)**. Geben Sie im Feld **Name** einen Namen für die Datei ein, z. B. `GT_HelloWorldWin32.cpp`. Klicken Sie auf **Hinzufügen**.  
  
### So beginnen Sie eine Windows\-Desktopanwendung  
  
1.  Ebenso wie jede C\- und C\+\+\-Anwendung als Ausgangspunkt eine `main`\-Funktion benötigen, muss jede Win32\-basierte Anwendung über eine `WinMain`\-Funktion verfügen.`WinMain` besitzt die folgende Syntax.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow);  
    ```  
  
     Informationen zu den Parametern und Rückgabewerten dieser Funktion finden Sie unter [WinMain Function](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
2.  Da für Anwendungscode vorhandene Definitionen verwendet werden müssen, fügen Sie der Datei Include\-Anweisungen hinzu.  
  
    ```  
    #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h>  
    ```  
  
3.  Neben der `WinMain`\-Funktion muss jede Windows\-Desktopanwendung auch über eine Fensterprozedurfunktion verfügen. Diese Funktion wird in der Regel als `WndProc` bezeichnet.`WndProc` besitzt die folgende Syntax.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);  
    ```  
  
     Diese Funktion behandelt die zahlreichen *Nachrichten*, die eine Anwendung vom Betriebssystem empfängt. Beispiel: In einer Anwendung mit einem Dialogfeld, das die Schaltfläche **OK** beinhaltet, wird beim Klicken auf die Schaltfläche vom Betriebssystem eine Meldung an die Anwendung gesendet, dass auf die Schaltfläche geklickt wurde.`WndProc` ist für die Reaktion auf das Ereignis zuständig. Im Beispiel könnte die entsprechende Antwort sein, das Dialogfeld zu schließen.  
  
     Weitere Informationen finden Sie unter [Window Procedures](http://msdn.microsoft.com/library/windows/desktop/ms632593).  
  
### So fügen Sie der WinMain\-Funktion Funktionen hinzu  
  
1.  Erstellen Sie in der `WinMain`\-Funktion eine Fensterklassenstruktur vom Typ [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577). Diese Struktur enthält Informationen über das Fenster, z. B. das Anwendungssymbol, die Hintergrundfarbe des Fensters, den Namen für die Anzeige in der Titelleiste, den Namen der Fensterprozedurfunktion usw. Das folgende Beispiel zeigt eine typische `WNDCLASSEX`\-Struktur.  
  
    ```  
    WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION));  
    ```  
  
     Informationen über die Felder dieser Struktur finden Sie unter [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577).  
  
2.  Nachdem Sie nun eine Fensterklasse erstellt haben, müssen Sie sie registrieren. Verwenden Sie die [RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587)\-Funktion, und übergeben Sie die Fensterklassenstruktur als Argument.  
  
    ```  
    if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
3.  Sie können nun ein Fenster erstellen. Verwenden Sie die [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)\-Funktion.  
  
    ```  
    static TCHAR szWindowClass[] = _T("win32app"); static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
     Diese Funktion gibt einen HWND zurück, der ein Handle für ein Fenster ist. Weitere Informationen finden Sie unter [Windows\-Datentypen](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
4.  Zeigen Sie das Fenster nun mithilfe des folgenden Codes an.  
  
    ```  
    // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd);  
    ```  
  
     Zu diesem Zeitpunkt weist das angezeigte Fenster nur wenig Inhalt auf, da die `WndProc`\-Funktion noch nicht implementiert wurde.  
  
5.  Fügen Sie nun eine Nachrichtenschleife für die Nachrichten hinzu, die vom Betriebssystem gesendet werden. Wenn die Anwendung eine Meldung empfängt, wird die Meldung von der Schleife zur Behandlung an die `WndProc`\-Funktion weitergeleitet. Die Nachrichtenschleife ähnelt dem folgenden Code.  
  
    ```  
    MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam;  
    ```  
  
     Weitere Informationen über die in der Nachrichtenschleife verwendeten Strukturen und Funktionen finden Sie unter [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
     An diesem Punkt sollte die `WinMain`\-Funktion in etwa dem folgenden Code entsprechen.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application dows not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; }  
    ```  
  
### So fügen Sie der WndProc\-Funktion Funktionen hinzu  
  
1.  Damit die `WndProc`\-Funktion die Nachrichten behandeln kann, die von der Anwendung empfangen werden, implementieren Sie eine switch\-Anweisung.  
  
     Als erste Meldung wird die [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)\-Meldung behandelt. Die Anwendung empfängt diese Nachricht, wenn ein Teil des angezeigten Fenster aktualisiert werden muss. \(Wenn das Fenster erstmals angezeigt wird, muss es vollständig aktualisiert werden.\)  
  
     Rufen Sie zur Behandlung einer `WM_PAINT`\-Nachricht zuerst [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362) auf, behandeln Sie anschließend die gesamte Logik, um das Layout von Text, Schaltflächen und anderen Steuerelementen im Fenster zu behandeln, und rufen Sie anschließend [EndPaint](http://msdn.microsoft.com/library/windows/desktop/dd162598) auf. Für diese Anwendung besteht die Logik zwischen dem Anfangs\- und dem Beendigungsaufruf in der Anzeige der Zeichenfolge "Hello, World\!" im Fenster. Im folgenden Code wird die [TextOut](http://msdn.microsoft.com/library/windows/desktop/dd145133)\-Funktion zur Anzeige der Zeichenfolge verwendet.  
  
    ```  
    PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; }  
    ```  
  
2.  Eine Anwendung behandelt normalerweise viele andere Meldungen, z. B. [WM\_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619) und [WM\_DESTROY](http://msdn.microsoft.com/library/windows/desktop/ms632620). Der folgende Code zeigt eine grundlegende, jedoch vollständige `WndProc`\-Funktion.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
    ```  
  
##  <a name="example"></a> Beispiel  
  
#### So erstellen Sie dieses Beispiel  
  
1.  Erstellen Sie ein Win32\-basiertes Projekt gemäß der Erläuterung unter "So erstellen Sie ein Win32\-basiertes Projekt" zu Beginn dieser exemplarischen Vorgehensweise.  
  
2.  Kopieren Sie den Code, der diesen Schritten entsprechend erstellt wurde, und fügen Sie ihn anschließend in die Quelldatei "GT\_HelloWorldWin32.cpp" ein.  
  
3.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
4.  Drücken Sie F5, um die Anwendung auszuführen. Ein Fenster mit dem Text „Hello World\!“ sollte in der oberen linken Ecke der Anzeige angezeigt werden.  
  
### Code  
  
```  
// GT_HelloWorldWin32.cpp // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h> // Global variables // The main window class name. static TCHAR szWindowClass[] = _T("win32app"); // The string that appears in the application's title bar. static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); HINSTANCE hInst; // Forward declarations of functions included in this code module: LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM); int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; } // //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM) // //  PURPOSE:  Processes messages for the main window. // //  WM_PAINT    - Paint the main window //  WM_DESTROY  - post a quit message and return // // LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
```  
  
## Siehe auch  
 [Windows\-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md)