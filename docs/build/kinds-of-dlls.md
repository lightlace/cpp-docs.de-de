---
title: Arten von DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: daf042f742a9c4b7757813fc73eeb4b6d1a87413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441118"
---
# <a name="kinds-of-dlls"></a>Arten von DLLs

Anhand der Informationen unter diesem Thema können Sie feststellen, welche Art von DLL erstellt werden sollte.

##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> Verschiedene Arten von DLLs zur Verfügung

Mit Visual C++ können Sie Win32-DLLs in C oder C++ erstellen, die nicht die MFC-Bibliothek (Microsoft Foundation Class Library) verwenden. Um ein MFC-fremdes DLL-Projekt zu erstellen, verwenden Sie den Win32-Anwendungs-Assistenten.

Die MFC-Bibliothek selbst ist über den MFC-DLL-Assistenten entweder in Static Link Libraries oder in einer Reihe von DLLs verfügbar. Wenn die DLL MFC verwendet, unterstützt Visual C++ drei verschiedene Szenarien für die DLL-Entwicklung:

- Erstellen einer reguläres MFC-DLL, die statisch mit MFC verknüpft wird

- Erstellen einer reguläres MFC-DLL, die dynamisch mit MFC verknüpft wird

- Erstellen einer MFC-Erweiterungs-DLL, die immer dynamisch mit MFC verknüpft wird

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [MFC-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)

- [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)

- [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC extension DLLs: Overview (MFC-Erweiterungs-DLLs: Übersicht)](../build/extension-dlls-overview.md)

- [Welche Art von DLL verwenden](#_core_which_kind_of_dll_to_use)

##  <a name="_core_which_kind_of_dll_to_use"></a> Entscheiden, welche Art von DLL verwendet

Wenn die DLL nicht MFC verwendet, erstellen Sie mit Visual C++ eine MFC-fremde Win32-DLL. Das (statische oder dynamische) Verknüpfen einer DLL mit MFC beansprucht erhebliche Festplattenspeicher- und Arbeitsspeicherkapazitäten. Sie sollten eine Verknüpfung mit MFC nur dann vorsehen, wenn MFC von der DLL auch tatsächlich verwendet wird.

Wenn die DLL MFC verwenden und entweder MFC oder MFC-fremden Anwendungen verwendet werden, müssen Sie erstellen entweder eine reguläre MFC-DLL, die dynamisch mit MFC verknüpft oder eine reguläre MFC-DLL, die statisch mit MFC verknüpft wird. In den meisten Fällen möchten Sie wahrscheinlich auch eine reguläre MFC-DLL zu verwenden, die dynamisch mit MFC verknüpft wird, da die Dateigröße der DLL wird wesentlich kleiner ist und die einsparungen im Arbeitsspeicher verwenden Sie die freigegebene Version von MFC können erheblich sein. Bei einer statischen Verknüpfung mit MFC wird die DLL größer, und es wird möglicherweise mehr Arbeitsspeicher benötigt, da eine eigene Kopie des MFC-Bibliothekscodes geladen wird.

Das Erstellen einer DLL, die dynamisch mit MFC verknüpft wird, verläuft schneller als das Erstellen einer DLL, die statisch mit MFC verknüpft wird, da MFC selbst in diesem Fall nicht verknüpft werden muss. Dies trifft insbesondere auf Debugbuilds zu, bei denen der Linker die Debuginformationen komprimieren muss. Durch das Verknüpfen mit einer DLL, die bereits Debuginformationen enthält, bleiben innerhalb der DLL weniger Debuginformationen zu komprimieren.

Ein Nachteil der dynamischen Verknüpfung mit MFC besteht darin, dass Sie die gemeinsam genutzten DLLs, nämlich Mfcx0.dll und Msvcrxx.dll (oder ähnliche Dateien), zusammen mit der DLL verteilen müssen. Die MFC-DLLs können frei verteilt werden, sie müssen jedoch noch im Setupprogramm installiert werden. Darüber hinaus müssen Sie Msvcrxx.dll mitliefern. Diese Datei enthält die C-Laufzeitbibliothek, die sowohl vom Programm als auch von den MFC-DLLs selbst verwendet wird.

Wenn Ihre DLL nur von ausführbaren MFC-Dateien verwendet wird, müssen Sie die Wahl zwischen dem Erstellen einer regulären MFC-DLL oder eine MFC-Erweiterungs-DLL. Wenn Ihre DLL, wiederverwendbare Klassen von bestehenden MFC-Klassen abgeleitet implementiert oder MFC abgeleitete Objekte zwischen Anwendung und DLL übergeben werden müssen, müssen Sie eine MFC-Erweiterungs-DLL erstellen.

Wenn die DLL dynamisch mit MFC verknüpft wird, können die MFC-DLLs zusammen mit der DLL verteilt werden. Diese Architektur ist besonders geeignet, wenn die Klassenbibliothek von mehreren ausführbaren Dateien gemeinsam genutzt wird, um Festplattenspeicher zu sparen und die Arbeitsspeicherauslastung zu minimieren.

Vor Version 4.0 unterstützte Visual C++ nur zwei Arten von DLLs, die MFC verwendeten: USRDLLs und AFXDLLs. Reguläre, statisch mit MFC verknüpfte MFC-DLLs haben dieselben Merkmale wie die frühere USRDLL. MFC-Erweiterungs-DLLs haben dieselben Merkmale wie die früheren AFXDLLs.

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [MFC-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)

- [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)

- [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC extension DLLs: Overview (MFC-Erweiterungs-DLLs: Übersicht)](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](../build/dlls-in-visual-cpp.md)