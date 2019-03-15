---
title: 'Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs'
ms.date: 11/04/2016
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
ms.openlocfilehash: c593d0bae6fc23cfd765116c44b07caa2a6d8ccf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821325"
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs

MFC-Version 7.0 und höher bietet erweiterte Unterstützung für Satelliten-DLLs, ein Feature, können beim Erstellen von Anwendungen, die für mehrere Sprachen lokalisiert. Eine Satelliten-DLL ist eine [reine Ressourcen-DLL](creating-a-resource-only-dll.md) , enthält die Ressourcen einer Anwendung für eine bestimmte Sprache lokalisiert. Wenn die Anwendung die Ausführung beginnt, lädt MFC automatisch die lokalisierte Ressourcen für die Umgebung am besten geeignet. Beispielsweise könnten Sie eine Anwendung mit Sprachressourcen für Englisch und zwei Satelliten-DLL-Dateien, enthält eine französische Übersetzung Ihrer Ressourcen und der andere eine deutsche Übersetzung enthält haben. Wenn die Anwendung auf einem System für die englische Sprache ausgeführt wird, wird die englischen Ressourcen. Wenn auf einem französischen System ausgeführt wird, verwendet es die französischen Ressourcen. Wenn auf einem deutschen System ausgeführt wird, wird die Ressourcen für Deutsch.

In einer bestimmten Sprache lokalisiert, die Ressourcen enthält, zur Unterstützung von lokalisierter Ressourcen in einer MFC-Anwendung MFC versucht, eine Satelliten-DLL zu laden. Satelliten-DLLs werden mit dem Namen *AnwendungsnameXXX*.dll, wobei *ApplicationName* ist der Name der .exe oder .dll, die unter Verwendung von MFC, und *XXX* ist der drei Buchstaben bestehenden Code für die Sprache der Ressourcen (z. B. "ENU" oder "DEU").

MFC versucht, laden die Ressourcen-DLL für jede der folgenden Sprachen in der Reihenfolge und hört, sobald einer gefunden wird:

1. Standardmäßige Benutzeroberflächensprache des aktuellen Benutzers, wie aus der GetUserDefaultUILanguage() Win32-API zurückgegeben.

1. Des aktuellen Benutzers Standard-Benutzeroberflächensprache, ohne jede bestimmte untersprachen (d. h. ENC [Kanadische Englisch] wird [US-DEU Englisch]).

1. Standardmäßige Benutzeroberflächensprache des Systems, wie die GetSystemDefaultUILanguage()-API zurückgegeben. Auf anderen Plattformen ist dies die Sprache des Betriebssystems selbst.

1. Die Benutzeroberflächensprache des Systems standardmäßig, ohne alle spezifischen Sprachvariante an.

1. Eine falsche Sprache mit 3 Buchstaben bestehende Code, loc abgerufen werden

Wenn alle Satelliten-DLLs mit MFC nicht gefunden wird, wird alle Ressourcen in der Anwendung selbst enthalten sind.

Ein Beispiel: Angenommen Sie, eine Anwendung LangExample.exe MFC verwendet, und klicken Sie auf einem Benutzeroberfläche-System ausgeführt wird; die Benutzeroberflächensprache des Systems ist [US-DEU Englisch] und die aktuelle Sprache der Benutzeroberfläche auf FRC [kanadisches Französisch] festgelegt ist. MFC ist die folgenden DLLs in der folgenden Reihenfolge gesucht:

1. SprachenbeispielFRC.dll (Sprache der Benutzeroberfläche).

1. LangExampleFRA.dll (Sprache der Benutzeroberfläche ohne Sprachvariante, in diesem Beispiel Französisch (Frankreich).

1. SprachenbeispielENU.dll (Benutzeroberflächensprache des Systems).

1. LangExampleLOC.dll.

Wenn keine dieser DLLs gefunden werden, verwendet MFC die Ressourcen in LangExample.exe an.

## <a name="see-also"></a>Siehe auch

[DLLs in Visual C++](dlls-in-visual-cpp.md)<br/>
[TN057: Lokalisierung von MFC-Komponenten](../mfc/tn057-localization-of-mfc-components.md)
