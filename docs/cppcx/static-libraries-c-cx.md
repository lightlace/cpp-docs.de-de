---
title: Statische Bibliotheken (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb69b65d78b6369d872fd6f953f6ddde382c21b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759443"
---
# <a name="static-libraries-ccx"></a>Statische Bibliotheken (C++/CX)
Eine statische Bibliothek, die in einer app (Universelle Windows Plattform) verwendet wird, kann ISO-Standard C++-Code, einschließlich der STL-Typen, und außerdem Aufrufe für Win32-APIs, die von der Windows-Runtime-app-Plattform nicht ausgeschlossen sind enthalten. Eine statische Bibliothek nutzt Windows-Runtime-Komponenten und kann Windows-Runtime-Komponenten mit bestimmten Einschränkungen erstellen.  
  
## <a name="creating-static-libraries"></a>Erstellen von statischen Bibliotheken  
  
#### <a name="to-create-a-static-library-for-use-in-a-uwp-app"></a>Erstellen Sie eine statische Bibliothek für die Verwendung in einer UWP-app  
  
1.  Klicken Sie in der Menüleiste auf **Datei** > **Neu** > **Projekt**. Klicken Sie unter **Visual C++** > **Windows Universal** wählen **statische Bibliothek (Universal Windows)**.  
  
2.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus. In der **Eigenschaften** Dialogfeld auf die **Konfigurationseigenschaften** > **C/C++-** Seite **Nutzen von Windows Runtime-Erweiterung** zu **Ja (/ Zw)**.  
  
 Wenn Sie eine neue statische Bibliothek kompilieren, wenn Sie eine Win32-API aufrufen, die für UWP-apps ausgeschlossen wird, löst der Compiler Fehler C3861 aus, die "Bezeichner wurde nicht gefunden." Suchen Sie nach einer alternativen Methode, die für die Windows-Runtime unterstützt wird, finden Sie unter [Alternativen zu Windows-APIs in UWP-apps](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).  
  
 Wenn Sie eine UWP-app-Projektmappe ein statisches C++-Bibliotheksprojekt hinzufügen, müssen Sie möglicherweise eigenschafteneinstellungen des Bibliotheksprojekts aktualisieren, damit die UWP-Support-Eigenschaft festgelegt ist, um **Ja**. Der Code aufgebaut und verknüpft, jedoch ein Fehler tritt auf, wenn Sie versuchen, die app für den Microsoft Store zu überprüfen, ohne diese Einstellung. Die statische Bibliothek sollte mit den gleichen Compilereinstellungen wie das Projekt kompiliert werden, in dem sie verwendet werden.  
  
 Wenn Sie eine statische Bibliothek nutzen, die öffentliche `ref` -Klassen, öffentliche Schnittstellenklassen oder öffentliche Wertklassen erstellt, gibt der Linker folgende Warnung aus:  
  
> **Warnung LNK4264:** in einer statischen Bibliothek; mit/zw kompilierte Objektdatei wird archiviert Beachten Sie, dass beim Erstellen von Windows-Runtime-Typen nicht empfohlen wird, mit einer statischen Bibliothek verknüpft werden, die Windows-Runtime-Metadaten enthält.  
  
 Sie können die Warnung ignorieren, wenn die statische Bibliothek nicht-Windows-Runtime-Komponenten erstellt, die außerhalb der Bibliothek selbst genutzt werden. Wenn die Bibliothek keine Komponenten verwendet, die sie definiert, kann der Linker die Implementierung optimieren, obwohl die öffentlichen Metadaten die Typinformationen enthalten. Das bedeutet, dass öffentliche Komponenten in einer statischen Bibliothek kompiliert, aber nicht zur Laufzeit aktiviert werden. Aus diesem Grund muss jede Komponente des Windows-Runtime, die für die Nutzung vorgesehen ist, von anderen Komponenten oder apps in einer Dynamic Link Library (DLL) implementiert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading und Marshalling](../cppcx/threading-and-marshaling-c-cx.md)