---
title: Erstellen von parallelen C/C++-Assemblys
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 037fde58366ea4548ce3c7ff56c38cfc1a58aa17
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195143"
---
# <a name="building-cc-side-by-side-assemblies"></a>Erstellen von parallelen C/C++-Assemblys

Ein [Seite-an-Seite-Assembly](/windows/desktop/SbsCs/about-side-by-side-assemblies-) ist eine Sammlung von Ressourcen – eine Gruppe von DLLs, Windows-Klassen, COM-Servern, Typbibliotheken oder Schnittstellen – für eine Anwendung für die Verwendung zur Laufzeit verfügbar. Der wichtigste Vorteil von Neuverpacken von DLLs in Assemblys ist, dass mehrere Versionen der Assemblys von Anwendungen gleichzeitig verwendet werden können, und es möglich, den, der derzeit installierten Dienstassemblys im Falle einer Updateversion ist.

Visual C++-Anwendung kann eine oder mehrere DLLs in verschiedenen Teilen der Anwendung verwenden. Zur Laufzeit die DLLs sind in der zentrale Prozess geladen, und der erforderliche Code ausgeführt wird. Die Anwendung basiert auf dem Betriebssystem, suchen Sie die angeforderten DLLs, zu verstehen, habe anderen abhängigen DLLs geladen werden, und Laden Sie diese dann zusammen mit den angeforderten-DLL. Auf Windows-Betriebssystemversionen sucht älter als Windows XP, Windows Server 2003 und Windows Vista, vom Ladeprogramm des Betriebssystems abhängigen DLLs im lokalen Ordner der Anwendung oder einen anderen Ordner auf dem Systempfad angegeben. Auf Windows XP, Windows Server 2003 und Windows Vista, kann vom Ladeprogramm des Betriebssystems auch nach abhängigen DLLs, die mithilfe von suchen eine [manifest](/windows/desktop/sbscs/manifests) -Datei, und suchen Sie für Seite-an-Seite-Assemblys, die diese DLLs enthalten.

Standardmäßig, wenn eine DLL, mit Visual Studio erstellt wird hat ein [Anwendungsmanifest](/windows/desktop/SbsCs/application-manifests) eingebettet als Ressource "RT_MANIFEST" mit der ID gleich 2. Genau wie bei einer ausführbaren Datei beschreibt dieses Manifest diese DLL-Abhängigkeiten von anderen Assemblys. Dies setzt voraus, dass die DLL nicht Teil einer Seite-an-Seite-Assembly ist und Anwendungen, die diese DLL abhängig sind nicht für das ein Anwendungsmanifest zu laden, aber verwenden stattdessen auf das Ladeprogramm des Betriebssystems finden Sie diese DLL-Datei unter dem Systempfad verwenden möchte.

> [!NOTE]
> Es ist wichtig für eine DLL, die ein Anwendungsmanifest verwendet, um das Manifest als Ressource eingebettet ist, mit der ID gleich 2 zu erhalten. Wenn die DLL zur Laufzeit dynamisch geladen wird (z. B. die [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya) Funktion), vom Ladeprogramm des Betriebssystems lädt die abhängigen Assemblys, die im Manifest der DLL angegeben. Ein externes Anwendungsmanifest für DLLs nicht aktiviert ist, während eine `LoadLibrary` aufrufen. Wenn das Manifest nicht eingebettet werden, das Ladeprogramm möglicherweise falsche Versionen von Assemblys zu laden oder Fehler beim abhängigen Assemblys finden.

Eine oder mehrere bezogene DLLs können neu verpackt werden, in eine Seite-an-Seite-Assembly mit einem entsprechenden [Assemblymanifest](/windows/desktop/SbsCs/assembly-manifests), das beschreibt, welche Dateien der Assembly als auch die Abhängigkeit von der Assembly auf der anderen Seite-an-Seite bilden Assemblys.

> [!NOTE]
> Wenn eine Assembly eine DLL enthält, wird empfohlen, die das Assemblymanifest als Ressource mit der ID gleich 1 ist in dieser DLL-Datei einzubetten, und geben Sie den gleichen Namen wie die DLL der privaten Assembly. Beispielsweise ist der Name der DLL "MyLibrary.dll", der Wert des Namensattributs in verwendet die \<AssemblyIdentity >-Element des Manifests möglicherweise auch Mylibrary. In einigen Fällen, wenn eine Bibliothek mit eine anderen Erweiterung als DLL aufweist (z. B. für ein Projekt für die MFC-ActiveX-Steuerelementen erstellt eine OCX-Bibliothek) kann ein externes Manifest erstellt werden. In diesem Fall muss der Name der Assembly und das Manifest den Namen der DLL (z. B. MyAssembly, MyAssembly.manifest und mylibrary.ocx) abweichen. Es jedoch immer noch empfohlen wird, benennen Sie diese Bibliotheken haben die Erweiterung.dll zu verleihen, und das Manifest als Ressource zur Reduzierung der Kosten zukünftige Verwaltung dieser Assembly einzubetten. Weitere Informationen darüber, wie das Betriebssystem nach privaten Assemblys sucht, finden Sie unter [Assemblysuchsequenz](/windows/desktop/SbsCs/assembly-searching-sequence).

Diese Änderung können die Bereitstellung der entsprechenden DLLs als eine [private Assembly](/windows/desktop/Msi/private-assemblies) im lokalen Anwendungsordner oder als eine [freigegebene Assembly](/windows/desktop/Msi/shared-assemblies) in WinSxS-Assemblycache. Es müssen verschiedene Schritte befolgt werden, um die korrekte Laufzeitverhalten diese neue Assembly zu erreichen. Sie werden beschrieben [Richtlinien für die Seite-an-Seite-Assemblys erstellen](/windows/desktop/SbsCs/guidelines-for-creating-side-by-side-assemblies). Nachdem eine Assembly richtig erstellt wurde können es bereitgestellt als entweder freigegeben oder privat Assembly zusammen mit einer Anwendung, die von ihr abhängig ist. Beim Installieren von Seite-an-Seite-Assemblys als freigegebene Assembly kann entweder die Richtlinien folgen in [Installieren von Win32-Assemblys für die Seite-an-Seite-Freigabe unter Windows XP](/windows/desktop/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) oder [Mergemodule](/windows/desktop/msi/merge-modules). Beim Side-by-Side Assemblys als private Assembly installieren, können Sie einfach Kopieren der entsprechenden DLL, Ressourcen und das Assemblymanifest im Rahmen des Installationsvorgangs auf den lokalen Ordner der Anwendung auf dem Zielcomputer, um sicherzustellen, dass diese Assembly sein kann durch das Ladeprogramm zur Laufzeit gefunden (finden Sie unter [Assemblysuchsequenz](/windows/desktop/SbsCs/assembly-searching-sequence)). Eine weitere Möglichkeit ist die Verwendung [Windows Installer](/windows/desktop/Msi/windows-installer-portal) , und befolgen Sie die Richtlinien unter [Installieren von Win32-Assemblys für die Private Nutzung einer Anwendung unter Windows XP](/windows/desktop/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp).

## <a name="see-also"></a>Siehe auch

[Erstellen isolierter C/C++-Anwendungen](building-c-cpp-isolated-applications.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
