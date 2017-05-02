---
title: "DLLs (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 21
---
# DLLs (C++/CX)
Sie können Visual Studio verwenden, um entweder eine standardmäßige Win32\-DLL oder eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-DLL\-Komponente zu erstellen, die von [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps genutzt werden kann. Eine Standard\-DLL, die mit einer Version von Visual Studio oder mit dem Visual C\+\+\-Compilers aus der Zeit vor [!INCLUDE[vs_dev11_long](../cppcx/includes/vs-dev11-long-md.md)] erstellt wurde, wird in einer [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App möglicherweise nicht ordnungsgemäß geladen und besteht möglicherweise den App\-Überprüfungstest im [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)] nicht.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten\-DLLs  
 In fast allen Fällen, in denen Sie eine DLL für eine [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App erstellen möchten, erstellen Sie sie als [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente, indem Sie die Projektvorlage dieses Namens verwenden. Sie können ein [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponentenprojekt für DLLs erstellen, die öffentliche oder private [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen besitzen. Auf eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente kann von Apps zugegriffen werden, die in einer zu [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-kompatiblen Sprache geschrieben sind. Standardmäßig verwenden die Compilereinstellungen für ein [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponentenprojekt den **\/ZW**\-Schalter. Eine WinMD\-Datei muss denselben Namen wie der Stammnamespace haben. Zum Beispiel kann eine Klasse namens A.B.C.MyClass nur instanziiert werden, wenn sie in einer Metadatendatei definiert ist, die A.winmd oder A.B.winmd oder A.B.C.winmd heißt. Der Name der DLL muss nicht mit dem Namen der WINMD\-Datei übereinstimmen.  
  
 Weitere Informationen finden Sie unter [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
#### So verweisen Sie in Ihrem Projekt auf eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten\-Binärdatei eines Drittanbieters  
  
1.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften** aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen**.  
  
2.  Eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente besteht aus einer DLL\- und einer WINMD\-Datei, die die Metadaten enthält. In der Regel sind diese Dateien im selben Ordner. Klicken Sie im linken Bereich des Dialogfelds **Verweis hinzufügen** auf die Schaltfläche **Durchsuchen**, und navigieren Sie dann zum Speicherort der DLL und der WINMD\-Datei. Weitere Informationen finden Sie unter [Tutorial: Erstellen und Verwenden von Erweiterungs\-SDKs](http://msdn.microsoft.com/de-de/001e2fca-3d56-43ab-a5e0-0561d085679f).  
  
## Standard\-DLLs  
 Sie können eine Standard\-DLL für C\+\+\-Code erstellen, der keine öffentlichen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen nutzt oder erzeugt und dafür die [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App verwenden. Nutzen Sie den [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-DLL\-Projekttyp, wenn Sie nur eine vorhandene DLL migrieren möchten, um diese in diese Visual Studio\-Version zu kompilieren und den Code nicht in ein Windows\-Runtime\-Komponentenprojekt konvertieren möchten. Wenn Sie die folgenden Schritte durchführen, wird die DLL neben Ihrer App bereitgestellt und kann im APPX\-Paket ausgeführt werden.  
  
#### Erstellen einer Standard\-DLL in Visual Studio  
  
1.  Wählen Sie auf der Menüleiste **Datei**, **Neu**, **Projekt** und dann die [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-DLL\-Vorlage.  
  
2.  Geben Sie einen Namen für das Projekt ein und wählen Sie dann die Schaltfläche **OK** aus.  
  
3.  Fügen Sie den Code hinzu. Stellen Sie sicher, dass Sie `__declspec(dllexport)` für Funktionen verwenden, die Sie exportieren möchten, z. B. `__declspec(dllexport) Add(int I, in j);`.  
  
4.  Fügen Sie `#include winapifamily.h` hinzu, um diese Headerdatei aus dem Windows SDK für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps einzuschließen, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP` fest.  
  
#### So verweisen Sie auf ein Standard\-DLL\-Projekt aus derselben Projektmappe  
  
1.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften** aus. Klicken Sie auf der Seite **Allgemeine Eigenschaften** auf die Schaltfläche **Neuen Verweis hinzufügen**.  
  
2.  Wählen Sie im linken Bereich **Projektmappe** aus, und aktivieren Sie dann das entsprechende Kontrollkästchen im rechten Bereich.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include`\-Anweisung für die DLL\-Headerdatei hinzu.  
  
#### So verweisen Sie auf eine standardmäßige DLL\-Binärdatei  
  
1.  Kopieren Sie die DLL\-Datei, die LIB\-Datei und die Headerdatei. Fügen Sie sie an einem bekannten Speicherort ein, z. B. in den aktuellen Projektordner.  
  
2.  Öffnen Sie das Kontextmenü für das Projekt, das die DLL verwendet, und wählen Sie dann **Eigenschaften** aus. Fügen Sie die LIB\-Datei auf der Seite **Konfigurationseigenschaften**, **Linker**, **Eingabe** als Abhängigkeit hinzu.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include`\-Anweisung für die DLL\-Headerdatei hinzu.  
  
#### So migrieren Sie eine vorhandene Win32\-DLL zur Kompatibilität mit [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps  
  
1.  Erstellen Sie ein Projekt vom [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-DLL\-Typ, und fügen Sie den vorhandenen Quellcode hinzu.  
  
2.  Fügen Sie `#include winapifamily.h` hinzu, um diese Headerdatei aus dem Windows SDK für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps einzuschließen, und legen Sie das Makro `WINAPI_FAMILY=WINAPI_PARTITION_APP` fest.  
  
3.  Fügen Sie nötigenfalls in den Quellcodedateien eine `#include`\-Anweisung für die DLL\-Headerdatei hinzu.  
  
## Siehe auch  
 [\(NOTINBUILD\) Weiterführende Themen](http://msdn.microsoft.com/de-de/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)