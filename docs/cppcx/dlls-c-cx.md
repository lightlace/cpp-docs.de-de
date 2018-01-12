---
title: DLLs (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a759541dd31121f12283f9b2b0c5b468da477554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-ccx"></a>DLLs (C++/CX)
Sie können Visual Studio verwenden, erstellen Sie eine standardmäßige Win32-DLL oder eine Windows-Runtime-Komponenten-DLL, die von universellen Windows-Plattform-apps genutzt werden kann. Eine standard-DLL, die mit einer Version von Visual Studio oder Visual C++-Compiler, die älter als Visual Studio 2012 möglicherweise nicht ordnungsgemäß in einer universellen Windows-Plattform-app geladen und die app-Überprüfungstest im möglicherweise nicht erfolgreich erstellt wurde die [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)].  
  
## <a name="windows-runtime-component-dlls"></a>Windows-Runtime-Komponenten-DLLs  
 In fast allen Fällen Wenn Sie eine DLL für die Verwendung in einer universellen Windows-Plattform-app erstellen möchten, erstellen Sie es als Windows-Runtime-Komponente mithilfe der Projektvorlage dieses Namens. Sie können ein Windows-Runtime-Komponentenprojekt für DLLs erstellen, die öffentliche oder private Windows-Runtime-Typen aufweisen. Eine Windows-Runtime-Komponente kann von apps zugegriffen werden, die in einer beliebigen Windows-Runtime-kompatiblen Sprache geschrieben werden. Standardmäßig Projekt die compilereinstellungen für ein Windows-Runtime-Komponente verwendet die **/Zw** wechseln. Eine WinMD-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD-Datei übereinstimmen.  
  
 Weitere Informationen finden Sie unter [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md).  
  
#### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>Um einen Drittanbieter-Windows-Runtime-Komponente binäre in Ihrem Projekt zu verweisen  
  
1.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .  
  
2.  Eine Windows-Runtime-Komponente besteht aus einer DLL- und einer winmd-Datei, die die Metadaten enthält. In der Regel sind diese Dateien im selben Ordner. Klicken Sie im linken Bereich des Dialogfelds **Verweis hinzufügen** auf die Schaltfläche **Durchsuchen** , und navigieren Sie dann zum Speicherort der DLL und der WINMD-Datei. Weitere Informationen finden Sie unter [Tutorial: Erstellen und Verwenden von Erweiterungs-SDKs](http://msdn.microsoft.com/en-us/001e2fca-3d56-43ab-a5e0-0561d085679f).  
  
## <a name="standard-dlls"></a>Standard-DLLs  
 Sie können eine standard-DLL für C++-Code erstellen, die nicht verarbeiten oder öffentliche Windows-Runtime-Typen zu erzeugen und ihn in eine universelle Windows-Plattform-app nutzen. Verwenden Sie die universelle Windows Plattform-DLL-Projekttyp, wenn Sie nur um in dieser Version von Visual Studio kompiliert, aber nicht den Code in ein Windows-Runtime-Komponentenprojekt konvertieren eine vorhandene DLL migrieren möchten. Wenn Sie die folgenden Schritte durchführen, wird die DLL neben Ihrer App bereitgestellt und kann im APPX-Paket ausgeführt werden.  
  
#### <a name="to-create-a-standard-dll-in-visual-studio"></a>Erstellen einer Standard-DLL in Visual Studio  
  
1.  Wählen Sie in der Menüleiste **Datei**, **neu**, **Projekt**, und wählen Sie dann die Vorlage für universelle Windows-Plattform-DLL.  
  
2.  Geben Sie einen Namen für das Projekt ein und wählen Sie dann die Schaltfläche **OK** aus.  
  
3.  Fügen Sie den Code hinzu. Stellen Sie sicher, dass Sie `__declspec(dllexport)` für Funktionen verwenden, die Sie exportieren möchten, z. B. `__declspec(dllexport) Add(int I, in j);`.  
  
4.  Hinzufügen `#include winapifamily.h` , fügen Sie diese Headerdatei aus dem Windows SDK für universelle Windows-Plattform-apps, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
#### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>So verweisen Sie auf ein Standard-DLL-Projekt aus derselben Projektmappe  
  
1.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen** .  
  
2.  Wählen Sie im linken Bereich **Projektmappe**aus, und aktivieren Sie dann das entsprechende Kontrollkästchen im rechten Bereich.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.  
  
#### <a name="to-reference-a-standard-dll-binary"></a>So verweisen Sie auf eine standardmäßige DLL-Binärdatei  
  
1.  Kopieren Sie die DLL-Datei, die LIB-Datei und die Headerdatei. Fügen Sie sie an einem bekannten Speicherort ein, z. B. in den aktuellen Projektordner.  
  
2.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften**aus. Fügen Sie die LIB-Datei auf der Seite **Konfigurationseigenschaften**, **Linker**, **Eingabe** als Abhängigkeit hinzu.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.  
  
#### <a name="to-migrate-an-existing-win32-dll-for-universal-windows-platform-app-compatibility"></a>Migrieren Sie eine vorhandene Win32-DLL für universelle Windows-Plattform-app-Kompatibilität  
  
1.  Erstellen Sie ein Projekt des Typs universelle Windows-Plattform-DLL, und fügen Sie den vorhandenen Quellcode hinzu.  
  
2.  Hinzufügen `#include winapifamily.h` , fügen Sie diese Headerdatei aus dem Windows SDK für universelle Windows-Plattform-apps, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP`.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include` -Anweisung für die DLL-Headerdatei hinzu.  
  

