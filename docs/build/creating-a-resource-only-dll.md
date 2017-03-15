---
title: "Erstellen einer DLL als reine Ressource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Erstellen"
  - "Nur-Ressourcen-DLLs [C++], Erstellen"
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erstellen einer DLL als reine Ressource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine reine Ressourcen\-DLL ist eine DLL, die ausschließlich Ressourcen enthält, z. B. Symbole, Bitmaps, Zeichenfolgen und Dialogfelder.  Die Verwendung einer reinen Ressourcen\-DLL bietet eine gute Möglichkeit, dieselben Ressourcen von mehreren Programmen gemeinsam nutzen zu lassen.  Sie ist außerdem von Vorteil, wenn für eine Anwendung in mehreren Sprachen lokalisierte Ressourcen bereitgestellt werden sollen \(siehe [Lokalisierte Ressourcen in MFC\-Anwendungen: Satelliten\-DLLs](../build/localized-resources-in-mfc-applications-satellite-dlls.md)\).  
  
 Um eine reine Ressourcen\-DLL zu erstellen, erstellen Sie ein neues Win32\-DLL\-Projekt \(MFC\-fremd\) und fügen dem Projekt die Ressourcen hinzu.  
  
-   Wählen Sie im Dialogfeld **Neues Projekt** die Option Win32\-Projekt aus, und legen Sie im Win32\-Projekt\-Assistenten einen DLL\-Projekttyp fest.  
  
-   Erstellen Sie für die DLL ein neues Ressourcenskript, das die Ressourcen \(z. B. eine Zeichenfolge oder ein Menü\) enthält, und speichern Sie es als RC\-Datei.  
  
-   Wählen Sie im Menü **Projekt** die Option **Vorhandenes Element hinzufügen**, und fügen Sie dann die neue RC\-Datei in das Projekt ein.  
  
-   Legen Sie die [\/NOENTRY](../build/reference/noentry-no-entry-point.md)\-Linkeroption fest. **\/NOENTRY** verhindert, dass der Linker einen Verweis auf **\_main** in die DLL einfügt. Diese Option ist erforderlich, um eine reine Ressourcen\-DLL zu erstellen.  
  
-   Erstellen Sie die DLL.  
  
 Die Anwendung, die die reine Ressourcen\-DLL verwendet, sollte **LoadLibrary** aufrufen, um eine [explizite Verknüpfung mit der DLL zu erstellen](../build/loadlibrary-and-afxloadlibrary.md).  Um auf die Ressourcen zuzugreifen, rufen Sie die generischen Funktionen **FindResource** und **LoadResource** auf, die für jeden beliebigen Ressourcentyp verwendet werden können. Alternativ können Sie eine der folgenden ressourcenspezifischen Funktionen aufrufen:  
  
-   `FormatMessage`  
  
-   **LoadAccelerators**  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
 Die Anwendung sollte **FreeLibrary** aufrufen, sobald die Ressourcen nicht mehr benötigt werden.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [DELETE\_PENDING\_Editing Resources](assetId:///c29d31c7-2d94-40ca-8aa0-c7262883529c)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)