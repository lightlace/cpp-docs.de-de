---
title: "Statische Bibliotheken (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Statische Bibliotheken (C++/CX)
Eine statische Bibliothek, die in einer [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App verwendet wird, kann C\+\+\-Code im ISO\-Standard inklusive STL\-Typen und außerdem Aufrufe für Win32\-APIs enthalten, die nicht nicht von der Plattform der [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App ausgeschlossen sind. Eine statische Bibliothek nutzt [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten und erstellt möglicherweise [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten mit bestimmten Einschränkungen.  
  
## Erstellen von statischen Bibliotheken  
  
#### So erstellen Sie eine statische Bibliothek zur Verwendung in einer [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App  
  
1.  Wählen Sie in der Menüleiste **Datei** \> **Neu** \> **Projekt** \> **Leere statische Bibliothek** für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps aus.  
  
2.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus. Legen Sie im Dialogfeld **Eigenschaften** auf der Seite **Konfigurationseigenschaften** \> **Allgemein** die [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App\-Unterstützung auf **Ja** fest.  
  
3.  Legen Sie auf der Seite **Konfigurationseigenschaften** \> **C\/C\+\+** die Option **Nutzung der**[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]**\-Erweiterung** auf **Ja \(\/ZW\)** fest.  
  
 Wenn Sie beim Kompilieren einer neuen statischen Bibliothek einen Aufruf an eine Win32\-API ausführen, die für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps ausgeschlossen ist, löst der Compiler Fehler C3861 aus \(„Bezeichner wurde nicht gefunden“\). Informationen zur Suche nach einer alternativen Methode, die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützt, finden Sie unter [Alternatives to Windows APIs in Windows Store apps](http://msdn.microsoft.com/de-de/75568012-61e0-41cc-a4df-c698f54f21ec).  
  
 Wenn Sie einer [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App\-Projektmappe ein statisches C\+\+\-Bibliotheksprojekt hinzufügen, müssen Sie möglicherweise die Eigenschafteneinstellungen des Bibliotheksprojekts aktualisieren, damit die support\-Eigenschaft für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] auf **Ja** festgelegt ist. Ohne diese Einstellung wird der Code aufgebaut und verknüpft, jedoch tritt ein Fehler auf, wenn Sie versuchen, die App für [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)] zu überprüfen. Die statische Bibliothek sollte mit den gleichen Compilereinstellungen wie das Projekt kompiliert werden, in dem sie verwendet werden.  
  
 Wenn Sie eine statische Bibliothek nutzen, die öffentliche `ref`\-Klassen, öffentliche Schnittstellenklassen oder öffentliche Wertklassen erstellt, gibt der Linker folgende Warnung aus:  
  
> **warning LNK4264:** Mit \/ZW kompilierte Objektdatei wird in einer statischen Bibliothek archiviert. Beachten Sie, dass beim Erstellen von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen das Verknüpfen mit einer statischen Bibliothek, die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Metadaten enthält, nicht empfohlen wird.  
  
 Sie können die Warnung nur gefahrlos ignorieren, wenn die statische Bibliothek keine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten erzeugt, die außerhalb der Bibliothek selbst genutzt werden. Wenn die Bibliothek keine Komponenten verwendet, die sie definiert, kann der Linker die Implementierung optimieren, obwohl die öffentlichen Metadaten die Typinformationen enthalten. Das bedeutet, dass öffentliche Komponenten in einer statischen Bibliothek kompiliert, aber nicht zur Laufzeit aktiviert werden. Aus diesem Grund muss jede [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente, die für die Nutzung durch andere Komponenten oder Apps vorgesehen ist, in einer DLL \(Dynamic Link Library\) implementiert werden.  
  
## Siehe auch  
 [Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)