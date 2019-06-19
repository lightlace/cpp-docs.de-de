---
title: Zusammenarbeit mit Live Share für C++ in Visual Studio
description: Verwenden Sie Live Share für C++ in Visual Studio, um Code in Echtzeit zu bearbeiten und zu teilen.
ms.date: 05/24/2019
ms.openlocfilehash: 8886bb3ea4b7389a9d6953655e2dc6ccfa1c7c9a
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66742066"
---
# <a name="collaborate-using-live-share-for-c"></a>Zusammenarbeiten mithilfe von Live Share für C++

In Visual Studio 2019 und Visual Studio Code können Sie **Live Share** für die Zusammenarbeit an C++-Projekten in Echtzeit verwenden. Mit **Live Share** kann eine andere Person Ihren Code bearbeiten und debuggen ohne Ihr Projekt oder die zugehörigen Abhängigkeiten zu installieren. Die Bearbeitungen des Anderen werden angezeigt, und jede Bearbeitung wird mit dem Namen der Person markiert, die die Veränderung vorgenommen hat. 

![C&#43;&#43; Live Share-Bearbeitung](../ide/media/live-share-edit-cpp.png "Live Share-Bearbeitung in C++")

## <a name="live-share-host-and-guests"></a>Live Share-Gastgeber und -Gäste

In einer Live Share-Sitzung gibt es einen Gastgeber und mindestens einen Gast. Sowohl der Gastgeber als auch die Gäste können entweder Visual Studio oder Visual Studio Code verwenden. Ein Visual Studio 2019-Gastgeber unter Windows kann nun Inhalte mit einem Visual Studio Code-Gast unter Linux teilen.

Der Gastgeber bietet dem Gast alles, was dieser benötigt, um produktiv zu sein. Gäste müssen nicht über den Quellcode, Compiler, externe Abhängigkeiten oder die gleichen installierten Komponenten verfügen. 

Der Gastgeber und die Gäste können diese IntelliSense-Funktionen verwenden: 

- Memberliste
- Parameterhilfe
- QuickInfo
- Debuggen/Breakpoints
- Alle Verweise suchen
- Gehe zu Definition
- Symbolsuche (STRG+T)
- Markieren von Verweisen
- Diagnose/Fehler/Wellenlinien

![C&#43;&#43; Debuggen mit Live Share](../ide/media/live-share-debug-cpp.png "Debuggen mit Live Share in C++")

## <a name="start-and-end-a-live-share-session"></a>Starten und Beenden einer Live Share-Sitzung

Klicken Sie oben rechts auf die Schaltfläche „Freigeben“ oder auf **Datei** > **Start Collaboration Session** (Zusammenarbeitssitzung starten), um eine Live Share-Sitzung in Visual Studio zu starten. Daraufhin wird ein Link generiert, den Sie mit Ihren Projektmitarbeitern teilen können.

![C&#43;&#43; Schaltfläche „Live Share“](../ide/media/live-share-button-cpp.png "Schaltfläche „Live Share“")

Wählen Sie zum Beenden einer Sitzung **End Collaboration Session** (Zusammenarbeitssitzung beenden) in der Dropdownliste **Freigabe** aus.

![C&#43;&#43; Schaltfläche „Live Share“](../ide/media/live-share-end-session-cpp.png "Schaltfläche „Live Share“")

## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu **Live Share** in Visual Studio finden Sie unter [What is Visual Studio Live Share? (Was ist Visual Studio Live Share)](/visualstudio/liveshare/). Weitere Informationen zu Live Share in Visual Studio Code finden Sie unter [Live Share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare).

## <a name="see-also"></a>Siehe auch

[Edit and refactor code (C++) (Schreiben und Refactoring von Code (C++))](writing-and-refactoring-code-cpp.md)</br>
[Navigate your C++ code base in Visual Studio (Navigieren in Ihrer C++-Codebasis in Visual Studio)](navigate-code-cpp.md)</br>
[Read and understand C++ code (Lesen und Verstehen von C++-Code)](read-and-understand-code-cpp.md)</br>