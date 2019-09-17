---
title: Erstellen von parallelen C/C++-Assemblys
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 6e49ba72a397efb97437a2f7e6d721c782875c48
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493325"
---
# <a name="building-cc-side-by-side-assemblies"></a>Erstellen von parallelen C/C++-Assemblys

Eine parallele [Assembly](/windows/win32/SbsCs/about-side-by-side-assemblies-) ist eine Sammlung von Ressourcen – eine Gruppe von DLLs, Windows-Klassen, com-Servern, Typbibliotheken oder Schnittstellen –, die zur Laufzeit von einer Anwendung verwendet werden können. Der Hauptvorteil der erneuten Paket Erstellung in Assemblys besteht darin, dass mehrere Versionen von Assemblys gleichzeitig von Anwendungen verwendet werden können, und es ist möglich, derzeit installierte Assemblys im Falle einer Update Version zu verarbeiten.

Eine C++ -Anwendung kann eine oder mehrere DLLs in verschiedenen Teilen der Anwendung verwenden. Zur Laufzeit werden die DLLs in den Hauptprozess geladen, und der erforderliche Code wird ausgeführt. Die Anwendung basiert auf dem Betriebssystem, um die angeforderten DLLs zu suchen, zu verstehen, welche anderen abhängigen DLLs geladen werden müssen, und Sie dann zusammen mit der angeforderten dll zu laden. Bei Windows-Betriebssystemen, die älter als Windows XP, Windows Server 2003 und Windows Vista sind, sucht das Betriebssystem-Lade Modul entweder im lokalen Ordner der Anwendung oder in einem anderen Ordner, der im Systempfad angegeben ist, nach abhängigen DLLs. Unter Windows XP, Windows Server 2003 und Windows Vista kann das Betriebssystem-Lade Modul auch mithilfe einer [Manifest](/windows/win32/sbscs/manifests) -Datei nach abhängigen DLLs suchen und nach parallelen Assemblys suchen, die diese DLLs enthalten.

Wenn eine DLL mit Visual Studio erstellt wird, verfügt sie standardmäßig über ein [Anwendungs Manifest](/windows/win32/SbsCs/application-manifests) , das als RT_MANIFEST-Ressource mit der ID 2 eingebettet ist. Ebenso wie bei einer ausführbaren Datei beschreibt dieses Manifest Abhängigkeiten dieser DLL für andere Assemblys. Dabei wird davon ausgegangen, dass die dll nicht Teil einer parallelen Assembly ist, und Anwendungen, die von dieser dll abhängig sind, verwenden kein Anwendungs Manifest, um Sie zu laden, sondern verwenden stattdessen das Betriebssystem-Lade Modul, um diese DLL im Systempfad zu finden.

> [!NOTE]
> Es ist wichtig für eine DLL, die ein Anwendungs Manifest verwendet, damit das Manifest als Ressource mit der ID 2 eingebettet ist. Wenn die dll zur Laufzeit dynamisch geladen wird (z. b. mithilfe der [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) -Funktion), lädt das Betriebssystem-Lade Modul abhängige Assemblys, die im Manifest der DLL angegeben sind. Ein externes Anwendungs Manifest für DLLs wird während eines `LoadLibrary` Aufrufes nicht geprüft. Wenn das Manifest nicht eingebettet ist, versucht das Lade Modul möglicherweise, falsche Versionen von Assemblys zu laden, oder es kann nicht nach abhängigen Assemblys suchen.

Eine oder mehrere verknüpfte DLLs können mit einem entsprechenden [Assemblymanifest](/windows/win32/SbsCs/assembly-manifests) in eine parallele Assembly umgepackt werden. Darin werden die Dateien, die die Assembly bilden, sowie die Abhängigkeit der Assembly zu anderen parallelen Assemblys beschrieben.

> [!NOTE]
> Wenn eine Assembly eine DLL enthält, empfiehlt es sich, das Assemblymanifest in diese DLL als Ressource mit der ID 1 einzubetten und der private Assembly den gleichen Namen wie die dll zu übergeben. Wenn der Name der DLL z. b. MyLibrary. dll lautet, kann der Wert des Namens Attributs, das \<im Element assemblyIdentity > des Manifests verwendet wird, auch MyLibrary lauten. In einigen Fällen kann ein externes Assemblymanifest erstellt werden, wenn eine Bibliothek eine andere Erweiterung als die dll aufweist (z. b. ein MFC-ActiveX-Steuerelement Projekt, das eine OCX-Bibliothek erstellt). In diesem Fall müssen sich der Name der Assembly und des zugehörigen Manifests von dem Namen der DLL unterscheiden (z. b. myAssembly, MyAssembly. Manifest und MyLibrary. ocx). Es wird jedoch weiterhin empfohlen, solche Bibliotheken so umzubenennen, dass Sie die Erweiterung ". dll" aufweisen, und das Manifest als Ressource einbetten, um die zukünftigen Wartungskosten dieser Assembly zu verringern. Weitere Informationen zum Suchen von privaten Assemblys durch das Betriebssystem finden Sie unter [Assemblysuchsequenz](/windows/win32/SbsCs/assembly-searching-sequence).

Diese Änderung kann die Bereitstellung entsprechender DLLs als [private Assembly](/windows/win32/Msi/private-assemblies) in einem lokalen Anwendungsordner oder als frei [gegebene Assembly](/windows/win32/Msi/shared-assemblies) im WinSxS-Assemblycache ermöglichen. Es müssen mehrere Schritte ausgeführt werden, um das richtige Laufzeitverhalten dieser neuen Assembly zu erzielen. Sie werden in [Richtlinien zum Erstellen](/windows/win32/SbsCs/guidelines-for-creating-side-by-side-assemblies)paralleler Assemblys beschrieben. Nachdem eine Assembly ordnungsgemäß erstellt wurde, kann Sie entweder als freigegeben oder private Assembly gemeinsam mit einer Anwendung bereitgestellt werden, die von ihr abhängt. Bei der Installation paralleler Assemblys als freigegebene Assembly können Sie entweder die unter Installieren von Win32-Assemblys für die parallele [Freigabe unter Windows XP](/windows/win32/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) und Verwenden von [Mergemodulen](/windows/win32/msi/merge-modules)beschriebenen Richtlinien befolgen. Wenn Sie parallele Assemblys als private Assembly installieren, können Sie die entsprechende dll, Ressourcen und das Assemblymanifest als Teil des Installationsvorgangs in den lokalen Anwendungsordner auf dem Zielcomputer kopieren und sicherstellen, dass diese Assembly gefunden durch das Lade Modul zur Laufzeit (siehe [Assemblysuchsequenz](/windows/win32/SbsCs/assembly-searching-sequence)). Eine andere Möglichkeit ist die Verwendung von [Windows Installer](/windows/win32/Msi/windows-installer-portal) und den Richtlinien, die unter Installieren von Win32-Assemblys [für die private Verwendung einer Anwendung unter Windows XP](/windows/win32/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)beschrieben werden.

## <a name="see-also"></a>Siehe auch

[Erstellen isolierter C/C++-Anwendungen](building-c-cpp-isolated-applications.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
