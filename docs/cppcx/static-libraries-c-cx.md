---
title: Statische Bibliotheken (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a68475447ed520298b0eab7949386c2e8d078ac6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="static-libraries-ccx"></a>Statische Bibliotheken (C++/CX)
Eine statische Bibliothek, die in einer universellen Windows-Plattform-app verwendet wird, kann ISO-Standard C++-Code, einschließlich der STL-Typen und außerdem Aufrufe für Win32-APIs, die nicht von der universellen Windows-Plattform-app-Plattform ausgeschlossen sind enthalten. Eine statische Bibliothek nutzt Windows-Runtime-Komponenten und kann Windows-Runtime-Komponenten mit bestimmten Einschränkungen erstellen.  
  
## <a name="creating-static-libraries"></a>Erstellen von statischen Bibliotheken  
  
#### <a name="to-create-a-static-library-for-use-in-a-universal-windows-platform-app"></a>So erstellen Sie eine statische Bibliothek zur Verwendung in einer universellen Windows-Plattform-app  
  
1.  Wählen Sie in der Menüleiste **Datei** > **neu** > **Projekt** > **leere statische Bibliothek** für universelle Windows Plattform-apps.  
  
2.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus. In der **Eigenschaften** Dialogfeld auf die **Konfigurationseigenschaften** > **allgemeine** Seite, legen Sie universelle Windows-Plattform-app-Unterstützung auf  **Ja**.  
  
3.  Auf der **Konfigurationseigenschaften** > **C/C++-** Seite **verbrauchen** Windows-Runtime **Erweiterung** auf **Ja (/ Zw)**.  
  
 Wenn Sie eine neue statische Bibliothek kompiliert, wenn Sie einen Aufruf an eine Win32-API ausführen, die für die universelle Windows-Plattform-apps ausgeschlossen ist, löst der Compiler Fehler C3861 aus, die "Bezeichner wurde nicht gefunden." Um nach einer alternativen Methode zu suchen, die für die Windows-Runtime unterstützt wird, finden Sie unter [Alternativen zu Windows-APIs in Windows Store-apps](http://msdn.microsoft.com/en-us/75568012-61e0-41cc-a4df-c698f54f21ec).  
  
 Wenn Sie eine universelle Windows-Plattform-app-Projektmappe ein statisches C++-Bibliotheksprojekt hinzufügen, müssen Sie möglicherweise eigenschafteneinstellungen des Bibliotheksprojekts aktualisieren, sodass die universelle Windows-Plattform-Support-Eigenschaft, um festgelegt ist **Ja**. Ohne diese Einstellung wird der Code aufgebaut und verknüpft, jedoch tritt ein Fehler auf, wenn Sie versuchen, die App für [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]zu überprüfen. Die statische Bibliothek sollte mit den gleichen Compilereinstellungen wie das Projekt kompiliert werden, in dem sie verwendet werden.  
  
 Wenn Sie eine statische Bibliothek nutzen, die öffentliche `ref` -Klassen, öffentliche Schnittstellenklassen oder öffentliche Wertklassen erstellt, gibt der Linker folgende Warnung aus:  
  
> **Warnung LNK4264:** archivieren, die in einer statischen Bibliothek archiviert mit/zw kompilierte Objektdatei Beachten Sie, dass beim Erstellen von Windows-Runtime-Typen nicht empfohlen wird, mit einer statischen Bibliothek verknüpft werden, die Windows-Runtime-Metadaten enthält.  
  
 Sie können die Warnung sicher ignorieren, nur, wenn die statische Bibliothek nicht-Windows-Runtime-Komponenten erzeugt, die außerhalb der Bibliothek selbst genutzt werden. Wenn die Bibliothek keine Komponenten verwendet, die sie definiert, kann der Linker die Implementierung optimieren, obwohl die öffentlichen Metadaten die Typinformationen enthalten. Das bedeutet, dass öffentliche Komponenten in einer statischen Bibliothek kompiliert, aber nicht zur Laufzeit aktiviert werden. Aus diesem Grund muss jede Windows-Runtime-Komponente, die für die Nutzung vorgesehen ist, von anderen Komponenten oder apps in einer Dynamic Link Library (DLL) implementiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)