---
title: Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: 2651a83c50b03dfffd1ac0238b6c6d0a61888c88
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741560"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Details zur ATL-Unterstützung, die vom ATL-Assistenten hinzugefügt wird

Wenn Sie [ATL-Unterstützung hinzufügen, um eine vorhandene MFC-Anwendung oder DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ stellt die folgenden Änderungen an der vorhandenen MFC-Projekt (in diesem Beispiel heißt das Projekt `MFCEXE`):

- Es werden zwei neue Dateien (einer IDL-Datei und ein RGS-Datei verwendet, um den Server zu registrieren) hinzugefügt.

- In den Hauptthread der Anwendung Header- und Implementierungsdateien Dateien (Mfcexe.h und Mfcexe.cpp) eine neue Klasse (abgeleitet von `CAtlMFCModule`) hinzugefügt wird. Zusätzlich zu der neuen Klasse Code hinzugefügt `InitInstance` für die Registrierung. Außerdem wird Code hinzugefügt die `ExitInstance` -Funktion für das Klassenobjekt aufheben. In der Headerdatei, schließlich zwei neue Headerdateien (Initguid.h und Mfcexe_i.c) sind enthalten in der Implementierungsdatei, deklarieren und initialisieren die neuen GUIDs für die `CAtlMFCModule`-abgeleitete Klasse.

- Um den Server ordnungsgemäß zu registrieren, wird ein Eintrag für die neue RGS-Datei Ressourcedatei des Projekts hinzugefügt.

## <a name="notes-for-dll-projects"></a>Hinweise für die DLL-Projekten

Wenn Sie ATL-Unterstützung zu einem MFC-DLL-Projekt hinzufügen, sehen Sie einige Unterschiede. Code wird hinzugefügt, um die `DLLRegisterServer` und `DLLUnregisterServer` Funktionen für das Registrieren und Aufheben der Registrierung der DLL. Außerdem wird Code hinzugefügt ["DllCanUnloadNow"](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) und [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>Siehe auch

[ATL-Unterstützung in einem MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigate-code-cpp.md)
