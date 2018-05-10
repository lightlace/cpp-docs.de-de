---
title: 'Vorgehensweise: Verwenden von vorhandenem C++-Code in einer universelle Windows-Plattform-App | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3f8cb26a66fce9c4b87822ffbfa4005f3a2e758
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Vorgehensweise: Verwenden von vorhandenem C++-Code in einer universelle Windows-Plattform-App
Die vielleicht einfachste Möglichkeit, für die Ausführung Ihres Desktop-Programms in der UWP-Umgebung zu sorgen, ist der Einsatz von Desktop Bridge-Technologien. Zu diesen gehört der Desktop App Converter, der Ihre vorhandene Anwendung als UWP-App packt, ohne dass Codeänderungen erforderlich sind. Weitere Informationen finden Sie unter [Portieren Ihrer Desktop-App zur universellen Windows-Plattform (UWP) mit der Desktop-Brücke](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-root).

Im weiteren Verlauf dieses Themas wird das Portieren von C++-Bibliotheken (DLLs und statischen Bibliotheken) auf die universelle Windows-Plattform (UWP) erläutert. Dieser Vorgang ermöglicht, dass Ihre wesentliche C++-Logik in mehreren UWP-Apps verwendet werden kann. 
  
 UWP-Apps werden in einer geschützten Umgebung ausgeführt. Daher sind viele Win32-, COM- und CRT-API-Aufrufe, die die Sicherheit der Plattform gefährden können, nicht zulässig. Der Compiler kann solche Aufrufe erkennen und einen Fehler erzeugen, wenn die Option /ZW verwendet wird. Sie können das Zertifizierungskit für Apps auf Ihre Anwendung anwenden, um Code mit unzulässigen API-Aufrufen zu erkennen. Siehe [Verwenden des Zertifizierungskits für Windows-Apps](https://msdn.microsoft.com/library/windows/apps/hh694081.aspx).  
  
 Wenn der Quellcode für die Bibliothek verfügbar ist, können Sie unzulässige API-Aufrufe möglicherweise beseitigen. Details, einschließlich einer Liste der zulässigen bzw. unzulässigen APIs, finden Sie unter [Win32- und COM-API für Windows-Runtime-Apps und Universal Windows-Plattform-Apps (UWP)](https://msdn.microsoft.com/library/windows/apps/br205762.aspx) und [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md). Einige Alternativen finden Sie unter [Alternatives to Windows APIs in UWP apps (Alternativen zu Windows-APIs in UWP-Apps)](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).  
  
 Sobald Sie versuchen, einen Verweis von einem universellen Windows-Projekt auf eine klassische Desktopbibliothek hinzuzufügen, erhalten Sie eine Fehlermeldung, die besagt, dass die Bibliothek nicht kompatibel ist. Bei einer statischen Bibliothek können Sie ganz einfach einen Link auf Ihre Bibliothek erstellen, indem Sie die Bibliothek (LIB-Datei) zu Ihrer Linkereingabe hinzufügen, genau wie in einer klassischen Win32-Anwendung. Bei Bibliotheken, für die nur eine Binärdatei verfügbar ist, ist dies die einzige Option. Eine statische Bibliothek wird mit der ausführbaren Datei Ihrer App verknüpft, aber eine Win32-DLL, die Sie in einer UWP-App nutzen, muss in die App gepackt werden, indem sie in das Projekt eingeschlossen und als Inhalt markiert wird. Um eine Win32-DLL in einer UWP-App zu laden, müssen Sie außerdem [LoadPackagedLibrary](https://msdn.microsoft.com/library/windows/desktop/hh447159.aspx) anstelle von „LoadLibrary“ oder „LoadLibraryEx“ aufrufen.  
  
 Wenn Sie über den Quellcode für die DLL oder statische Bibliothek verfügen, können Sie sie mit /ZW als UWP-Projekt neu kompilieren. Dann können Sie mit dem Projektmappen-Explorer einen Verweis hinzufügen und sie in C++-Apps für UWP verwenden. Im Fall einer DLL erstellen Sie einen Link mit der Exportbibliothek.  
  
 Um Funktionalität für Aufrufer in anderen Sprachen verfügbar zu machen, können Sie die Bibliothek in eine Komponente für Windows-Runtime konvertieren. Komponenten für Windows-Runtime unterscheiden sich insofern von normalen DLLs, als sie Metadaten in Form von WINMD-Dateien enthalten, die den Inhalt auf eine Weise beschreiben, die von .NET und JavaScript-Consumern benötigt wird. Um API-Elemente für andere Sprachen verfügbar zu machen, können Sie C++/CX-Konstrukte, wie z.B. Verweisklassen, hinzufügen und öffentlich machen bzw. die [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md) verwenden.  In Windows 10 und höher können Sie die [C++/WinRT-Bibliothek](https://github.com/microsoft/cppwinrt) anstelle von C++/CX verwenden. 
  
 Die vorangegangenen Erläuterungen gelten nicht für COM-Komponenten. Diese müssen anders behandelt werden. Wenn Sie über einen COM-Server in einer EXE oder DLL verfügen, können Sie ihn in einem universellen Windows-Projekt verwenden, sofern Sie ihn als [registrierungsfreie COM-Komponente](https://msdn.microsoft.com/library/dd408052.aspx) packen, dem Projekt als Inhaltsdatei hinzufügen und mit [CoCreateInstanceFromApp](https://msdn.microsoft.com/library/windows/apps/hh404137.aspx) instanziieren. Siehe den Blogbeitrag [Using Free-COM DLL in Windows Store C++ Project](http://blogs.msdn.com/b/win8devsupport/archive/2013/05/20/using-free-com-dll-in-windows-store-c-project.aspx).  
  
 Wenn Sie eine vorhandene COM-Bibliothek auf die UWP portieren möchten, können Sie sie möglicherweise mit der [Windows Runtime C++ Template Library (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md) in eine Komponente für Windows-Runtime konvertieren. Die WRL unterstützt nicht alle Funktionen von ATL und OLE. Ob eine Portierung möglich ist, hängt davon ab, wie stark Ihr COM-Code von welchen COM-, ATL- und OLE-Funktionen abhängt.  
  
 Dies sind die verschiedenen Verwendungsmöglichkeiten für vorhandenen C++-Code in UWP-Projekten. Einige Methoden erfordern die Neukompilierung des Codes mit aktivierten Komponentenerweiterungen (C++/CX) (d. h. mit der Option /ZW), andere nicht. Wenn Sie daher Code in standardmäßigem C++ beibehalten oder eine klassische Win32-Kompilierungsumgebung für einigen Code aufrechterhalten möchten, können Sie dies mit den entsprechenden Architekturoptionen tun. Beispielsweise sollte jeglicher Code, der UWP-Benutzeroberfläche und Typen enthält, die für C#-, Visual Basic- und JavaScript-Aufrufer verfügbar gemacht werden sollen, in Windows-App-Projekten und Windows-Runtime-Komponenten-Projekten enthalten sein. Code, der nur in C++-Code (einschließlich C++/CX) verwendet werden soll, kann entweder in einem Projekt, das mit der Option /WX kompiliert wird, oder in einem standardmäßigen C++-Projekt enthalten sein. Ausschließlich binärer Code kann durch Einbindung als statische Bibliothek verwendet oder mit der App als Inhalt gepackt und in eine DLL geladen werden, sofern keine unzulässigen APIs verwendet werden.  
  
 Unabhängig davon, welches dieser Entwicklungsszenarios Sie wählen, sollten Sie in jedem Fall eine Reihe von Makrodefinitionen kennen, die Sie in Ihrem Code verwenden können, damit Sie Code bedingt auf der klassischen Win32-Desktopplattform und UWP kompilieren können.  
  
```cpp  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)  
```  
  
 Diese Anweisungen gelten jeweils für UWP-Apps, Windows Phone Store-Apps, beide oder keines von beiden (nur klassische Win32-Desktop-Apps). Diese Makros sind nur in Windows SDK 8.1 und höher verfügbar. Wenn Code mit früheren Versionen des Windows SDK oder für andere Plattformen als Windows kompiliert werden muss, sollten Sie daher auch den Fall berücksichtigen, dass sie nicht definiert sind.  
  
 Dieses Thema enthält die folgenden Verfahren.  
  
1.  [Verwenden einer Win32-DLL in einer UWP-App](#BK_Win32DLL)  
  
2.  [Verwenden einer nativen, statischen C++-Bibliothek in einer UWP-App](#BK_StaticLib)  
  
3.  [Portieren einer C++-Bibliothek in eine Komponente für Windows-Runtime](#BK_WinRTComponent)  
  
##  <a name="BK_Win32DLL"></a> Verwenden einer Win32-DLL in einer UWP-App  
 Um eine höhere Sicherheit und Zuverlässigkeit zu erreichen, werden universelle Windows-Apps in einer eingeschränkten Runtime-Umgebung ausgeführt, damit Sie eine beliebige systemeigene DLL nicht genauso nutzen können, wie sie es in einer klassischen Windows-Desktopanwendung würden. Wenn Sie über Quellcode für eine DLL verfügen, können Sie den Code so portieren, dass er unter UWP ausgeführt werden kann. Als Erstes ändern Sie einige Projekteinstellungen und Projektdatei-Metadaten, um das Projekt als UWP-Projekt zu identifizieren. Sie müssen den Bibliothekscode mit der Option /ZW kompilieren, sodass C++/CX aktiviert wird. Bestimmte API-Aufrufe sind in UWP-Apps aufgrund strenger Kontrollen hinsichtlich der Umgebung nicht zulässig. Siehe [Win32 und COM für Windows-Runtime-Apps und Universal Windows Platform (UWP)-Apps](https://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
 Das folgende Verfahren gilt für den Fall, in dem Sie über eine systemeigene DLL verfügen, die mithilfe der „__declspec(dllexport)“ Funktionen verfügbar macht.  
  
#### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>So portieren Sie eine systemeigene DLL auf UWP, ohne ein neues Projekt zu erstellen  
  
1.  Wenn Sie eine systemeigene DLL besitzen, die Funktionen mithilfe von „__declspec(dllexport)“ exportiert, können Sie diese Funktionen aus einer UWP-App aufrufen, indem Sie die DLL als UWP-Projekt neu kompilieren. Nehmen wir beispielsweise an, wir haben eine DLL, die eine Reihe von Klassen und deren Methoden mit ähnlichem Code wie in der folgenden Header-Datei exportiert:  
  
    ```  
    // giraffe.h  
    #pragma once  
  
    #ifdef _DLL  
    #define GIRAFFE_API __declspec(dllexport)  
    #else  
    #define GIRAFFE_API   
    #endif  
  
    GIRAFFE_API int giraffeFunction();  
  
    class Giraffe  
    {  
        int id;  
            Giraffe(int id_in);  
        friend class GiraffeFactory;  
  
    public:  
        GIRAFFE_API int GetID();  
    };  
  
    class GiraffeFactory  
    {  
        static int nextID;  
    
    public:  
        GIRAFFE_API GiraffeFactory();  
        GIRAFFE_API static int GetNextID();  
        GIRAFFE_API static Giraffe* Create();  
   };  
    ```  
  
     Und folgende Codedatei:  
  
    ```  
    // giraffe.cpp  
    #include "stdafx.h"  
    #include "giraffe.h"  
  
    Giraffe::Giraffe(int id_in) : id(id_in)  
    {  
    }  
  
    int Giraffe::GetID()  
    {  
      return id;  
    }  
  
    int GiraffeFactory::nextID = 0;  
  
    GiraffeFactory::GiraffeFactory()  
    {  
        nextID = 0;  
    }  
  
    int GiraffeFactory::GetNextID()  
    {  
        return nextID;  
    }  
  
    Giraffe* GiraffeFactory::Create()  
    {  
        return new Giraffe(nextID++);  
    }  
  
    int giraffeFunction();  
    ```  
  
     Alles im Projekt (stdafx.h, dllmain.cpp) ist Teil der standardmäßigen Win32-Projektvorlage. Wenn Sie das nachvollziehen möchten, jedoch zu diesem Zeitpunkt noch nicht Ihre eigene DLL mit diesen Schritten verwenden möchten, erstellen Sie ein Win32-Projekt, wählen Sie im Projekt-Asssistenten DLL, und fügen Sie dann als Headerdatei „giraffe.h“ und als Codedatei „giraffe.cpp“ hinzu. Kopieren Sie anschließend die Inhalte aus dem Code in diesem Schritt in die entsprechenden Dateien.  
  
     Der Code definiert das Makro GIRAFFE_APIzum Auflösen der __declspec(dllexport), wenn _DLL definiert ist (d. h. wenn das Projekt als DLL erstellt wird).  
  
2.  Öffnen Sie die Projekteigenschaften für das DLL-Projekt, und legen Sie die Konfiguration auf **Alle Konfigurationen** fest.  
  
3.  Legen Sie in den Projekteigenschaften auf der Registerkarte **Allgemein** unter **C/C++** die Option **Windows Runtime-Erweiterung verwenden** auf **Ja (/ZW)** fest. Dadurch werden Komponentenerweiterungen (C++/CX) aktiviert.  
  
4.  Wählen Sie im **Projektmappen-Explorer** den Projektknoten, öffnen Sie das Kontextmenü , und wählen Sie dann **Projekt entladen** aus. Öffnen Sie anschließend das Kontextmenü des entladenen Projektknotens, und klicken Sie dann auf die Option zum Bearbeiten der Projektdatei. Suchen Sie das WindowsTargetPlatformVersion-Element, und ersetzen Sie sie durch die folgenden Elemente.  
  
    ```xml  
    <AppContainerApplication>true</AppContainerApplication>  
    <ApplicationType>Windows Store</ApplicationType>  
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>  
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>  
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>  
    ```  
  
     Schließen Sie die VCXPROJ-Datei, öffnen Sie erneut das Kontextmenü, und wählen Sie **Projekt erneut laden**.  
  
     Der Projektmappen-Explorer erkennt das Projekt nun als universelles Windows-Projekt.  
  
5.  Stellen Sie sicher, dass der Name der vorkompilierten Headerdatei richtig ist. Ändern Sie im Abschnitt „Vorkompilierte Header“ den Namen der vorkompilierten Headerdatei von „pch.h“ in „stdafx.h“. Wenn Sie dies nicht tun, wird die folgende Fehlermeldung angezeigt.  
  
    ```Output  
    error C2857: '#include' statement specified with the /Ycpch.h command-line option was not found in the source file  
    ```  
  
     Das Problem besteht darin, dass das universelle Windows-Projekt eine andere Namenskonvention für die vorkompilierte Headerdatei verwendet.  
  
6.  Erstellen Sie das Projekt. Sie erhalten möglicherweise einige Fehler zu nicht kompatiblen Befehlszeilenoptionen. Die häufig verwendete Option „Minimale Neuerstellung aktivieren“ (/ Gm) ist beispielsweise standardmäßig in vielen C++-Projekten festgelegt, ist nicht kompatibel mit/ZW.  
  
     Einige Funktionen sind nicht verfügbar, wenn Sie Etwas für die universelle Windows-Plattform kompilieren. Zu allen Problemen werden Compilerfehler angezeigt. Lösen Sie diese Fehler, bis Sie eine einwandfreie Version besitzen.  
  
7.  Um die DLL in einer UWP-App in der gleichen Projektmappe verwenden zu können, öffnen Sie das Kontextmenü für den UWP-Projektknoten, und wählen Sie **Verweis hinzufügen**.  
  
     Aktivieren Sie unter **Projekte>Projektmappe** das Kontrollkästchen neben dem DLL-Projekt, und klicken Sie dann auf die Schaltfläche **OK**.  
  
8.  Schließen Sie die Headerdatei(en) für die Bibliothek in die „pch.h“-Datei Ihrer UWP-App ein.  
  
    ```  
    #include "..\MyNativeDLL\giraffe.h"  
    ```  
  
9. Fügen Sie im UWP-Projekt wie gewohnt Code zum Aufrufen von Funktionen und Erstellen von Typen aus der DLL hinzu.  
  
    ```  
    MainPage::MainPage()  
    {  
        InitializeComponent();  
        GiraffeFactory gf;  
        Giraffe* g = gf.Create();  
        int id = g->GetID();  
    }  
  
    ```  
  
##  <a name="BK_StaticLib"></a> Verwenden einer nativen, statischen C++-Bibliothek in einer UWP-App  
 Sie können eine native statische C++-Bibliothek in einem UWP-Projekt verwenden, aber es gibt einige Einschränkungen zu beachten. Lesen Sie zunächst dieses [Thema](https://msdn.microsoft.com/library/hh771041.aspx) zu statischen Bibliotheken in C++/CX. Sie können auf den nativen Code in Ihrer statischen Bibliothek aus Ihrer UWP-App zugreifen, aber es wird nicht empfohlen, öffentliche Verweistypen in einer solchen statischen Bibliothek zu erstellen. Wenn Sie eine statische Bibliothek mit der Option /ZW kompilieren, gibt der Bibliothekar (eigentlich der Linker) folgende Warnung aus:  
  
```  
LNK4264: archiving object file compiled with /ZW into a static library; note that when authoring Windows Runtime types it is not recommended to link with a static library that contains Windows Runtime metadata  
```  
  
 Sie können jedoch eine statische Bibliothek in einer UWP-App ohne Neukompilieren mit /ZW verwenden. Sie können dann keine Verweistypen deklarieren oder C++/CX-Konstrukte verwenden, aber wenn Sie nur eine Bibliothek mit systemeigenem Code verwenden möchten, können Sie dies mit den folgenden Schritten tun.  
  
#### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>So verwenden Sie eine systemeigene, statische C++-Bibliothek in einem UWP-Projekt  
  
1.  Fügen Sie in den Projekteigenschaften für das UWP-Projekt im Bereich „Linker“ in der Input-Eigenschaft den Pfad zur Bibliothek hinzu. Beispiel: Für eine Bibliothek in dem Projekt, das seine Ausgabe in *SolutionFolder\Debug\MyNativeLibrary\MyNativeLibrary.lib* platziert, fügen Sie den relativen Pfad `Debug\MyNativeLibrary\MyNativeLibrary.lib` hinzu.  
  
2.  Fügen Sie eine include-Anweisung hinzu, um die Headerdatei auf Ihre Datei „pch.h“ im UWP-Projekt zu verweisen, und fügen Sie Code hinzu, der die Bibliothek verwendet.  
  
    ```  
    #include "..\MyNativeLibrary\giraffe.h"  
    ```  
  
     Fügen Sie keinen Verweis im Knoten **Verweise** im **Projektmappen-Explorer** hinzu. Dieser Mechanismus funktioniert nur für Komponenten für Windows-Runtime.  
  
##  <a name="BK_WinRTComponent"></a> Portieren einer C++-Bibliothek in eine Komponente für Windows-Runtime  
 Wenn Sie systemeigene APIs in einer statischen Bibliothek aus einer UWP-App nutzen möchten und Sie über den Quellcode für die systemeigene Bibliothek verfügen, können Sie den Code in eine Komponente für Windows-Runtime portieren. Es ist dann keine statische Bibliothek mehr, sondern eine DLL. Sie können diese in jeder C++-App für UWP verwenden. Im Gegensatz zur statischen Bibliothek können Sie jedoch auch Verweistypen und andere C++/CX-Konstrukte hinzufügen, die Clients unabhängig von der Sprache in UWP-App-Code zur Verfügung stehen. Daher können Sie auf diese Typen in C#, Visual Basic oder JavaScript zugreifen.  Das grundlegende Verfahren besteht darin, ein Projekt für eine Komponente für Windows-Runtime zu erstellen, den Code für die statische Bibliothek in das Projekt zu kopieren und alle Fehler zu beheben, die beim Verschieben des Codes von einer standardmäßigen C++-Kompilierung zu einer /ZW-Kompilierung auftreten.  
  
#### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>So portieren Sie eine C++-Bibliothek in eine Komponente für Windows-Runtime  
  
1.  Erstellen Sie ein Projekt für eine Komponente für Windows-Runtime.  
  
2.  Schließen Sie das Projekt.  
  
3.  Suchen Sie im Windows-Datei-Explorer nach dem Projekt. Standardmäßig verwendet Visual Studio den Ordner „Visual Studio 2017\Projects“ im Ordner „Dokumente“. Suchen Sie das C++-Bibliotheksprojekt, das den Code enthält, den Sie portieren möchten. Kopieren Sie die Quelldateien (Headerdateien, Codedateien und andere Ressourcen, auch in Unterverzeichnissen) aus dem C++-Bibliotheksprojekt, und fügen Sie sie in den Projektordner ein. Achten Sie dabei darauf, die gleiche Ordnerstruktur beizubehalten.  
  
4.  Öffnen Sie das Projekt der Komponente für Windows-Runtime erneut. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für den Projektknoten, und wählen Sie **Hinzufügen>Vorhandenes Element**.  
  
5.  Wählen Sie alle Dateien aus, die Sie aus dem ursprünglichen Projekt hinzufügen möchten, und wählen Sie OK. Wiederholen Sie dies ggf. für Unterordner.  
  
6.  Möglicherweise ist der Code jetzt teilweise doppelt. Wenn mehrere vorkompilierte Header (z. B. „stdafx.h“ und „pch.h“) vorhanden sind, wählen Sie einen aus. Kopieren Sie allen erforderlichen Code, wie z. B. include-Anweisungen, in den beibehaltenen Header. Löschen Sie anschließend die anderen, und überprüfen Sie in den Projekteigenschaften unter **Vorkompilierte Header**, ob der Name der Headerdatei korrekt ist.  
  
     Wenn Sie die als vorkompilierten Header zu verwendende Datei geändert haben, überprüfen Sie, ob die Optionen für vorkompilierte Header für jede Datei korrekt sind. Wählen Sie nacheinander die einzelnen CPP-Dateien aus, öffnen Sie jeweils das Eigenschaftenfenster, und vergewissern Sie sich, dass alle auf **Verwenden (/Yu)** festgelegt sind, mit Ausnahme des gewünschten vorkompilierten Headers, der auf **Erstellen (/Yc)** festgelegt werden sollte.  
  
7.  Erstellen Sie das Projekt, und beheben Sie alle Fehler. Diese Fehler können durch die Option /ZW oder durch eine neue Version des Windows SDK verursacht werden. Möglicherweise weisen Sie auch auf Abhängigkeiten, z. B. Headerdateien, von denen Ihre Bibliothek abhängt, oder auf Unterschiede in den Projekteinstellungen zwischen dem alten und dem neuen Projekt hin.  
  
8.  Fügen Sie Ihrem Projekt öffentliche Verweistypen hinzu, oder konvertieren Sie normale Typen in Verweistypen, um Einstiegspunkte in die Funktionalität verfügbar zu machen, die Sie von UWP-Apps aufrufen möchten.  
  
9. Testen Sie die Komponente, indem Sie in einem UWP-App-Projekt einen Verweis darauf erstellen, und fügen Sie Code zum Aufrufen der öffentlichen APIs hinzu, die Sie erstellt haben.  
  
## <a name="see-also"></a>Siehe auch  
 [Portieren auf die universelle Windows-Plattform](../porting/porting-to-the-universal-windows-platform-cpp.md)