---
title: Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird
ms.date: 08/20/2019
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: 10bafc9bd06ee94398f91d5af478a6e1cd7ca617
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108455"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird

::: moniker range=">=vs-2019"

Wenn Sie [ATL-Unterstützung zu einer vorhandenen MFC-ausführbaren Datei oder dll hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), fügt Visual Studio standardmäßig eine Header Datei mit dem `#define` Namen " *Framework. h* " hinzu, die-und-Präprozessordirektiven enthält `#include` , um die Verwendung von ATL im Projekt Es werden keine weiteren Dateien oder Klassen hinzugefügt, wie dies in früheren Versionen von Visual Studio geschehen ist.

::: moniker-end

::: moniker range="<=vs-2017"

Wenn Sie [ATL-Unterstützung zu einer vorhandenen MFC-ausführbaren Datei oder dll hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), führt Visual Studio die folgenden Änderungen am vorhandenen MFC-Projekt durch (in `MFCEXE`diesem Beispiel wird das Projekt aufgerufen):

- Zwei neue Dateien (eine IDL-Datei und eine RGS-Datei, die zum Registrieren des Servers verwendet werden) werden hinzugefügt.

- In der Haupt Anwendungs Kopfzeile und den Implementierungs Dateien ("Mfcexe. h" und "Mfcexe. cpp") wird `CAtlMFCModule`eine neue Klasse (abgeleitet von) hinzugefügt. Zusätzlich zur neuen Klasse wird der Code `InitInstance` für die Registrierung hinzugefügt. Außerdem wird der `ExitInstance` -Funktion Code zum Widerrufen des Class-Objekts hinzugefügt. In der Header Datei sind schließlich zwei neue Header Dateien (Initguid. h und Mfcexe_i. c) in der Implementierungs Datei enthalten, die die neuen GUIDs für die `CAtlMFCModule`von abgeleitete Klasse deklarieren und initialisieren.

- Zum ordnungsgemäßen Registrieren des Servers wird der Ressourcen Datei des Projekts ein Eintrag für die neue RGS-Datei hinzugefügt.

::: moniker-end

## <a name="notes-for-dll-projects"></a>Hinweise für DLL-Projekte

Wenn Sie einem MFC-DLL-Projekt ATL-Unterstützung hinzufügen, werden einige Unterschiede angezeigt. Der-Funktion und der `DLLRegisterServer` - `DLLUnregisterServer` Funktion werden zum Registrieren und Aufheben der Registrierung der DLL-Code hinzugefügt. Der Code wird auch [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) und [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject)hinzugefügt.

## <a name="see-also"></a>Siehe auch

[ATL-Unterstützung in einem MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigate-code-cpp.md)
